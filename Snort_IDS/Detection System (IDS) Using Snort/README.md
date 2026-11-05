# Practical 6: Snort IDS – ICMP Alert Testing

**Category:** Cyber Security / Intrusion Detection  
**Operating system:** Kali Linux  
**Snort version:** 3.12.2.0  
**Network interface:** `eth0`  
**Local IP:** `10.0.2.15/24`  
**Test target:** `10.0.2.2`  
**Protocol tested:** ICMP

## 1. Aim
To install and configure Snort IDS on Kali Linux, monitor network traffic on `eth0`, create a custom ICMP detection rule, and verify that Snort generates alerts for ICMP traffic.

## 2. Procedure: How the practical was performed

1. **Install Snort.** Snort was installed from the Kali rolling repository. The documentation records Snort 3.12.2.0 and supporting packages as successfully configured.
2. **Identify the network interface.** Run `ip -br addr` to identify the active interface. The interface used in this practical was `eth0`, with IPv4 address `10.0.2.15/24`.
3. **Validate Snort configuration.** The configuration was tested and the supplied evidence records a successful load with zero warnings.
4. **Start passive packet processing.** Snort was run in passive packet-processing mode on `eth0`.
5. **Create a local ICMP rule.** A custom rule was added to `/etc/snort/rules/local.rules`. It used SID `1000001` and the alert message `LOCAL ICMP TEST ALERT`.
6. **Generate test traffic.** A four-packet ping test was sent to `10.0.2.2`. The documented result was 4 packets transmitted, 4 received, and 0% packet loss.
7. **Verify detection.** Snort was run in passive mode with the custom rule loaded. The evidence records alerts for ICMP traffic, including traffic between `10.0.2.15` and `10.0.2.2`.

## 3. Key Evidence
- Snort version: `3.12.2.0`
- Monitoring interface: `eth0`
- Configuration validation: 0 warnings, as recorded in the documentation
- Custom rule SID: `1000001`
- Ping test: 4/4 packets received, 0% packet loss
- Alert message: `LOCAL ICMP TEST ALERT`

## 4. Result
Snort IDS was installed and configured on Kali Linux. The `eth0` interface was monitored in passive mode, a custom ICMP detection rule was validated, and the test ICMP traffic triggered Snort alerts.

## 5. Conclusion
The practical demonstrated a basic IDS workflow: installation, interface identification, configuration validation, local rule creation, generation of test traffic, and alert verification.

## 6. Screenshots and Documentation
- Screenshots extracted from the supplied Word report are in [`Screenshots/`](Screenshots/).
- The original report is included at [`Documentation/Snort_IDS_Documentation.docx`](Documentation/Snort_IDS_Documentation.docx).

## Repository Contents
- `README.md` – aim, environment, procedure, evidence, result, and conclusion
- `Screenshots/` – images extracted from the supplied DOCX
- `Documentation/` – original DOCX report

## Safety Note
Use IDS testing only on systems and networks you own or are authorized to monitor. This README reflects the steps and results recorded in the supplied documentation.
