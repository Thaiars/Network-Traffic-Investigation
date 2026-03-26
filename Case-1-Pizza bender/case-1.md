- Source: malware-traffic-analysis.net - Pizza-Bender
- Day: 2020-08-21

# Victim
IP: 10.8.21.163

## Key Findings
- Suspicious DNS: ubbifeder.cyou → 89.44.9.186
- TLS certificate: self-signed, issued to "localhost"
  by "Internet Widgits Pty Ltd"
- Certificate created: 2020-08-20 (1 day before infection)
- Traffic pattern: C2 → Victim (download payload)
- Total packets to C2: ~2200

## IOCs
| Type   | Value                    |
|--------|--------------------------|
| Domain | ubbifeder.cyou           |
| IP     | 89.44.9.186              |

## MITRE ATT&CK Mapping
- T1071.001 - Application Layer Protocol: Web Protocols
- T1573.002 - Encrypted Channel: Asymmetric Cryptography
- T1105 - Ingress Tool Transfer

## Conclusion
IP 10.8.21.163 was compromise, establish C2 channel to 89.44.9.186 via TLS using a self-signed certificate.
C2 server downloaded payload to victim machine.
Severity: High.
Next step: isolate machine , check process list at the time of infection, and identify persistence mechanism.