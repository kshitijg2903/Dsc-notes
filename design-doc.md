# Multi‑Client Chat Server (Threads & Events)

**Course Assignment**: Multi‑client chat server implemented in two variants — thread‑based and event‑based.

**Port Used**: 5432
**Test Date**: 13 Sep 2025

---

## 1) Brief Overview of the Implementation

### A. `server_threads` (Thread‑per‑Client)

* The main thread creates a listening TCP socket and accepts connections.
* For each accepted client socket, the server spawns a detached handler thread responsible only for **reading** from that client and writing received bytes to the server’s `stdout`.
* The main thread also reads from `stdin`. Each line typed on the server is sent to **exactly one** connected client using a round‑robin selector. The send path uses a small `send_all` helper to handle partial writes and appends a newline if the line lacks one.
* A shared array of active client FDs is protected by a mutex for safe add/remove and for choosing the next target in round‑robin. On client disconnect, the handler thread removes its FD and exits gracefully.
* `SIGPIPE` is ignored (or `MSG_NOSIGNAL` is used) so that broken pipes don’t crash the server.

### B. `server_events` (Single‑Threaded, `select()` Event Loop)

* A single event loop monitors the listening socket, `stdin`, and all connected client sockets using `select()`.
* When `listen_fd` is readable, the server accepts a new client and adds its FD to the `fd_set` and an in‑memory list.
* When `stdin` is readable, one full line is read and sent to **one** client chosen by round‑robin (same policy as threads variant) with `send_all`.
* When a client FD is readable, the server `recv()`s available bytes and writes them to `stdout`. A zero‑length read or error triggers removal, `FD_CLR`, and close.

**Shared Behavior Across Both Variants**

* **Client → Server**: Any text a client sends is displayed on the server terminal.
* **Server → Clients**: Text typed on the server goes to **one** client at a time (round‑robin), not all clients.
* Clean disconnect handling; resource cleanup on client departure; no global lock around the whole structure (fine‑grained in threads; none needed in events).

---

## 2) Are messages sent by all four clients displayed on the server's terminal?

**Yes.** Verified with four concurrent clients connecting to the same server on port 5432. Messages from **each** client are visible on the server terminal.

**Note on TCP framing**: TCP may deliver data in chunks. The server prints exactly the bytes it receives; therefore partial lines may appear if clients send without `\n` or if their output is split by the network stack. This is expected for raw TCP; it does not indicate data loss. If strictly line‑by‑line display is desired, the client can buffer until `\n` before printing.

---

## 3) Build & Run (for reference)

```bash
make clean && make
# Variant 1: Threads
./server_threads
# Variant 2: Events
./server_events
# In four other terminals
./client localhost
```

**Observed Behavior**

* All client messages appear on server.
* Server‑typed lines are delivered to exactly one client per line in round‑robin order.
* Disconnects are handled without impacting other clients.

---

## 4) Group Members

* **Name**: Kshitij Gupta
  **Roll No.**:2022257
* **Name**: Mohit Bhariya
  **Roll No.**: 2023327
* **Name**: Rajit Bhagat
  **Roll No.**: 2023423
* **Name**: Arpit Dabas
  **Roll No.**: 2023131
* **Name**: Sanjeev
  **Roll No.**: 2023483


---

## 5) Files Submitted - 

* Threaded implementation: **server\_threads.c**
* Event‑based implementation: **server\_events.c**
* Design document: **Design.pdf** (this document)


