# Practical 9: Command Injection – DVWA

**Category:** Web Application Security  
**Application:** Damn Vulnerable Web Application (DVWA)  
**Target:** `127.0.0.1` (localhost)

## 1. Aim
To study and demonstrate the Command Injection vulnerability in DVWA and observe how input filtering differs across Low, Medium, and High security levels.

## 2. Practical overview
The DVWA Command Injection module provides a “Ping a device” form. The user supplies an IP address, which the application incorporates into a system command. In this practical, the normal input `127.0.0.1` was tested at Low, Medium, and High security levels, and the supplied source code was reviewed.

## 3. Procedure: How the practical was performed

1. Open DVWA on the local lab (`127.0.0.1`) and navigate to **Command Injection**.
2. Confirm that the **Ping a device** input field is available.
3. At **Low** security, enter `127.0.0.1` and submit the form. The documentation records a successful ping response.
4. Change the DVWA security level to **Medium**, repeat the normal input test with `127.0.0.1`, and submit. The documentation again records a successful ping response.
5. Change the security level to **High**, repeat the normal input test with `127.0.0.1`, and submit. The documentation records a successful ping response.
6. Review the supplied `medium.php` source. It removes `&&` and `;` using `str_replace()` before concatenating the target into a command passed to `shell_exec()`.
7. Review the supplied `high.php` source. It removes a broader list of shell characters/operators, including `||`, `&`, `;`, `| `, `-`, `$`, parentheses, and backticks, before using `shell_exec()`.

> The supplied report documents normal ping tests and source-code review. It does not document a successful command-injection payload execution, so this README does not claim one.

## 4. Source-code observations

### Medium security
- Reads the user-controlled `ip` parameter.
- Removes `&&` and `;` from the input.
- Passes the remaining target into a command string executed by `shell_exec()`.

### High security
- Trims the user-controlled `ip` parameter.
- Applies a broader blacklist of shell metacharacters/operators.
- Still builds the ping command by concatenating the filtered target into a shell command.

## 5. Observations
- The Command Injection page accepts an IP address and runs a ping operation.
- `127.0.0.1` returned successful ping output at Low, Medium, and High levels.
- Medium and High use different blacklist-based filtering rules.
- The source code shows user-controlled input being concatenated into a shell command.

## 6. Result
The DVWA Command Injection practical was performed. Normal ping execution was verified at Low, Medium, and High security levels, and the supplied source code was reviewed to understand the different filtering mechanisms.

## 7. Conclusion
The practical demonstrates the risk of concatenating user-controlled input directly into operating-system commands. Blacklist filtering may block some characters but is not a substitute for safe command construction and strict input validation.

## 8. Screenshots and documentation
- Extracted screenshots from the supplied Word document are in [`Screenshots/`](Screenshots/).
- The original report is included at [`Documentation/DVWA_Command_Injection_Documentation.docx`](Documentation/DVWA_Command_Injection_Documentation.docx).

## Repository contents
- `README.md` – aim, environment, procedure, observations, result, and conclusion
- `Screenshots/` – images extracted from the supplied documentation
- `Documentation/` – original DOCX report

**Lab safety:** Perform security testing only in your own authorized DVWA lab.
