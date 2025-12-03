# Day-7 Linux Fundamentals Part 7 — Section 1: Advanced Process Management

**Lab Folder:** `Day-7-Linux-Fundamentals-Part-7`
**Purpose:** Learn advanced process management in Kali Linux, including viewing, searching, terminating, and prioritizing processes.
All commands are Kali-safe — no syntax errors even if multiple or zero PIDs exist.

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

**Screenshot Checkpoint:**
`Section1_Step2_search.png`

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

**Explanation:**

* `sleep 500 &` runs a background process for testing.
* `pgrep sleep` finds its PID.
* `kill $(pgrep sleep | head -n 1)` kills only one process.
* `killall sleep` kills all sleep processes safely.

**Screenshot Checkpoint:**
`Section1_Step3_kill.png`

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

**Explanation:**

* `yes > /dev/null &` generates CPU load for testing.
* `ps -o pid,ni,cmd` shows PID, nice value (priority), and command.
* `renice +10` lowers priority, `renice -5` raises it.
* `head -n 1` ensures only one PID is modified.

**Screenshot Checkpoint:**
`Section1_Step4_priority.png`

---

## Step 5 — Section Complete

* All steps are **Kali-safe** and can be executed without syntax errors.
* Screenshots should be stored in the same folder.
* Commands and screenshots are **self-contained** for easy GitHub viewing.

**Screenshot Links (Relative Paths for Browser):**

```markdown
![Process Search](Section1_Step2_search.png)
![Terminate Processes](Section1_Step3_kill.png)
![Priority Management](Section1_Step4_priority.png)
```

---

## GitHub Commit Reminder

From your repo root:

```bash
git add Day-7-Linux-Fundamentals-Part-7
git commit -m "Add Day-7 Section 1 lab with screenshots"
git push origin main
```

* After pushing, open GitHub in your browser to confirm the README.md renders correctly and screenshots display inline.

---

**Notes:**

* Each Day’s folder is standardized (`Day-7-Linux-Fundamentals-Part-7`) to maintain consistency across the repo.
* Following this structure keeps your repository recruiter-friendly and organized.
