# Day-7 Linux Fundamentals Part 7 — Advanced Process Management

**Lab Folder:** `Day-7-Linux-Fundamentals-Part-7`
**Purpose:** Learn advanced process management in Kali Linux, including viewing, searching, terminating, and prioritizing processes.
All commands are Kali-safe — no syntax errors even if multiple or zero PIDs exist.

---

## Step 1 — View Running Processes

**Objective:** Learn to list processes and view them interactively.

**Basic process listing:**

```bash
ps aux
```

* Shows every process for all users with PID, CPU/memory usage, and command.

**Interactive real-time monitoring:**

```bash
top
```

* Press **q** to quit.

**Optional: If `htop` is installed:**

```bash
htop
```

* Easier to navigate and see CPU/memory usage visually.
* Use arrow keys to scroll and **F10** to quit.

![screenshot1a](./s2_pa_aux_output.png)
![screenshot1b](./s3_top_running.png)
![screenshot1c](./s4_htop_running.png)

---

## Step 2 — Search for Specific Processes

**Objective:** List and inspect processes safely.

**Commands:**

```bash
# List all bash processes
ps -ef | grep [b]ash

# Optional: Get only PIDs
pgrep bash

# Safely list details for all bash PIDs
pgrep bash | xargs -r ps -o pid,ppid,cmd -p

# Find PID of systemd
pidof systemd
```

**Explanation:**

* `ps -ef | grep [b]ash` lists running bash processes; `[b]ash` prevents grep from appearing.
* `pgrep bash` outputs all bash PIDs.
* `xargs -r ps -o pid,ppid,cmd -p` safely handles multiple or zero PIDs.
* `pidof systemd` finds the main systemd PID.

![screenshot1a](./s5_ps-ef_grep[b]ash.png)
![screenshot1a](./s6_pidof_systemd.png)

---

## Step 3 — Terminate Processes

**Objective:** Safely terminate individual or all processes.

**Commands:**

```bash
# Start a dummy background process
sleep 500 &

# Verify PID
pgrep sleep

# Kill a single process safely
kill $(pgrep sleep | head -n 1)

# Start another dummy process
sleep 800 &

# Kill all sleep processes
killall sleep
```

![screenshot1a](./s7_kill_processes.png)

---

## Step 4 — Adjust Process Priorities

**Objective:** Change process priorities using nice values.

**Commands:**

```bash
# Start a CPU-intensive process
yes > /dev/null &

# Check current priority
ps -o pid,ni,cmd -p $(pgrep yes | head -n 1)

# Lower priority (increase nice value)
sudo renice +10 $(pgrep yes | head -n 1)

# Raise priority (decrease nice value)
sudo renice -5 $(pgrep yes | head -n 1)
```

![screenshot1a](./s8_prioritising_deprioritising.png)





