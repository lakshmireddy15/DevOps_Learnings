
# MQ Database Notes

---

## Proxy: Forward Proxy and Reverse Proxy

A **proxy** server is an intermediate server that sits between the client and the server, forwarding requests and responses.

> Think of it as a middleman handling communication between two people.

### Forward Proxy (Client-side proxy)

A **forward proxy** sits in front of the client and forwards the client’s requests to the internet (servers).

```
Client ---> Forward Proxy ---> Internal Servers
```

- Hides the client-side IP
- Monitors outgoing traffic

### Reverse Proxy (Server-side proxy)

A **reverse proxy** sits in front of the server and handles the requests that come from the client to the backend servers.

```
Client ---> Reverse Proxy ---> Internal Servers
```

- Hides the server IP

---

## Synchronous vs Asynchronous

### Synchronous

- Each task runs one after another.
- A new task won’t start until the previous one finishes.
- Blocks the flow.
- Simple and easy to understand.
- **Not suitable for long and waiting tasks.**

Example:

```
Wait for 1 minute ---> No response ---> Raises an error
```

### Asynchronous

- Tasks can start, pause, allow others to run, and come back when ready.
- Non-blocking system.
- Improves performance.
- Can handle multiple operations (e.g., sending a message, opening new chat).

---

## Message Queue (MQ)

Used to handle asynchronous communication.

### Types of Communication

#### 1. Point-to-Point Communication

- **Sender → Receiver**  
- **Producer → Consumer**  
- Example: WhatsApp (1-on-1 messaging)

Structure:

```
Producer ---> Queue ---> Consumer
```

- Messages are stored in a queue (e.g., RabbitMQ, ActiveMQ).
- Only one consumer gets each message.
- Once delivered, the message is deleted from the queue.

#### 2. Topic-to-Subscriber (Publish/Subscribe)

- One sender publishes a message.
- Multiple subscribers receive it.
- Messages are published to a **topic** (e.g., Kafka).
- All active subscribers get a **copy** of the message.

Example:

```
Publisher → [Topic] → Subscriber 1  
                     → Subscriber 2  
                     → Subscriber 3
```

---

## inode

**inode** = Index node  
Stores **metadata** of the file (not content). Includes:

- File size
- File permissions
- Owner
- Group
- Pointers to actual file data blocks

> A **data block** is a chunk of disk space that holds part of your file content.

Each file and directory is assigned a **unique inode number**.

Commands:

```bash
ls -i <filename>      # View the inode number of a file
stat <filename>       # Detailed file info including inode
```

---

## File System

A **file system** is the system used for managing data on storage devices (e.g., hard disk, SSD).

---

## Hard Link

- A **hard link** is like an alias name or second name for an existing file.
- Multiple hard links can point to the same inode (file data).

Example:

```
file.txt <----> link.txt (hard link)
```

- Both point to the same data on disk.
- If `file.txt` is deleted, `link.txt` still accesses the data.
- Disk space is only freed when **all** hard links are deleted.

---
