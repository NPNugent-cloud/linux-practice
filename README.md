# linux-practice
My Linux Fundamentals learning journey,notes,commands, and labs

## Day 1 – Linux Permissions Lab

**Objective:** Practice file permissions with chmod and chown.

**Lab Steps:**
1. Created a training directory: `~/training/test-permissions`  
2. Created files:
   - `alpha.txt`
   - `beta.txt`
   - `gamma.sh`
   - `delta.log`

3. Applied permissions using `chmod`:
   - `alpha.txt` → 744
   - `beta.txt` → 660
   - `gamma.sh` → 755
   - `delta.log` → 600

4. Verified permissions with `ls -l`  


## Linux Fundamentals 2 – Day 1 Screenshots

### chmod Numeric Code Lab

![chmod lab 1](day-1-permissions/10_chmod_numeric_code_lab_1.png)
![chmod lab 2](day-1-permissions/10_chmod_numeric_code_lab_2.png)

## Day 2 — Linux Fundamentals Part 2
Completed lab covering permissions, ownership, chmod, chown, and permission verification.  
[View the work →](./Day-2-Linux-Fundamentals-Part-2/README.md)

# Linux Fundamentals Part 3 — Day 3 Lab

## Overview
This lab focused on:
- Understanding processes
- Starting and killing background jobs
- Managing services with systemctl
- Monitoring system processes

---

## Screenshots & Notes

### 1. List running processes
![screenshot1](./screenshot1.png)
- Ran `ps aux` to view all active processes.

### 2. Start a background process
![screenshot2](./screenshot2.png)
- Command: `sleep 200 &`  
- Verified the job started and noted the PID.

### 3. Identify and verify process
![screenshot3](./screenshot3.png)
- Verified PID with `ps -p <PID> -o pid,ppid,user,etime,cmd`.

### 4. Kill the process safely
![screenshot4](./screenshot4.png)
- Used `kill <PID>`  
- Verified process terminated with `ps -p <PID>`.

### 5. Check service status
![screenshot5](./screenshot5.png)
- Command: `systemctl status cron.service`.

### 6. Stop the service
![screenshot6](./screenshot6.png)
- Command: `sudo systemctl stop cron.service`.

### 7. Start the service
![screenshot7](./screenshot7.png)
- Command: `sudo systemctl start cron.service`.

### 8. Optional: Enable service at boot
![screenshot8](./screenshot8.png)
- Command: `sudo systemctl enable cron.service`.

---

## Key Takeaways
- Learned to track and manage processes  
- Learned to safely kill background jobs  
- Learned to view, stop, start, and enable services  
- Gained confidence in systemctl commands and Linux process management
- 


## Day 4 — Linux Fundamentals Part 4
Completed lab covering:
- File creation and editing
- Searching text in files
- Locating files in directories
- Basic text manipulation with awk

[View Day 4 Lab →](./Day-4-Linux-Fundamentals-Part-4/README.md)



## Day 5 — Linux Fundamentals Part 5
Completed lab covering:
- Viewing and understanding file permissions
- Changing file ownership
- Modifying file permissions (symbolic and numeric)

[View Day 5 Lab →](./Day-5-Linux-Fundamentals-Part-5/README.md)



## Day 6 — Linux Fundamentals Part 6
Completed lab covering:
- Creating directories and organizing files
- Archiving files with tar
- Extracting archives
- Compressing archives using gzip and bzip2

[View Day 6 Lab →](./Day-6-Linux-Fundamentals-Part-6/README.md)



## Day 7 — Linux Fundamentals Part 7
Completed lab covering:
- Advanced process management in Kali Linux
- Viewing all processes with `ps aux` and real-time monitoring with `top` and `htop`
- Searching for specific processes using `pgrep` and `ps` with safe handling of multiple or zero PIDs
- Terminating processes individually or in bulk with `kill` and `killall`
- Adjusting process priorities with `renice` to manage CPU usage
- Capturing screenshots for documentation and verification

[View Day 7 Lab →](./Day-7-Linux-Fundamentals-Part-7/README.md)



## Day 8 — Linux Fundamentals Part 8
Completed lab covering:
- Understanding systemd and managing services
- Checking service status and enabling/disabling services safely
- Enabling and starting SSH service on Kali VM
- Generating SSH key pairs for passwordless login
- Copying public keys to remote VM for key-based authentication
- Securing SSH by disabling root login and password authentication
- Capturing screenshots at every step for documentation and verification

[View Day 8 Lab →](./Day-8-Linux-Fundamentals-Part-8/README.md)


