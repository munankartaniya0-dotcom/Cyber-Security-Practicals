# DVWA Security Practicals

This repository contains screenshots and the full practical documentation for the DVWA (Damn Vulnerable Web Application) exercises demonstrated in a controlled local lab.

## Project contents

- `Screenshots/` – screenshots extracted from the practical documentation, named by practical.
- `Documentation/DVWA_All_Successful_Practicals_Complete_Documentation.docx` – full report with aims, observations, screenshot evidence, results, and conclusion.

## Lab and method

The work was carried out in the DVWA lab. For each exercise, the corresponding DVWA module/page was opened, the feature was tested as described below, and the visible result was recorded as screenshot evidence. These exercises are for learning and testing in an authorised local lab only.

## Practicals and how they were tested

### 1. Authorisation Bypass
- **Aim:** Check whether a user without admin privileges could access an administration-only user-management feature.
- **Method:** Opened the Authorisation Bypass module and inspected the user-management/update interface that was labelled as admin-only.
- **Observation/result:** The user-management interface was accessible in the controlled DVWA lab, demonstrating an authorisation-control weakness.
- **Evidence:** `Screenshots/01_Authorisation_Bypass.png`

### 2. DOM-Based Cross-Site Scripting (XSS)
- **Aim:** Examine client-side DOM-based XSS behaviour on the language-selection page.
- **Method:** Opened the DOM Based XSS module and tested the language-selection functionality.
- **Observation/result:** The page was opened and tested during the session; the screenshot records the module and its visible output.
- **Evidence:** `Screenshots/02_DOM_Based_XSS.png`

### 3. Stored Cross-Site Scripting (XSS)
- **Aim:** Test whether submitted content could persist and execute through the guestbook/comment feature.
- **Method:** Used the Stored XSS page and entered a script payload in the Name field in the local lab.
- **Observation/result:** A browser alert was displayed, demonstrating the stored-XSS behaviour in the lab.
- **Evidence:** `Screenshots/03_Stored_XSS.png`

### 4. Content Security Policy (CSP) Bypass
- **Aim:** Study the CSP configuration and the DVWA CSP Bypass exercise.
- **Method:** Opened the CSP Bypass page and inspected the page and browser Network/Inspector information.
- **Observation/result:** The exercise was completed as part of the DVWA session. The screenshot shows the module and browser inspection evidence.
- **Evidence:** `Screenshots/04_CSP_Bypass.png`

### 5. JavaScript Attacks
- **Aim:** Test the JavaScript Attacks challenge in DVWA.
- **Method:** Opened the JavaScript Attacks module and exercised its user-manager functionality.
- **Observation/result:** A successful save message was observed during the session.
- **Evidence:** `Screenshots/05_JavaScript_Attacks.png`

### 6. Open HTTP Redirect
- **Aim:** Check whether a redirect destination was accepted without adequate validation.
- **Method:** Tested the DVWA vulnerable redirect endpoint using its redirect parameter.
- **Observation/result:** The browser redirected to `example.com`, confirming the open-redirect behaviour in the lab.
- **Evidence:** `Screenshots/06_Open_HTTP_Redirect.png`

### 7. Cryptography Problems
- **Aim:** Decode an intercepted DVWA message and use the recovered value in the provided login form.
- **Method:** Decoded the intercepted message and entered the recovered value into the exercise's login form.
- **Observation/result:** The page displayed a successful welcome-back message.
- **Evidence:** `Screenshots/07_Cryptography_Problems.png`

### 8. API Security
- **Aim:** Compare API versions and check for sensitive information disclosure.
- **Method:** Requested the DVWA v2 user endpoint and the legacy v1 individual-user endpoints, then compared the returned fields.
- **Observation/result:** The v2 endpoint returned user records with fields such as id, name, and level. The v1 endpoints also exposed password-hash data, confirming a sensitive-information disclosure issue in the legacy endpoint.
- **Evidence:** `Screenshots/08_API_Security.png`

### 9. Brute Force (unsuccessful credential attempt)
- **Aim:** Test the DVWA Brute Force login module.
- **Method:** Submitted a test login attempt for the `admin` username using the test password recorded in the report.
- **Observation/result:** DVWA returned “Username and/or password incorrect.” This was a failed login attempt, **not** a successful password compromise.
- **Evidence:** `Screenshots/09_Brute_Force_Failed_Attempt.png`

## Notes and limitations

- The report documents eight successful vulnerability demonstrations plus one unsuccessful Brute Force login attempt.
- Reflected XSS was also discussed/worked through, but a matching screenshot was not reliably available in the source file set, so it is not included as screenshot evidence here.
- Screenshots were extracted from the supplied DOCX report. They are evidence of the displayed lab session, not independent verification of the application state.
- All testing should be performed only in an authorised lab or on systems for which permission has been granted.

## Suggested GitHub upload

Upload the `README.md`, `Screenshots/` folder, and `Documentation/` folder to your `Cyber-Security-Practicals` repository. Keep the folder names unchanged so the screenshot links in this README remain valid.
