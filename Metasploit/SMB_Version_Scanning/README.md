# Practical 3: Metasploit Framework - SMB Service Version Scanning

## Aim
To use the Metasploit Framework to identify SMB protocol versions and related SMB characteristics exposed by the authorized lab target `10.0.2.2`.

## Tools and Environment
- Platform: Kali Linux
- Tool: Metasploit Framework
- Framework version shown: `6.4.99-dev`
- Module: `auxiliary/scanner/smb/smb_version`
- Target: `10.0.2.2`

## Procedure
1. Verify the framework version:
   ```bash
   msfconsole --version
   ```
2. Launch the console and view help:
   ```text
   msfconsole
   help
   ```
3. Search for SMB auxiliary scanner modules:
   ```text
   search type:auxiliary scanner smb
   ```
4. Select the SMB version scanner:
   ```text
   use auxiliary/scanner/smb/smb_version
   ```
5. Display module options:
   ```text
   show options
   ```
6. Set the authorized lab target:
   ```text
   set RHOSTS 10.0.2.2
   ```
7. Run the scanner:
   ```text
   run
   ```

## Observed Result
According to the supplied documentation, the scanner contacted `10.0.2.2` on TCP port 445 and identified SMB versions 2 and 3, with preferred dialect `SMB 3.1.1`. The output also reported LZNT1 and Pattern_V1 compression capabilities, AES-256-GCM encryption capabilities, required SMB signatures, and authentication domain `DESKTOP-K39A4BE`.

The documented host version was `10.0.26100`, reported by Metasploit as likely Windows 11 version 24H2 / Windows Server 2025.

## Result
The practical demonstrated the use of a Metasploit auxiliary scanner to identify SMB protocol versions and related service characteristics.

## Scope and Safety Note
This practical documents service identification only. The supplied screenshots do not show a successful exploit, Meterpreter session, reverse shell, or post-exploitation activity. Run scans only against systems you own or are explicitly authorized to test.

## Repository Structure
```text
Metasploit-SMB-Version-Scanning/
├── README.md
├── Screenshots/
│   └── Metasploit_SMB_Scanning_Screenshot_01...
└── Documentation/
    └── Metasploit_Documentation.docx
```

## Evidence
Screenshots extracted from the supplied DOCX are stored in `Screenshots/`. The original documentation is preserved in `Documentation/`.
