# Week 3 Session 2 — Linux services

**Status:** In progress / partially evidenced.

## Reported results

- SSH was installed after an initial missing-service result.
- `cron` was active and running.
- `ssh.socket` was **active** and **enabled**.

The later installation report supersedes the earlier “Unit ssh.service could not be found” observation. An active cron service does not establish that a scheduled job has been created or tested.

## Interpretation

An active socket unit listens for connections and may activate its associated service on demand. `ssh.service` does not have to remain active in every socket-activated configuration. Enabled describes startup integration; active describes current runtime state. Neither proves a remote login succeeds.

```bash
systemctl status ssh.socket --no-pager
systemctl is-enabled ssh.socket
systemctl status ssh.service --no-pager
systemctl status cron --no-pager
sudo ss -lntp
journalctl -u ssh.socket -u ssh.service -n 30 --no-pager
```

## Remaining checkpoint

Record which unit owns the listening socket, confirm the intended SSH port, and perform an authorized test login. If the proposed host forward exists, a Windows example is `ssh -p 2222 USERNAME@127.0.0.1`, replacing USERNAME with an actual VM account.

**IT connection:** service-state inspection, startup behavior, and remote-access troubleshooting.
