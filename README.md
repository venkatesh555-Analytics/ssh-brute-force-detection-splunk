# ssh-brute-force-detection-splunk
Detecting SSH brute force attacks using Splunk SIEM
# SSH Brute Force Detection using Splunk

## Project Overview
This project demonstrates detection of SSH brute force attacks using Splunk SIEM. The analysis identifies malicious IPs attempting unauthorized access through repeated login failures.

---

## Tools Used
- Splunk Enterprise
- SSH Log Data
- SPL (Search Processing Language)

---

## Use Case
Detect brute force attacks by identifying IPs generating multiple authentication failures.

---


---Findings
Multiple IPs performed brute force attacks
High failed login attempts indicate suspicious activity
Common usernames targeted: root, admin, test

Limitation

Successful login logs did not contain IP address, so attack correlation is limited.

Conclusion

This project demonstrates SOC analyst skills:

Log analysis
Threat detection
Splunk dashboard creation
