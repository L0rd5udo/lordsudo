---
layout : page
---

<img src='/Sherlocks/Ore/Ore.png' width="640" height="140">

# HTB Sherlocks - Ore </br> [Difficulty-Medium]

## Description
One of our technical partners are currently managing our AWS infrastructure. We requested the deployment of some technology into the cloud. The solution proposed was an EC2 instance hosting the Grafana application. Not too long after the EC2 was deployed the CPU usage ended up sitting at a continuous 98%+ for a process named "xmrig". Important Information Our organisation's office public facing IP is ```86.5.206.121```, upon the deployment of the application we carried out some basic vulnerability testing and maintenance.

-----
## Questions
- Which CVE lead to the initial compromise of the EC2?
- Please detail all malicious IP addresses used by the threat actor (TA) targeting our organisation.
- Which account to the TA utilise to authenticate to the host OS?
- Which file did the TA modify in order to escalate privileges and run the mining service as "root"?
- Which program did the TA utilise to download the injector.sh script?
- Where was the crypto mining binary & config file initially downloaded to?
- Which program did the TA utilise to download both the crypto mining binary & configuration file?
- We need to confirm the exact time the SOC team began artefact collection as this was not included in the report. They utilise the same public facing IP address as our system administrators in Lincoln.
- Please confirm the password left by the system administrator in some Grafana configuration files.
- What was the mining threads value set to when xmrig was initiated?
- Our CISO is requesting additional details surrounding which mining pool this may have been utilising. Please confirm which (if any) mining pool this the TA utilised.
- We couldn't locate the crypto mining binary and configuration file in the original download location. Where did the TA move them to on the file system?
- We have been unable to forensically recover the "injector.sh" script for analysis. - We believe the TA may have ran a command to prevent us doing recovering the file. - - What command did the TA run?
- How often does the cronjob created by our IT admins run for the script modified by the TA?


-----
## Brainstorming
