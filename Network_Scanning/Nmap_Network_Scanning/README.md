# Network Scanning Using Nmap

## Aim
To perform network scanning using Nmap and demonstrate host discovery, port scanning, service and version detection, operating-system detection, NSE script scanning, firewall detection, and scan-report generation.

## Tools and Environment
- Platform: Kali Linux
- Tool: Nmap 7.95
- Authorized local lab target: `10.0.2.2`

## Practical Steps

### 1. Verify Nmap
```bash
nmap --version
```
The documentation records Nmap version 7.95.

### 2. Host Discovery
```bash
nmap -sn 10.0.2.0/24
```
The lab scan identified three active hosts: `10.0.2.2`, `10.0.2.3`, and `10.0.2.15`.

### 3. Port Scanning
```bash
nmap 10.0.2.2
```
The documentation reports open TCP ports including 135, 445, 2968, and 8090.

### 4. Service and Version Detection
```bash
nmap -sV 10.0.2.2
```
The result identified Microsoft Windows RPC on port 135 and provided additional service/OS information.

### 5. OS Detection
```bash
sudo nmap -O 10.0.2.2
```
Nmap reported that the OS result may be unreliable because the target did not provide enough information for a confident match.

### 6. NSE Script Scanning
```bash
sudo nmap -sC 10.0.2.2
```
The result included SMB2 security-mode and SMB2 time information.

### 7. Firewall Detection
```bash
sudo nmap -sA 10.0.2.2
```
The ACK scan reported scanned ports as unfiltered (reset), providing information about packet-filtering behavior.

### 8. Save a Scan Report
```bash
nmap -sV 10.0.2.2 -oN nmap_scan_report.txt
```
The `-oN` option saves scan output in normal text format.

## Result
The supplied documentation records host discovery, port scanning, service/version detection, OS detection, NSE script scanning, firewall detection, and normal-format scan-report generation in the authorized local lab.

## Safety
Only scan systems and networks you own or have explicit permission to test. The target documented for this exercise is the local lab target `10.0.2.2`.

## Repository Structure
```text
Nmap-Network-Scanning/
├── README.md
├── Screenshots/
│   └── Nmap_Network_Scanning_Screenshot_01...
└── Documentation/
    └── Nmap_Practical_Documentation.docx
```

## Evidence
Screenshots extracted from the supplied DOCX are in `Screenshots/`. The original practical documentation is preserved in `Documentation/`.
