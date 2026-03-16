# 👤 Linux User and Group Management Commands

---

## 🏠 User Home Directories

```bash
ls -l /home
```

→ List all user home directories.

---

## 👨‍💻 User Management

| Command                                      | Description                                      |
| -------------------------------------------- | ------------------------------------------------ |
| `sudo useradd kkfunda`                       | Create a new user named `kkfunda`.               |
| `cat /etc/passwd`                            | View all user information.                       |
| `sudo passwd kkfunda`                        | Set or change a password for user `kkfunda`.     |
| `sudo cat /etc/shadow`                       | Check how password data is stored (encrypted).   |
| `sudo chage kkfunda`                         | Set password expiration for a user.              |
| `sudo chage -l username`                     | View user password expiration and aging details. |
| `usermod -l new_username old_username`       | Change an existing username.                     |
| `usermod -d /new/home/directory -m username` | Change user’s home directory and move files.     |
| `passwd -l username`                         | Lock a user account.                             |
| `passwd -u username`                         | Unlock a user account.                           |
| `userdel username`                           | Delete a user (keep home directory).             |
| `userdel -r username`                        | Delete a user and remove home directory.         |

---

## 👥 Group Management

| Command                                   | Description                                    |
| ----------------------------------------- | ---------------------------------------------- |
| `sudo groupadd devops`                    | Create a new group named `devops`.             |
| `cat /etc/group`                          | View all groups and their members.             |
| `getent group`                            | Alternative command to view group list.        |
| `sudo usermod -aG devops kkfunda`         | Add user `kkfunda` to `devops` group (append). |
| `sudo usermod -aG group1,group2 username` | Add user to multiple groups simultaneously.    |
| `sudo lid -g devops`                      | Verify members of a group.                     |
| `id username`                             | Display user ID and group memberships.         |
| `groups kkfunda`                          | Show all groups the user belongs to.           |
| `gpasswd -d username groupname`           | Remove a user from a group.                    |
| `groupdel groupname`                      | Delete a group.                                |

---

## 📁 Files Involved in User & Group Management

| File          | Description                               |
| ------------- | ----------------------------------------- |
| `/etc/passwd` | Stores basic user account information.    |
| `/etc/shadow` | Stores encrypted password data.           |
| `/etc/group`  | Stores group information and memberships. |
