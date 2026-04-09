SSH Brute Force Detection using Splunk
Project Overview
This project demonstrates detection of SSH brute force attacks using Splunk SIEM by analyzing authentication logs and identifying suspicious login behavior.
Tools Used
Splunk SIEM
Kali Linux (Attack Simulation)
SPL (Search Processing Language)
Objective
To detect brute force attacks by identifying repeated failed SSH login attempts and analyzing attacker behavior.
 Attack Simulation
A brute force attack was simulated using Kali Linux (Hydra tool) to generate multiple failed SSH login attempts against a target system. These events were captured in authentication logs and analyzed in Splunk.
 Detection Approach
1. Identify Failed Login Attempts
Filtered logs containing authentication failures
Extracted source IP addresses
2. Detect Suspicious IPs
Aggregated failed login attempts by IP
Applied threshold (>10 attempts) to identify attackers
3. Analyze Username Targeting
Identified commonly targeted usernames such as root, admin, and test
4. Monitor Login Trends
Visualized failed login activity over time to identify attack spikes
Key SPL Queries
Detect Brute Force Attackers
index=* "authentication failure"
| rex "rhost=(?<clientip>\d+\.\d+\.\d+\.\d+)"
| stats count by clientip
| where count > 10
| sort -count
Failed Login Trend
index=* "authentication failure"
| timechart count span=1h
Username Targeting
index=* "authentication failure"
| rex "user=(?<user>\w+)"
| stats count by user
| sort -count
