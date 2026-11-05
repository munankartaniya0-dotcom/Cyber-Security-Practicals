# Practical 10: Phishing Email Analysis Using a Local Sample

## Aim
To analyze a controlled sample email for phishing and social-engineering indicators by examining email headers, extracting URLs, checking authentication-related headers, and identifying suspicious wording.

## Environment and Tools
- Kali Linux Terminal
- Local sample email: `~/phishing_sample.eml`
- Linux commands: `cat`, `head`, `grep`
- Web browser used only to observe the documentation/example domain

## Procedure
1. Displayed the complete sample email with `cat ~/phishing_sample.eml`.
2. Displayed the first seven lines of the email with `head -n 7 ~/phishing_sample.eml` to inspect the available header fields.
3. Extracted URLs using:
   ```bash
   grep -Eo 'https?://[^ ]+' ~/phishing_sample.eml
   ```
4. Extracted the From, To, Subject, Date, and Message-ID fields using `grep`.
5. Searched for authentication-related headers including `Received`, `Authentication-Results`, `Received-SPF`, `DKIM-Signature`, and ARC headers. These headers were absent from the supplied sample.
6. Searched the message for suspicious wording such as `urgent`, `suspend`, `verify`, `account`, `24 hours`, `click`, and `password`.

## Observations and Findings
- The sender text used the look-alike string `micr0soft-security.example`.
- The subject used urgency: **“Urgent: Your account will be suspended”**.
- The message claimed unusual activity and imposed a 24-hour deadline.
- The recipient was asked to verify the account through a URL.
- Extracted URL: `https://example.com/verify`.
- The sample did not contain the checked authentication-related headers, so the sender could not be independently verified from those headers.

## Result
The controlled sample contains multiple phishing-style indicators: urgency, an account-suspension threat, a verification request, a look-alike sender string, and an embedded URL. The evidence supports treating it as a phishing-style training example.

## Safety Note
This exercise used a local training email and a documentation/example domain. According to the supplied documentation, no real credentials were entered and no real phishing message was sent.

## Repository Structure
```text
Practical-10-Phishing-Email-Analysis/
├── README.md
├── Screenshots/
│   ├── Phishing_Email_Analysis_Screenshot_01...
│   └── ...
└── Documentation/
    └── Practical_10_Phishing_Email_Analysis_Documentation.docx
```

## Evidence
Screenshots extracted from the supplied DOCX are in the `Screenshots/` folder. The original practical documentation is preserved in `Documentation/`.
