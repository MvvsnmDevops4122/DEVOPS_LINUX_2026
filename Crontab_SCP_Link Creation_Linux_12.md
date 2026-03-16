# 📅 Crontab: Scheduling Tasks

## 📌 What is Crontab?

**crontab** stands for **Cron Table**.  

It is used to **schedule commands or scripts** to run automatically at specific times and intervals (minutes, hours, days, weeks, months).

Cron = Background scheduler  
Crontab = File that contains user-defined scheduled tasks


## 🔧 Syntax :

```

* * * * * /path/to/command

---

| | | | |
| | | | +---- Day of the Week (0 - 6) (Sunday = 0 or 7)
| | | +------ Month (1 - 12)
| | +-------- Day of the Month (1 - 31)
| +---------- Hour (0 - 23)
+------------ Minute (0 - 59)

```

## Cron Commands

| Command              | Description                                       |
|----------------------|---------------------------------------------------|
| `crontab -l`         | List all scheduled cron jobs for current user     |
| `crontab -e`         | Edit crontab                                      |
| `crontab -r`         | Remove crontab                                    |
| `crontab -l -u <user>` | View another user's crontab (root only)        |

---

## 🔐 Control Cron Access:

```

sudo touch /etc/cron.allow       # Create allow file
sudo vi /etc/cron.allow          # Add allowed usernames (one per line)

````

---

## 📝 Sample Shell Script – hello.sh

```bash
#!/bin/bash
echo "Welcome to KK FUNDA"
echo "Today date is:"
date
uptime
pwd
````

---

## ▶️ Run the Script

```
sh hello.sh          # Method 1
./hello.sh           # Method 2 (needs execute permission)
chmod u+x hello.sh   # Add execute permission
```

---

## ⏰ Schedule Script in Cron

Add to `crontab -e`:

```
*/1 * * * * /home/ec2-user/hello.sh >> /home/ec2-user/hello.log
```

📝 Use `>>` to append output and preserve logs.

---

# 🕒 20 Cron Job Examples with Explanations

---

## 1️⃣ Run a script every minute
```

* * * * * /path/to/script.sh

```
**Explanation:** Runs the script every single minute — good for frequent health checks.

---

## 2️⃣ Run every 5 minutes
```

*/5 * * * * /path/to/script.sh

```
**Explanation:** `*/5` means "every 5 minutes" — useful for log or service checks.

---

## 3️⃣ Run every hour
```

0 * * * * /path/to/script.sh

```
**Explanation:** Runs on minute `0` of every hour.

---

## 4️⃣ Run daily at 12:00 AM
```

0 0 * * * /path/to/script.sh

```
**Explanation:** Executes at midnight every day — often used for backup rotation.

---

## 5️⃣ Run every day at 6 PM
```

0 18 * * * /path/to/script.sh

```
**Explanation:** Runs at 18:00 (6 PM) daily.

---

## 6️⃣ Run every Monday at 7 AM
```

0 7 * * 1 /path/to/script.sh

```
**Explanation:** `1` represents Monday.

---

## 7️⃣ Run on 1st day of every month
```

0 0 1 * * /path/to/script.sh

```
**Explanation:** Useful for monthly billing, report generation, or cleanup tasks.

---

## 8️⃣ Run at 3:30 AM every day
```

30 3 * * * /path/to/script.sh

```
**Explanation:** Minute `30`, hour `3`.

---

## 9️⃣ Run every 10 minutes
```

*/10 * * * * /path/to/script.sh

```
**Explanation:** Good for periodic monitoring scripts.

---

## 🔟 Run every 30 minutes
```

*/30 * * * * /path/to/script.sh

```
**Explanation:** Runs at :00 and :30 of every hour.

---

## 1️⃣1️⃣ Run every Sunday at midnight
```

0 0 * * 0 /path/to/script.sh

```
**Explanation:** Sunday can be `0` or `7`.

---

## 1️⃣2️⃣ Run at reboot (system startup)
```

@reboot /path/to/script.sh

```
**Explanation:** Executes once after the machine boots — useful for service initialization.

