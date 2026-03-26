# Network-Traffic-Investigation
PCAP analysis using Wireshark to investigate real-world malware traffic sourced from malware-traffic-analysis.net

## Cases
| # | Case | Key Technique | MITRE |
|---|------|--------------|-------|
| 1 | Pizza-Bender | C2 over TLS, self-signed cert | T1071, T1573, T1105 |
| 2 | Quiethub | Malware download + encrypted data exfiltration via HTTP POST | T1105, T1041, T1036, T1132 |


## Tools Used
- Wireshark
- VirusTotal (IOC verification)
