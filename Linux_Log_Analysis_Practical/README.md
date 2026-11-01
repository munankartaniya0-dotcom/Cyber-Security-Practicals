# Linux Log Analysis Practical

## Objective
Inspect Linux system logs and review authentication-related events using Kali Linux.

## Tools Used
- Kali Linux Terminal
- `journalctl`
- `grep`
- `last`
- `who`

## Practical Steps
1. Listed files and directories under `/var/log/`.
2. Used `who` to view the current logged-in session.
3. Used `last -n 10` to inspect recent login session records.
4. Searched authentication-related messages with `journalctl` and `grep`.
5. Prepared observations in `reports/observations.txt`.

## Findings
- Older authentication-failure messages appeared for `lightdm` and `xfce4-screensaver-dialog`.
- The SSH service query returned `-- No entries --` in the captured output.
- The current-day filtered query returned two matching records. The visible records were `sudo` command records generated while running the search, not confirmed failed login attempts.
- The captured evidence does not establish malicious activity.

## Conclusion
System logs can help investigate login and authentication events. Entries should be checked in context before classifying them as suspicious.

## Evidence Note
The `screenshots/` directory contains screenshots shared during the practical session. They were copied from the conversation for this ZIP; they were not automatically saved by the screenshot utility inside Kali.

## GitHub Upload
Upload the extracted `Linux_Log_Analysis_Practical` folder to your repository. Keep the screenshots and report together.
