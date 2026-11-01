# Practical Report: Linux Log Analysis

**Platform:** Kali Linux  
**Objective:** Inspect system logs and identify authentication-related events.  
**Commands used:** `ls -lh /var/log/`, `who`, `last -n 10`, `journalctl`, `grep`.

## Procedure
The `/var/log/` directory was inspected. Current and recent login-session information was checked using `who` and `last`. Journal entries were filtered for authentication-related terms.

## Results
Older authentication-failure messages appeared for `lightdm` and `xfce4-screensaver-dialog`. The SSH service query returned no entries. The two matching entries in the current-day filtered query were `sudo` command records associated with running the search, so they are not treated as confirmed failed login attempts.

## Conclusion
Log analysis provides useful evidence for reviewing authentication events. Individual messages should be interpreted with their context and timestamps before making security conclusions.
