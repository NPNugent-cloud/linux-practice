# Linux Fundamentals Part 7 — Day 7 Lab

## Overview

This lab focused on:

* Viewing running processes (ps, top, htop)
* Searching for processes safely (pgrep, ps, pidof)
* Terminating processes (kill, killall) without syntax errors
* Adjusting process priorities (nice, renice)
* Taking screenshot checkpoints for verification

---

## Screenshots & Notes

### 1. View running processes

![s1\_processes](./s2_ps_aux_output.png)

* Ran `ps aux` to list all processes and `top` for real-time monitoring. If `htop` is installed, used `htop` for easier navigation. Quitted interactive tools with `q` or `F10`.

### 2. Search for specific processes

![s2\_search](./Section1_Step2_search.png)

* Used `ps -ef | grep [b]ash` to list bash processes, `pgrep bash` for PIDs, and `pgrep bash | xargs -r ps -o pid,ppid,cmd -p` to safely show details. Verified `systemd` PID with `pidof systemd`.

### 3. Terminate processes

![s3\_kill](./Section1_Step3_kill.png)

* Started background `sleep` processes and used `pgrep sleep` to find them. Killed a single process with `kill $(pgrep sleep | head -n 1)` and removed all `sleep` processes with `killall sleep`.

### 4. Adjust process priorities

![s4\_priority](./Section1_Step4_priority.png)

* Launched `yes > /dev/null &` to generate CPU load. Checked nice values with `ps -o pid,ni,cmd -p $(pgrep yes | head -n 1)` and adjusted priority using `sudo renice +10` and `sudo renice -5` on the single PID.

---

## Key Takeaways

* Process inspection and interactive monitoring are critical for system troubleshooting.
* Always use Kali-safe commands to avoid PID syntax errors (use `xargs -r`, `head -n 1`, or `ps -ef | grep [b]ash`).
* Use `kill` for specific PIDs and `killall` for targeted process names.
* `renice` requires sudo to raise priority; lowering priority (higher nice value) is safe for background load testing.

---



