# Week 2 — Users, groups, and permissions

**Status:** Practiced; final access configuration needs verification.

## Recorded work

- Worked with `archiveadmin` and an archive-reader group.
- Encountered “not in the sudoers file” while running `apt update` as `archiveadmin`.
- A prior screenshot interpretation recorded directory mode `drwxr-x---` with owner/group `archiveadmin:archiveadmin`, while `researcher` belonged to `archivereader`.
- Changing the directory group to `archivereader` was suggested. A successful final change and access tests are not retained.

## Reasoning

Group membership only grants the directory's group permissions when the directory group matches a group in the user's session. Mode `750` gives the owner read/write/traverse, the group read/traverse, and others no access. Directory read lists names; execute permits traversal. Individual files need appropriate permissions too.

A sudo error concerns administrative authorization; it is separate from access to the archive. Membership changes may require a fresh login. Do not grant sudo to a read-only archive user solely to make an administrative command work.

## Verify before changing anything

```bash
id archiveadmin
id researcher
getent group archivereader
ls -ld /srv/black-history-archive
namei -l /srv/black-history-archive
sudo -l
```

From the intended reader's login, test listing and reading an existing sample file, then test creating a disposable file only within the lab directory. Record expected and actual results. Do not record the group mismatch as fixed until these checks pass.

**IT connection:** account troubleshooting, least privilege, and file-access diagnosis.