---

## 1️⃣3️⃣ Run Monday to Friday at 9 AM
```

0 9 * * 1-5 /path/to/script.sh

```
**Explanation:** `1-5` means weekdays — useful for office-hour tasks.

---

## 1️⃣4️⃣ Run weekends at 10 AM
```

0 10 * * 6,0 /path/to/script.sh

```
**Explanation:** 6 = Saturday, 0 = Sunday.

---

## 1️⃣5️⃣ Run every 15 minutes between 9 AM and 5 PM
```

*/15 9-17 * * * /path/to/script.sh

```
**Explanation:** Good for business-hour monitoring or log processing.

---

## 1️⃣6️⃣ Run on the last day of the month
```

0 23 28-31 * * [ "$(date +%d -d tomorrow)" = "01" ] && /path/to/script.sh

```
**Explanation:** Runs on 28th–31st but checks if tomorrow is the 1st → last day logic.

---

## 1️⃣7️⃣ Run yearly on January 1st
```

0 0 1 1 * /path/to/script.sh

```
**Explanation:** Only runs at 12:00 AM on Jan 1 — good for yearly maintenance.

---

## 1️⃣8️⃣ Run quarterly (Jan, Apr, Jul, Oct 1st)
```

0 0 1 1,4,7,10 * /path/to/script.sh

```
**Explanation:** Perfect for quarterly reports or audits.

---

## 1️⃣9️⃣ Clean logs every day at 1 AM
```

0 1 * * * > /var/log/app.log

```
**Explanation:** Empties the log file (truncate) every night.

---

## 2️⃣0️⃣ Backup home directory every day at 2 AM
```

0 2 * * * tar -czf /backup/home_$(date +%F).tar.gz /home/user/

```
**Explanation:** Creates a compressed backup file with today’s date.

# 🔐 SCP Command (Secure Copy)

`scp` stands for **Secure Copy Protocol**.  
It is used to **securely transfer files or directories** between:

- Local system → Remote system  
- Remote system → Local system  
- Remote system → Remote system  

It uses **SSH encryption**, so it is secure.

# 📦 SCP Commands (PowerShell & Git Bash)

Below are the correct SCP commands for both **Windows PowerShell** and **Git Bash**.

---

## 🟦 PowerShell
Use **Windows-style paths** with **double quotes**.

### ✅ Upload file (Local → EC2)
```

scp -i "C:\Users\satya\Downloads\KKDevops1.pem" "C:\Users\satya\Downloads\Jenkins_Notes_KKdevops" ec2-user@52.66.252.67:/home/ec2-user/

```

### ✅ Download file (EC2 → Local)
```

scp -i "C:\Users\satya\Downloads\KKDevops1.pem" ec2-user@52.66.252.67:/home/ec2-user/hello.sh "C:\Users\satya\Downloads"

```

---

## 🟩 Git Bash
Use **Linux-style paths** starting with `/c/...`

### ✅ Upload file (Local → EC2)
```

scp -i /c/Users/satya/Downloads/KKDevops1.pem /c/Users/satya/Downloads/Jenkins_Notes_KKdevops ec2-user@52.66.252.67:/home/ec2-user/

```

### Explanation

-i /c/Users/satya/Downloads/KKDevops1.pem → Your key

/c/Users/satya/Downloads/Jenkins_Notes_KKdevops → Source

ec2-user@52.66.252.67 → EC2 username + public IP

/home/ec2-user/ → Upload destination

### ✅ Download file (EC2 → Local)
```

scp -i /c/Users/satya/Downloads/KKDevops1.pem ec2-user@52.66.252.67:/home/ec2-user/hello.sh /c/Users/satya/Downloads/

```

---

# 📝 Notes
- PowerShell → Use `"C:\path\to\file"`  
- Git Bash → Use `/c/path/to/file`  
- Both require **inbound SSH (port 22)** allowed in AWS Security Group  
- `.pem` file should have correct permissions:  
```

chmod 400 <key>.pem    # (only required in Git Bash)

```

---



