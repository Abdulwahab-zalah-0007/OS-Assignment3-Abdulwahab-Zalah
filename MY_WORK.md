# 📝 MY_WORK: Student Information, Development Log, Reflection & Answers

> This is the **only file** your instructor reads to grade Parts 3 and 4 (documentation and video). Everything you write here must be **in your own words**.

---

## 🛑 STOP: Read This Before You Do Anything Else

> ### 1️⃣ Read the whole `README.md` first
> The `README.md` in this repository contains the full instructions: how this assignment continues Assignment 1, the Chapter 5 recap, class descriptions, feature specifications, question prompts and the video script. **If you skip it, you will lose marks.**
>
> ### 2️⃣ Understand the full code before answering any question
> Open `SchedulerSimulationSync.java` and read it **from top to bottom**. You must be able to explain what `SharedStats`, `ReadyQueue`, `CpuWorker`, `RaceWindow.pause()`, `ReentrantLock` and `Semaphore` do **before** you write a single answer in Parts B and C. **Run the original starter first** (it is intentionally broken) and **save its output**: you need it for Question 1 of Part C.
>
> ### 3️⃣ Use only the code of this repository
> Work **only** on `SchedulerSimulationSync.java` from this repository. Do **not** copy or paste code from your previous assignments.
>
> ### 4️⃣ Commit many times, not once
> A single commit, or all commits made in the last hour, costs you **-0.5 mark**. See the [Commit Rules](#-commit-rules-mandatory) below.

**How to use this file:**
1. Fill in your **Student Information** (below) right now.
2. Follow the steps in the **Work Roadmap** in order.
3. Update the **Development Log** *every time* you work on the assignment, not at the end.
4. Do not delete any section header. Replace the `[...]` placeholders with your own text.

---

## 👤 Student Information

> ⚠️ **WARNING:** Fill this in first. Your name and ID must match the student ID you set in `SchedulerSimulationSync.java` (line 304) and the one you say in your video.

| Field | Your Answer |
|-------|-------------|
| **Full Name** | Abdulwahab Zalah |
| **Student ID** | 445050007 |
| **University Email** | 445050007@std.psau.edu.sa |
| **GitHub Username** | Abdulwahab-zalah-0007 |
| **Repository Link** | https://github.com/Abdulwahab-zalah-0007/OS-Assignment3-Abdulwahab-Zalah |
 
---

## 🎥 Video Link

**Video Link**: [Paste your video link here]

> ⚠️ **WARNING:** The video must be **publicly accessible** ("Anyone with the link can view") on **Google Drive**, **YouTube (Unlisted or Public)** or any other cloud file-sharing system. A private, restricted or broken link counts as a **missing video (-1 mark)**.
>
> 💡 **TIP:** Open the link in a **private/incognito window** before you submit. If it asks you to log in or request access, it is not public.
>
> 📌 **NOTE:** The link goes in **this file only** (`MY_WORK.md`), **not** in `README.md`. Name your video file `StudentID_Assignment3_Demo.mp4`. It must last **2 to 3 minutes**.

---

## 🗺️ Work Roadmap (follow in this order)

| Step | What to do | Where | Marks |
|:----:|------------|-------|:-----:|
| 0 | Read `README.md`, read the full code, **run the original starter and save its output** (it fails on purpose) | Your IDE | – |
| 1 | Fork, rename, keep the repo **PUBLIC**, set your student ID (line 304), **commit** | GitHub + code | Part 1 (1) |
| 2 | Feature 1: Mutex lock on the ready queue, **commit** | Code | Part 2 (0.25) |
| 3 | Feature 2: Mutex lock(s) on the shared statistics, **commit** | Code | Part 2 (0.25) |
| 4 | Feature 3: Counting semaphore instead of busy waiting, **commit** | Code | Part 2 (0.5) |
| 5 | Development Log (5+ entries, different dates) | This file, Part A | Part 3 (0.5) |
| 6 | Reflection (4 questions) | This file, Part B | Part 3 (0.5) |
| 7 | Technical Answers (4 questions) | This file, Part C | Part 3 (0.5) |
| 8 | Record the video, upload it, paste the link above | Video + this file | Part 4 (1.5) |
| 9 | Final check, then submit the repo link on Blackboard | Blackboard | – |

> 💡 **TIP:** Tick each step off as you go. Do not leave the log, the reflection or the video for the last day.

---

## 🔁 Commit Rules (MANDATORY)

> ### ⚠️ MANY COMMITS ARE REQUIRED. A single bulk commit is penalized (-0.5 mark).

**Minimum: 4 meaningful commits. Aim for 7 or more.**

| # | Commit | Example message |
|:-:|--------|-----------------|
| 1 | Student ID set | `Set my student ID: 441234567` |
| 2 | Feature 1: Ready queue lock | `Feature 1: Protected the ready queue with a ReentrantLock` |
| 3 | Feature 2: Statistics locks | `Feature 2: Added locks to the shared statistics counters` |
| 4 | Feature 3: Semaphore | `Feature 3: Replaced busy waiting with a counting semaphore` |
| 5 | Development log entries | `Docs: Added development log entries 1-3` |
| 6 | Reflection and answers | `Docs: Completed reflection and technical answers` |
| 7 | Video link | `Docs: Added demo video link` |

**Rules:**
- ✅ **One commit per feature.** Do not put all three features in one commit.
- ✅ **Commit after each work session**, and after each part of this file.
- ✅ **Spread your commits over different dates.** Not all in one day.
- ❌ **Do not make all commits in the last hour** before the deadline (November 14, 2026).
- ❌ **No vague messages** like `done`, `update` or `final version`.

> 💡 **TIP:** Your commit history is checked and you **show it in your video** (at least 4 commits visible). Your development log dates should match your commit dates.
>
> 💡 **TIP:** **Use VS Code** (see *Recommended Development Environment* in `README.md` for the full setup). Sign in to GitHub in VS Code, then commit from the Source Control panel (Ctrl+Shift+G) → stage → write a message → Commit → Sync/Push. You can edit and commit this file the same way. **Pushing** matters: commits that are not pushed to GitHub are invisible to the instructor.

---

# Part A: Development Log (0.5 mark)

> ⚠️ **WARNING:** Minimum **5 entries**, spread over **different dates**. Five entries written on the same day, or written all at once at the end, will lose marks and look like a copy. Entry dates should be **between the start of the assignment and the deadline (November 14, 2026)**.
>
> 💡 **TIP:** Write an entry at the **end of each work session**, while you still remember what happened. It takes 5 minutes.
>
> 💡 **TIP:** Be specific. "Worked on the code" is a weak entry. "Added a `ReentrantLock queueLock` to `ReadyQueue` and wrapped the body of `poll()` in `lock()` / `try` / `finally { unlock() }`" is a strong one.
>
> 📌 **NOTE:** Each entry needs: date and time, what you did, details, challenges, solution, and time spent. Real challenges are fine (and expected). Do not invent fake ones.

## Example Entry (do not copy it, write your own)

### Entry 1 - [November 2, 2026, 4:30 PM]
**What I did**: Forked the repository, set my student ID, and ran the original starter

**Details**:
- Forked the starter repository and renamed it
- Changed student ID on line 304 to my actual ID (441234567)
- Ran the original program: 4 CPUs started, three of them picked `P1`, then `IllegalThreadStateException` and the watchdog stopped the program
- Saved the output in a text file for Question 1
- Committed and pushed: `Set my student ID: 441234567`

**Challenges**: I did not understand why the same process was picked by three CPUs

**Solution**: Read `ReadyQueue.poll()` again and found the `RaceWindow.pause()` between reading the head and removing it

**Time spent**: 45 minutes

---

## Your Development Log

### Entry 1 - November 8, 2026, 12:45 AM
**What I did**: Set up GitHub, forked and renamed the repository, set my student ID, and ran the original starter

**Details**:
- Checked that my GitHub account uses my university email (445050007@std.psau.edu.sa) as primary and verified
- Forked the starter repository and renamed it to OS-Assignment3-Abdulwahab-Zalah (public)
- Cloned it in VS Code and set my Git name and email
- Changed line 304 to my student ID: 12 processes, quantum 3000 ms, 2 CPUs
- Ran the original starter: CPU-1 and CPU-2 both picked P1, then IllegalThreadStateException on CPU-2. P9 was lost, so CPU-1 kept polling the empty queue until the watchdog stopped the program after 31 s
- Verification: context switches 23/24, completed 11/12, service time 52499/53380, busy-waiting polls 987
- Committed and pushed: `Set my student ID: 445050007`

**Challenges**: The first time I copied the output before the program finished, so the verification block was missing. VS Code also opened the folder in Restricted Mode.

**Solution**: I waited for the watchdog message and copied the full output again. I trusted the folder so the Java extension could run the program.

**Time spent**: 1 hour 15 minutes

---

### Entry 2 - November 10, 2026, 1:50 AM
**What I did**: Feature 1 - protected the ready queue with a ReentrantLock

**Details**:
- Imported `ReentrantLock` and declared `queueLock` in `ReadyQueue` (one lock for both `list` and `map`)
- Wrapped `add()`, `poll()`, `processOf()` and `snapshot()` in `lock()` / `try` / `finally { unlock() }`
- In `poll()`, reading the head and removing it are now one atomic step
- Result: no exception, CPU-1 picked P1 and CPU-2 picked P2, and all 12 processes finished
- Context switches was still 23/24 and busy-waiting polls was 5 (Feature 2 and 3 not done yet)
- Committed and pushed Feature 1

**Challenges**: When I replaced the body of `poll()` I selected one line too few, so the old `return head;` stayed after the closing brace and the code did not compile. Pasting also shifted the indentation of the first line.

**Solution**: I deleted the extra `return head;` and checked that the error count went back to 0. I fixed the indentation manually after each paste.

**Time spent**: 30 minutes

---

### Entry 3 - November 10, 2026, 3:30 AM
**What I did**: Feature 2 - protected the three shared statistics with one lock per variable

**Details**:
- Declared `contextSwitchLock`, `completedLock` and `serviceTimeLock` in `SharedStats`
- Protected the three update methods and the three getters with `lock()` / `try` / `finally`
- Chose one lock per variable because the three counters are independent
- Edited the methods from the bottom of the class to the top so the line numbers did not change while I worked
- Ran 3 times: context switches 24/24, completed 12/12, service time 53380/53380 in every run; only busy-waiting polls (5) was still wrong
- Committed and pushed Feature 2

**Challenges**: The new lock names were underlined in red while I was editing the getters, and an old comment from the original line stayed after a closing brace.

**Solution**: I understood the red lines were only because the locks were not declared yet; they disappeared after I added the declarations. I removed the old comment.

**Time spent**: 45 minutes

---

### Entry 4 - November 10, 2026, 8:20 PM
**What I did**: Feature 3 - replaced busy waiting with a counting semaphore

**Details**:
- Imported `Semaphore` and declared `readyCount = new Semaphore(0)` in `ReadyQueue`
- `add()` calls `release()` after the queue lock is released
- Added `waitForProcess()` (`acquire()`) and `wakeUpAll(cpus)` (`release(cpus)`)
- Rewrote the CPU loop: `acquire()` first, stop if all processes are completed, no more `Thread.sleep(20)` polling
- The CPU that sees the last process complete calls `wakeUpAll(totalCPUs)` so the blocked CPUs can stop
- Ran 5 times: all four verification lines ✔, busy-waiting polls 0, program ends by itself in about 6 seconds
- Committed and pushed Feature 3

**Challenges**: I had to understand why the program would hang without the shutdown signal, and the CPU loop was long to replace without deleting the closing braces of the method and class.

**Solution**: I traced the end of the run: after the last process finishes, the other CPU is blocked in `acquire()` and nobody calls `add()` again, so it needs the extra permits. I checked that the method and class braces were still there before running.

**Time spent**: 1 hour 30 minutes

---

### Entry 5 - November 12, 2026, 4:20 AM
**What I did**: Started the documentation in MY_WORK.md

**Details**:
- Filled the Student Information table
- Wrote development log entries 1 to 5 from my notes and commit history
- Compared the starter output (23/24, 11/12, 52499, 987 polls) with my final output (all ✔) to prepare Question 1

**Challenges**: Remembering the exact details of each session.

**Solution**: I used my saved output files and the dates on my GitHub commit history.

**Time spent**: 40 minutes

---

### Entry 6 - November 14, 2026, 6:20 PM
**What I did**: Completed the reflection, the technical answers and the summary, then recorded the video

**Details**:
- Wrote the 4 reflection answers and the 4 technical answers using my own starter output (23/24, 11/12, 52499/53380, 987 polls) and my final output (all ✔)
- Pasted both verification blocks in Question 1 and filled the critical-sections table in Question 2
- Prepared and recorded the 2-3 minute demo video in VS Code and uploaded it with a public link

**Challenges**: Explaining the lost update and the shutdown signal clearly and in a short time for the video.

**Solution**: I used my own numbers and the `contextSwitchCount` example with `RaceWindow.pause()`, and I practiced the explanation before recording.

**Time spent**: 1 hour 30 minutes

---

## Development Log Summary

**Total time spent on assignment**: about 7 hours

**Most challenging part**: The clean shutdown of Feature 3: understanding why a CPU blocked in `acquire()` would wait forever after the last process finished.

**Most interesting learning**: A single `RaceWindow.pause()` of 1 ms between a read and a write was enough to lose updates and even lose a whole process (P9) in my starter run.

**What I would do differently next time**: Start earlier and spread the work over more days, and write each log entry right after the session instead of from my notes.

---

# Part B: Reflection (0.5 mark)

## Question 1: What did you learn about synchronization?

**Your Answer:** *(5-7 sentences)*

I learned that a simple line like `count++` is not one step but three: read, modify and write, and another thread can run between them. When I ran the starter with my ID, both CPUs picked P1 at the same time and process P9 was lost, so the verification showed 23 context switches instead of 24 and 11 completed processes instead of 12. I learned that every piece of code that touches shared data is a critical section and must be protected with mutual exclusion. Using `ReentrantLock` with `lock()` and `unlock()` inside `finally` made sure the lock is always released, even if an exception happens or a `return` is inside the `try`. I also learned that a counting semaphore is not only a lock: its value can count real resources, here the processes waiting in the ready queue. What surprised me most was that the same program gave different wrong results in different runs, which shows why race conditions are so hard to find.

## Question 2: What was the most challenging part of this assignment?

**Your Answer:** *(5-7 sentences)*

The most challenging part was Feature 3, especially the shutdown of the CPUs. Replacing the polling loop with `acquire()` was easy to write, but I first did not understand why the program could hang at the end. After the last process finishes, the other CPU is already blocked in `acquire()`, and no one will ever call `add()` again, so it waits forever. This is a situation where the program does not crash but simply never ends, and the watchdog is the only thing that stops it. I also had to be careful to check "completed == total" right after waking up, so a CPU woken by the shutdown signal stops instead of trying to poll an empty queue. On the practical side, replacing a long loop without deleting the closing braces of the method and the class also needed attention.

## Question 3: How did you overcome the challenges you faced?

**Your Answer:** *(5-7 sentences)*

I worked one feature at a time and ran the program after each one, comparing the verification block with the previous run. After Feature 1 the exceptions disappeared but the context switches were still 23/24, which showed me that the counters were a separate problem. After Feature 2 the first three lines were always correct and only the busy-waiting polls (5) were still wrong, so I knew exactly what Feature 3 had to fix. To understand the shutdown, I followed the end of the run step by step and asked myself which thread could still call `release()`. When I edited the code, I worked from the bottom of the class to the top so the line numbers did not change, and I checked that the error count in VS Code was 0 before running. Finally, I ran the final version 5 times and all four lines were ✔ every time.

## Question 4: Where can synchronization concepts be applied in real-world applications?

**Your Answer:** *(5-7 sentences)*

In a banking system, two transfers from the same account at the same time are a read-modify-write on the balance, exactly like `contextSwitchCount`, so the balance update must be a critical section protected by a lock. In ticket or seat booking, two users can see the same free seat, like my two CPUs that both picked P1, so checking and reserving the seat must be one atomic step. A print queue or a job queue in a server is the same idea as my ready queue: producers add jobs, workers take them, and a semaphore lets workers sleep when there is no job instead of busy waiting. A web server with a fixed number of database connections can use a counting semaphore initialized to the number of connections. Databases also use locks to keep data consistent when many users write at the same time. In all these cases, the choice of lock granularity matters: one big lock is simple but slow, while finer locks allow more parallel work.

### Optional: What would you like to learn more about?

How databases and operating systems detect and recover from deadlocks, and how lock-free structures like `AtomicInteger` work internally.

### Optional: How confident do you feel about synchronization concepts now?

Intermediate. I understand race conditions, mutex locks with try/finally, and counting semaphores well. I need more practice with deadlock prevention and with monitors and condition variables.

### Optional: Feedback on the assignment

The `RaceWindow` and the verification block made the bugs visible and easy to check, which helped me understand the theory from the slides.

---

# Part C: Technical Answers (0.5 mark)

## Question 1: Race Condition in Your Own Output

**Your Answer:** *(3-5 sentences)*

In my starter run (ID 445050007, 12 processes, quantum 3000 ms, 2 CPUs), three values were wrong: context switches 23 instead of 24 (1 missing), completed processes 11 instead of 12 (1 missing), and total service time 52499 instead of 53380 (881 ms missing), plus 987 busy-waiting polls. Both CPUs picked P1 at the same time, CPU-2 crashed with `IllegalThreadStateException`, and process P9 was lost, so CPU-1 kept polling the empty queue until the watchdog stopped the program after 31 s. After I fixed only the queue (Feature 1), context switches was still 23/24 because of a lost update on `contextSwitchCount`, which Feature 2 fixed. On a real machine the same bug can happen without `RaceWindow` because the OS scheduler can preempt a thread between the read and the write at any time. It is hard to detect because that window is only a few nanoseconds, so the bug appears rarely and randomly and usually not when you test.

Verification block of the **original starter**:
```
⛔ WATCHDOG: the simulation did not finish (31 s). A process was lost, or a CPU is blocked forever, or the 'completed' counter lost an update.

═══ VERIFICATION (expected values are computed from YOUR seed) ═══
  Context switches (quanta executed)     expected 24       observed 23       ✘ MISMATCH
  Completed processes                    expected 12       observed 11       ✘ MISMATCH
  Total service time (ms)                expected 53380    observed 52499    ✘ MISMATCH
  Busy-waiting polls (must be 0)         expected 0        observed 987      ✘ MISMATCH
  ✘ At least one check failed (see the ✘ lines above): a race condition or busy waiting is still present.
```

Verification block of **my final version**:
```
═══ VERIFICATION (expected values are computed from YOUR seed) ═══
  Context switches (quanta executed)     expected 24       observed 24       ✔
  Completed processes                    expected 12       observed 12       ✔
  Total service time (ms)                expected 53380    observed 53380    ✔
  Busy-waiting polls (must be 0)         expected 0        observed 0        ✔
  ✔ All shared values are consistent.
```

**Explanation of the timeline:**
1. CPU-1's process thread reads `contextSwitchCount` = 5 into `tmp`.
2. `RaceWindow.pause()` puts it to sleep for 1 ms before the write.
3. CPU-2's process thread reads `contextSwitchCount`, which is still 5.
4. CPU-1 writes `tmp + 1` = 6.
5. CPU-2 writes `tmp + 1` = 6.
6. Two quanta started but the counter only went from 5 to 6: one increment is lost. This is why my run showed 23 instead of 24.

## Question 2: Critical Sections and Lock Granularity

**Your Answer:** *(3-5 sentences)*

I used one lock per statistic (`contextSwitchLock`, `completedLock`, `serviceTimeLock`) because the three counters are independent: updating `contextSwitchCount` has no reason to block a thread updating `totalServiceTime`. The trade-off is more parallelism but more code and three locks to manage; one single lock would be simpler but would make all updates wait for each other. Each method takes only one lock, so these locks cannot cause a deadlock. The ready queue uses a different lock (`queueLock`) because it is different data; with one shared lock, a CPU working on the queue would block all statistics updates for no reason. Mutual exclusion is guaranteed because only the thread holding the lock can run the read-modify-write, and every `unlock()` is in `finally`, which also gives progress since no thread keeps a lock while waiting for something else. A default `ReentrantLock` is not fair, so bounded waiting is not strictly guaranteed (a thread could in theory be overtaken many times), but my critical sections are very short (about 1 ms), and `new ReentrantLock(true)` would give a fair FIFO order if needed.

| Critical section (variable / method) | Lock used | Why it needs protection |
|---|---|---|
| `ReadyQueue.add()` (`list`, `map`) | `queueLock` | Two CPUs re-adding processes at the same time can corrupt the LinkedList and HashMap |
| `ReadyQueue.poll()` | `queueLock` | Reading the head and removing it must be one step, otherwise two CPUs pick the same process (P1 in my run) |
| `ReadyQueue.processOf()` | `queueLock` | Reading the HashMap while another CPU writes to it is not safe |
| `ReadyQueue.snapshot()` | `queueLock` | Iterating the list while it changes causes `ConcurrentModificationException` |
| `incrementContextSwitch()` / `getContextSwitchCount()` | `contextSwitchLock` | Read-modify-write on `contextSwitchCount` loses updates (23 instead of 24) |
| `incrementCompletedProcess()` / `getCompletedProcessCount()` | `completedLock` | A lost update makes the count never reach 12, so the CPUs never stop |
| `addServiceTime()` / `getTotalServiceTime()` | `serviceTimeLock` | Read-modify-write on `totalServiceTime` loses milliseconds |

## Question 3: Busy Waiting vs Semaphore

**Your Answer:** *(3-5 sentences)*

In the starter, a CPU that found the queue empty slept 20 ms and polled again in a loop; in my starter run this happened 987 times because CPU-1 kept checking an empty queue for 31 s after P9 was lost, wasting CPU time. In my version, `readyCount` is a counting semaphore whose value is the number of processes waiting in the ready queue. Its initial value is 0 because the queue is empty when it is created, so a CPU must block in `acquire()` until `add()` calls `release()`; after the 12 initial `add()` calls its value is 12. A CPU that waits in `acquire()` is blocked, not running, so busy-waiting polls became 0. When the last process completes, the CPU that sees it calls `release(totalCPUs)` (2 permits in my case) so the CPUs blocked in `acquire()` wake up, see completed == total and stop; without it they would wait forever and the watchdog would stop the program.

## Question 4: Classical Problems and Deadlock

**Your Answer:** *(3-5 sentences)*

**Classical problem and roles**:
It is the Producer-Consumer (bounded-buffer) problem. The producers are the main thread, which adds the 12 initial processes, and the CPUs themselves when they put an unfinished process back with `add()`. The consumers are the CPUs, which take processes from the ready queue with `poll()`.

**Semaphores for a bounded queue (name and initial value)**:
`mutex` = 1 (mutual exclusion on the queue), `empty` = K (number of free slots), `full` = 0 (number of processes in the queue).

**Deadlock scenario and prevention**:
If a producer did `wait(mutex)` before `wait(empty)` while the queue is full, it would block on `empty` while holding the mutex. A consumer then needs the mutex to remove a process and free a slot, so it also blocks, and both wait forever: a deadlock. To prevent it, I would break the hold-and-wait condition by always waiting on `empty` (or `full`) before taking the mutex, as in the slides. If two locks are needed, using the same global order for every thread breaks the circular wait condition. This is also why in my code a CPU calls `acquire()` without holding `queueLock`.

## Summary

**Key concepts I understood through these questions:**
1. A read-modify-write on shared data is a critical section, and a lost update happens when two threads read the same value before writing.
2. A mutex lock gives mutual exclusion, and `unlock()` must be in `finally` so the lock is always released.
3. A counting semaphore can count resources and lets threads block instead of busy waiting.

**Concepts I need to study more:**
1. Deadlock prevention and avoidance (Banker's algorithm).
2. Monitors and condition variables.

---

# ✅ Final Checklist (complete before submitting)

> ⚠️ **WARNING:** Go through every line. Blackboard does not accept submissions after the deadline, which is **November 14, 2026**.

**Repository**
- [ ] Repository is **PUBLIC** (Settings → Danger Zone → Visibility)
- [ ] Repository is renamed to `OS-Assignment3-YourFirstName-YourLastName`
- [ ] GitHub account uses the university email (`@std.psau.edu.sa`)

**Code**
- [ ] Student ID is set in `SchedulerSimulationSync.java` (line 304)
- [ ] My code is based **only** on the starter of this repository (nothing copied from previous assignments)
- [ ] Code compiles and runs with no errors, and terminates by itself (no `⛔ WATCHDOG`)
- [ ] Feature 1 (ready queue lock), Feature 2 (statistics locks) and Feature 3 (semaphore, no busy waiting) all work
- [ ] **The four verification lines are ✔ in 5 consecutive runs**
- [ ] Every lock is released in a `finally` block
- [ ] `RaceWindow`, `Config`, the verification block and the watchdog are **unchanged**
- [ ] Each feature has clear comments

**Commits**
- [ ] **At least 4 meaningful commits, ideally 7 or more**
- [ ] **One commit per feature**
- [ ] Commits are spread over **different dates** (not all in the last hour)
- [ ] Everything is **pushed** to GitHub

**This file (`MY_WORK.md`)**
- [ ] Full name and student ID filled in at the top
- [ ] Development log has **5+ entries** on different dates
- [ ] Reflection: 4 questions, 5-7 sentences each
- [ ] Technical answers: 4 questions, 3-5 sentences each, with examples from **your** output (starter output **and** final output pasted in Question 1)
- [ ] No `[...]` placeholders left
- [ ] No section headers deleted

**Video**
- [ ] 2-3 minutes long, named `StudentID_Assignment3_Demo.mp4`
- [ ] Shows your name, ID, repository, 3 features (and your lock granularity choice), IDE execution with the verification block, one synchronization concept, and commit history
- [ ] Link is **public** (tested in an incognito window) and pasted in the **Video Link** section above

**Blackboard**
- [ ] Submit **only** the link to your public GitHub repository

> 🎯 **Good luck!** Start early, commit regularly, and make sure you can explain every line you submit.
