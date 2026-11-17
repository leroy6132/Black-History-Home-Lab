# Week 3 Session 1 — Process management and recovery

**Status:** Reported complete.

## Practice

```bash
sleep 300 &
jobs -l
pgrep -a sleep
ps -C sleep -o pid,ppid,%cpu,%mem,etime,stat,cmd
```

Identify the lab process before terminating it. `jobs` is specific to the current shell; a PID identifies an operating-system process. A job number is not a PID.

`kill PID` normally sends SIGTERM, allowing the process to handle shutdown. `kill -9 PID` sends SIGKILL, which cannot be caught and bypasses application cleanup. `kill %1` targets shell job 1 only if that is the intended job in the current shell.

## Recovery event

During a CPU-load exercise using `yes` redirected to `/dev/null`, the VM became unresponsive. The VM was restarted and login succeeded. Recovery status was reported as “all.” The exact bottleneck and integrity checks were not retained, so CPU saturation is a hypothesis rather than a proven cause.

Do not automatically rerun the unbounded load exercise. Use `sleep` for job-control practice and inspect `top`, `free -h`, and `systemctl --failed` when investigating resource symptoms.

## Checkpoint

Reported Q1 B; Q2 B; explanation that `kill PID` requests termination while `kill -9 PID` forces it. Exact question text and numeric grading unavailable.

**IT connection:** process identification, resource triage, controlled termination, recovery documentation.
