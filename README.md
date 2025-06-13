SOC Home Lab: Incident Response, Splunk & Firewall Logging
 Welcome
This project is a handson Security Operations Center (SOC) lab environment, designed to simulate realworld security incidents, improve investigation skills, and build familiarity with tools like Splunk, Sysmon, and host/network firewalls.
Whether you're an aspiring SOC analyst or building a cybersecurity portfolio, this lab helps you demonstrate practical knowledge in a controlled, virtual setting.



  Objectives

 Practice log collection, parsing, and correlation using Splunk
 Learn how to detect and respond to common attacks (phishing, malware, lateral movement)
 Understand and apply Sysmon and Windows firewall logging
 Simulate realworld incident response workflows



  Lab Architecture

  Role;         
Attacker VM Simulate attacks using Kali Linux and Kali tools. The Target VM is a Windows 10 instrumented with sysmon/logs, A universal forwarder etc. Ubuntu is the choice for the Analyst VM, used for running collation,analysis and alerting tools like Splunk.    
A visual diagram of the lab is available in (architecture.png).



 Tools:

 [Splunk Free Trial](https://www.splunk.com/)
 [Sysmon (Sysinternals)](https://learn.microsoft.com/enus/sysinternals/downloads/sysmon)
 Windows Defender Firewall
 [Wireshark](https://www.wireshark.org/)
 [Velociraptor](https://www.velociraptor.app/)
 Universal Forwarder 



  Getting Started 

1. Install VirtualBox or VMware
2. Download ISOs (Kali, Windows 10 or Ubuntu)
3. Create VMs (allocate 2+ CPUs, 4–8GB RAM)
4. Use HostOnly or Internal Networking for safe isolation
5. Instrument the Windows VM:
    Install Sysmon
    Enable and configure firewall logging
6. Install and Configure Splunk on the Analyst VM
7. Forward Logs from the target to Splunk using Universal forwarder or manual upload

Detailed setup instructions are in (setupguide.md)



 Simulated Attacks

Sample attack scenarios for practicing detection and response:                 
      
 Phishing using SET toolkit (Kali) to detect Email activity and payload drop. Credential theft using mimikatz to detect LSASS access, logon events.      
 Lateral movement using PsExec/RDP to view the Firewal and event codes 4624/4672. Data exfiltration using Netcat / FTP to monitor Large data transfers and DNS logs.  
 Malware execution using Test EXE/PowerShell scripts to detect and get alerts on Sysmon ProcessCreate and hashes.    

Full attack simulations are in(investigations/) 



  Dashboards & Detections

 Custom Splunk queries for:

   Sysmon process tree mapping
   Firewall port scanning detection
   Suspicious parentchild process combos

Saved queries and detections can be found in (detections)



 Safety Notes

Use HostOnly or Internal Networking — never connect your lab to the public internet
Take VM snapshots before and after major changes
Do not run malware on your host machine
