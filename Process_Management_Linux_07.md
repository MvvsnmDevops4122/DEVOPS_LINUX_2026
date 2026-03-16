
#  Process Management in Linux

---

## (a) Viewing or Checking Processes

| Command | Description |
|----------|-------------|
| `ps` | List currently running processes |
| `ps aux` | View all running processes (with detailed info) |
| `ps aux \| nl` or `ps aux \| wc -l` | View all running processes along with numbering/count |
| `ps aux` | Shows memory and CPU utilization |
| `ps -ef` | Lists all running processes (without memory/CPU utilization) |
| `ps -u <username>` | Show processes for a specific user |
| `ps -C <processname>` | Show a process by name |
| `pgrep <processname>` | Find a process by name and return its PID |
| `pidof <processname>` | Find the PID of a running program |

---

## (b) Managing Processes

### 🔹 Killing Processes

| Command | Description |
|----------|-------------|
| `kill <PID>` | Terminate a process by its PID |
| `pkill <processname>` | Terminate a process using its name |
| `kill -9 <PID>` | Forcefully kill a process by PID |
| `pkill -9 <processname>` | Forcefully kill a process using its name |

---

### 🔹 Stopping & Resuming Processes

| Command | Description |
|----------|-------------|
| `kill -STOP <PID>` | Temporarily stop (pause) a running process |
| `kill -CONT <PID>` | Continue/resume a stopped process |

---

## (c) Changing Process Priority

| Command | Description |
|----------|-------------|
| `top` | View process priorities interactively |
| `renice -n 10 -p <PID>` | Lower process priority (positive value) |
| `renice -n -5 -p <PID>` | Increase process priority (negative value, requires root) |

---

## 🧩 Daemon Processes

Daemon processes are background services that run continuously **without user interaction**.

| Command | Description |
|----------|-------------|
| `systemctl list-units --type=service` | List all system daemon services |
| `systemctl start <service-name>` | Start a daemon/service |
| `systemctl stop <service-name>` | Stop a daemon/service |
| `systemctl enable <service-name>` | Enable a service to start automatically on boot |

---

## ⚙️ Services in Linux

- **Services** are special types of processes managed by the system.  
- They usually start **automatically during system boot**.  
- Examples: `sshd`, `crond`, `networking.service`

---

✅ **Tip:**  
You can monitor running services and their statuses using:
```bash
systemctl status <service-name>
````

Or view all active services:

```bash
systemctl list-units --type=service --state=active
```
