# Shell Script Execution

There are two common ways to execute a shell script:

```bash
sh <filename.sh>       # Executes using 'sh' shell
./<filename.sh>        # Executes directly (file must be executable)
```

## Disadvantages of Shell Scripting

- No proper error handling
- Difficult to manage across multiple servers (not scalable)
- Assumes a homogeneous environment
- Syntax is sometimes hard to understand
- Password security is not built-in
- Scripts are not idempotent (re-running may cause issues)

---

# Configuration Management

Configuration Management is the process of provisioning and configuring servers for application hosting. It involves:

- Installing required packages
- Setting up programming languages
- Creating folders and users
- Downloading the code
- Installing dependencies
- Creating systemd/systemctl services
- Starting the service/server

### Flow:

1. Provision server
2. Configure (as described above)
3. Deploy application:
   - Remove old versions
   - Download new version
   - Restart services

---

# Pull vs Push Model in Configuration Management

## Pull-Based Model (e.g., Chef)

- Configuration scripts are available on the **CM Server**.
- Nodes (agents) check the CM server every 30 minutes for new configurations.
- If new configurations are found, they are downloaded and executed on the node.

### Architecture:

```plaintext
Control Server ----> CM Server (Configurations) <----- Node 1 (Agent)
                                                        Node 2 (Agent)
                                                        Node 3 (Agent)
```

### Disadvantages:

1. Unnecessary traffic (nodes poll every 30 minutes even if no changes)
2. Wasted system resources
3. Increased power usage
4. Requires agent software
5. Protocols developed for agent communication

---

## Push-Based Model (e.g., Ansible)

- Ansible Server contains both the configurations and acts as the control/master node.
- Ansible uses **SSH protocol** to push configurations directly to nodes.

### Architecture:

```plaintext
Ansible Server (Config) ----SSH----> Node 1
                                    Node 2
                                    Node 3
```

### Advantages:

1. Uses secure SSH protocol
2. No agent software required
3. No unnecessary resource usage
4. Easier to manage and scale

---
