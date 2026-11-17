# Linux Infrastructure Home Lab

**Leroy Freeman III · Help desk and systems administration portfolio**

An Ubuntu Server lab in Oracle VirtualBox on a Windows host. I use a Black History Archive as the practical setting for learning Linux administration: controlling access, understanding networking, managing services, and investigating faults.

## Demonstrated work

- Practiced Linux CLI operations, user/group management, ownership, and permissions.
- Examined IPv4 addressing, routes, NAT, and DNS troubleshooting.
- Monitored processes, studied termination signals, and recovered after a VM freeze.
- Installed SSH, checked cron, and observed an active and enabled `ssh.socket`.
- Served a custom NGINX page and investigated an apparent content-delivery problem using HTTP responses, permissions, and logs.

These are foundational lab exercises, not production administration experience. Results below are based on my reported lab work; this repository does not contain an automated deployment or a live server export.

## Start here

| Document | Purpose |
| --- | --- |
| [Environment](docs/environment.md) | VM, networking, and known configuration |
| [Progress](docs/progress.md) | Completed work and open verification items |
| [Command reference](docs/commands.md) | Commands, explanations, and interpretation |
| [Networking concepts](docs/networking.md) | NAT, DNS, gateways, and loopback |
| [Skills matrix](docs/skills-matrix.md) | Evidence mapped to IT work |
| [Lab sessions](labs/README.md) | Session write-ups |
| [INC-001](incidents/INC-001-nginx-content.md) | NGINX investigation and resolution |
| [Configuration examples](configs/README.md) | Illustrative NGINX configuration and HTML |
| [Evidence](evidence/README.md) | How to add sanitized results |
| [Next steps](docs/roadmap.md) | Suggested future exercises |
| [GitHub setup](docs/github-setup.md) | Upload and ongoing maintenance |

## Repository layout

| Path | Contents |
| --- | --- |
| `docs/` | Environment, concepts, command reference, progress, career mapping |
| `labs/` | Completed and in-progress session records |
| `incidents/` | Symptoms, hypotheses, tests, findings, and prevention |
| `configs/` | Clearly labeled example configuration files |
| `evidence/` | Future sanitized screenshots and command output |
| `templates/` | Reusable session and incident templates |
| `.github/ISSUE_TEMPLATE/` | Follow-up task template |

## Accuracy and evidence

**Reported** means I described the result during the lab. **Recorded context** means a detail appeared in earlier lab guidance or summaries and needs comparison against the VM. **Example** means a reference file reconstructed for this repository. **Planned** means work still to do. No original VM configuration files or screenshots are bundled, and no checkpoint grade is invented.

Last compiled: November 17, 2026. Read [progress](docs/progress.md) before interpreting an exercise as fully verified.
