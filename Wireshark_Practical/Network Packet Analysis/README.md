# Practical 7: Wireshark – Network Packet Analysis

**Topics:** Packet capture, ICMP filtering, packet inspection, and Protocol Hierarchy analysis.

## Aim
To capture network packets using Wireshark, filter ICMP traffic, examine packet details, and analyze captured traffic using Protocol Hierarchy Statistics.

## Environment
- Operating system: Kali Linux
- Wireshark version: 4.6.0
- Capture interface: `eth0`
- Source IP shown in the practical: `10.0.2.15`
- Destination IP shown in the practical: `10.0.2.2`
- Protocol tested: ICMP

## Procedure: How the practical was performed

1. **Verify Wireshark installation.** The installed version was checked from the terminal; the documentation records Wireshark 4.6.0.
2. **Select the network interface.** Wireshark was opened and `eth0` was selected for live packet capture.
3. **Start packet capture.** A live capture was started on `eth0`.
4. **Generate ICMP traffic.** Four ping requests were sent to `10.0.2.2`. The recorded ping result was 4 packets transmitted, 4 received, and 0% packet loss.
5. **Filter ICMP packets.** The display filter `icmp` was entered in Wireshark. ICMP Echo Request and Echo Reply packets between `10.0.2.15` and `10.0.2.2` were observed.
6. **Inspect packet details.** A packet was selected and the Frame, Ethernet II, Internet Protocol Version 4, and Internet Control Message Protocol sections were examined.
7. **Analyze protocol hierarchy.** The menu **Statistics → Protocol Hierarchy** was opened. With the ICMP filter active, the hierarchy showed Frame → Ethernet → IPv4 → ICMP. The documentation records 8 displayed filtered packets.

## Observations
- Wireshark captured traffic from `eth0`.
- The `icmp` display filter isolated ICMP traffic.
- ICMP traffic was observed between `10.0.2.15` and `10.0.2.2`.
- Packet details showed Ethernet II, IPv4, and ICMP layers.
- Protocol Hierarchy Statistics showed ICMP under IPv4.

## Result
Wireshark was used to capture and analyze network traffic. ICMP packets were generated using ping, filtered with the `icmp` display filter, inspected at protocol level, and analyzed using Protocol Hierarchy Statistics.

## Screenshots
Extracted images from the supplied Word documentation are in the [`Screenshots/`](Screenshots/) folder. Open the images to review the available evidence.

## Documentation
The original Word report is included at [`Documentation/Wireshark_Documentation.docx`](Documentation/Wireshark_Documentation.docx).

## Repository contents
- `README.md` – aim, environment, procedure, observations, and result
- `Screenshots/` – images extracted from the supplied documentation
- `Documentation/` – original DOCX report

> Note: This README is based on the supplied documentation. It describes the recorded practical steps and results; it does not claim any additional tests beyond those documented.
