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
![screenshot1](./s1_process_listing.png)
- Ran `ps aux` to view all active processes.

### 2. Start a background process
![screenshot2](./s2_start_process_manually.png)
- Command: `sleep 200 &`  
- Verified the job started and noted the PID.

### 3. Identify and verify process
![screenshot3](./s3_id_sleep_process.png)
- Verified PID with `ps -p <PID> -o pid,ppid,user,etime,cmd`.

### 4. Kill the process safely
![screenshot4](./s4_kill_sleep_process.png)
- Used `kill <PID>`  
- Verified process terminated with `ps -p <PID>`.

### 5. Check service status
![screenshot5](./s5_check_services.png)
- Command: `systemctl status cron.service`.

### 6. Stop the service
![screenshot6](./s6_stop_services.png)
- Command: `sudo systemctl stop cron.service`.

### 7. Start the service
![screenshot7](./s7_restart_services.png)
- Command: `sudo systemctl start cron.service`.

### 8. Optional: Enable service at boot
![screenshot8](./s8_enable_service_boot.png)
- Command: `sudo systemctl enable cron.service`.

---

## Key Takeaways
- Learned to track and manage processes  
- Learned to safely kill background jobs  
- Learned to view, stop, start, and enable services  
- Gained confidence in systemctl commands and Linux process management
