# NMAP_Practicals <br></br>
***NMAP Practical using different swithces.*** <br></br>
**1. Task 1: Scan a Single Host** 
</br>- Nmap to scan the host scanme.nmap.org.
</br>- Determine the open ports on the target host.
</br>***ANS: nmap scanme.nmap.org/(any IP add)***<br></br>
**2. Task 2: Scan Multiple Hosts** 

</br>- Scan the hosts scanme.nmap.org and example.com.
</br>- Determine the open ports on each of the target host
</br> ***ANS: nmap 92.184.215.14 45.33.32.156***
<br></br>
**3. Task 3: Scan Specific Ports**
</br>- Scan the host scanme.nmap.org, but only scan ports 22, 80, and 443.
</br>- Record the status (open/closed) of these specific ports.
</br>***ANS: nmap -p22,80,443 scanme.nmap.org***
<br></br>
**4. Task 4: Scan a Range of IP Addresses**
</br>- Scan the IP range 192.168.1.1-20.
</br>- Identify any hosts with open ports within this range 
</br>***ANS: nmap 192.168.1.1-20***
<br></br>
**5. Task 5: Perform Aggressive Scan**
</br>- Perform an aggressive scan (-A option) on the host scanme.nmap.org.
</br>- Gather detailed information about the target host, including OS detection and service versions.
</br>***ANS: nmap -A scanme.nmap.org***
<br></br>
**6. Task 6: Scan UDP Ports (Scanning UDP port takes too much time, so relax)** 
</br>- Scan the host scanme.nmap.org for open UDP ports.
</br>- Record any open UDP ports found during the scan. 
</br>***ANS: nmap -sU scanme.nmap.org***
<br></br>
**7. Task 7: Perform OS Detection**
</br>- Scan the host scanme.nmap.org and attempt to detect the operating system running on the target. 
</br>***ANS: nmap -O scanme.nmap.org***
<br></br>
**8. Task 8: Scan with Service Version Detection** 
</br>- Scan the host scanme.nmap.org with service version detection (-sV option). 
</br>***ANS: nmap -sV scanme.nmap.org***
<br></br>
**9. Task 9: Scan for Vulnerabilities**
</br>- Perform a vulnerability scan (--script vulners) on the host scanme.nmap.org.
</br>- Identify any known vulnerabilities present on the target system 
</br>***ANS: nmap -sV -p20-8080 --script vulners scanme.nmap.org***
</br> NSE script vulners.com API to provide information about system that may be present in a targeted system <br></br>

***Questions***? <br></br>

**1. What is the difference between TCP and UDP port scanning?** </br>
**Answer:** The main difference between TCP and UDP port scanning is the purpose of each:
</br>TCP port scanning: Helps identify and prevent potential network security attacks.
</br>UDP port scanning: Helps discover services running on a target system, especially those that may not respond to traditional TCP scans.
</br>Here are some other differences between TCP and UDP: 
</br>Connection type
</br>TCP is a connection-oriented protocol, while UDP is a connectionless protocol.
</br>Speed
</br>UDP is faster than TCP because it doesn't require additional responses from the receiver.
</br>Data integrity
</br>TCP only transmits complete sets of data packets, while UDP transmits whatever it can, even if some packets are lost.
</br>Security
</br>TCP transmissions are generally easier to keep secure than those sent via UDP.
</br>Use cases
</br>TCP is better for direct communication, like email, web browsing, or transferring files. UDP is better for broadcasting and live streaming. <br></br>

**2. How does Nmap determine the operating system running on a target host?**</br>
**Answer:** Nmap (Network Mapper) uses TCP/IP stack fingerprinting to remotely detect the operating system (OS) on a target host:
</br>1. Send probes: Nmap sends a series of TCP and UDP packets to the target host.
</br>2. Analyse responses: Nmap examines the responses from the target host.
</br>3. Compare to database: Nmap compares the responses to its database of known OS fingerprints.
</br>4. Print results: If there is a match, Nmap prints out the OS details.
</br>Nmap can use either active or passive fingerprinting to identify the OS:
</br>• Active fingerprinting:
</br>Nmap sends packets to the target host and observes how it responds.
</br>• Passive fingerprinting:
</br>Nmap observes the packets the target sends during regular communication.
</br>Nmap can be useful for determining the vulnerability of a target host, tailoring exploits, and detecting unauthorized devices.
</br>To enable OS detection in Nmap, you can use the -O option. <br></br>

**3. Why is it important to perform a vulnerability scan on target hosts?**
**Answer:** Vulnerability scans are important for a number of reasons, including:
</br>• Prioritizing patches
</br>Vulnerability scans identify the most critical vulnerabilities to focus on first, based on their potential impact, severity, and exploitability. This helps organizations prioritize their patch management efforts.
</br>• Mitigating risk
</br>Vulnerability scans help detect security risks like unpatched software, broken authentication, and security misconfigurations. This can help prevent costly data breaches and malware attacks.
</br>• Industry compliance
</br>Many industries, including those with HIPAA and SOX compliance, are required to regularly perform vulnerability assessments.
</br>• Cybersecurity insurance
</br>A business's cybersecurity insurance may require vulnerability assessments, regardless of industry.
</br>• Staying ahead of hackers
</br>Cyber criminals also have access to vulnerability scanning tools, so it's important to perform scans before they do.
</br>• Remediation
</br>Once vulnerabilities are discovered, they need to be fixed. Remediation is generally preferred over mitigation, which is a temporary solution that could lead to future threats.
</br>• Automation
</br>Vulnerability scans can be scheduled and automated to run continuously in the background, reducing manual effort. <br></br>

**4. What are the potential risks associated with aggressive scanning?**</br>
**Answer:** Nmap’s aggressive scan (-A) option can increase the risk of detection because it’s more intrusive and send out more probes than a regular scan, and are more likely to be detected during a security audit.
</br>• Intrusiveness:
</br>Aggressive scans are very intrusive and CPU intensive.
</br>• Detection:
</br>Aggressive scans are more likely to be detected because they send more probes.
</br>• False negatives:
</br>Aggressive scans sometimes give false negatives.
</br>• Custom TCP fingerprints:
</br>Aggressive scans can sometimes provide a custom TCP fingerprint that can be difficult to decode. <br></br>

**5. How can Nmap scan results be useful for network administrators in securing their networks?**</br>
**Answer:** Network administrators can use Nmap scan results to secure their networks in several ways, Including
</br>• Identifying Vulnerabilities:
</br>Nmap scan for open ports and services running on them, which can help identify systems that may be vulnerable to attack.
</br>• Network Mapping:
</br>Nmap can create network maps that show the structure of a network, including connected devices, firewalls and routers.
</br>• Security Audits:
</br>Nmap can be used to assess a network's security by identifying potential entry points and weaknesses that malicious actors could exploit.
</br>• Troubleshooting
</br>Nmap can help diagnose network issues and connectivity problems by scanning a network and checking which services are running.
</br>• Operating system detection
</br>Nmap can identify the operating systems running on remote hosts by analyzing network responses.
</br>• Service version detection
</br>Nmap can probe open ports to determine the type and version of services running on them.
</br>• Scripting and automation
</br>Nmap's scripting engine allows users to write custom scripts to perform specialized security checks and automate network scanning tasks.
<br></br> <br></br>
Thank You.
<br></br>
**END**
