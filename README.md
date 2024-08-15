<h1>Splunk Investigation 3</h1>

<h2>Description</h2>
The IT team reported an unknown file, "xxx.exe," in an employee's registry. OSINT suggested it was a legitimate Microsoft file, but its location was suspicious. Using a Splunk query (sourcetype=xmlwineventlog, "xxx.exe"), I found nearly 50,000 Sysmon events, revealing the file's full path (image), affected computer (SourceHostName), internal IP (Sourceip), and user (User). Adding destination port and '|stat count by DestinationIp' showed 16,384 unique destination IPs. The file's SHA256 hash, found in Sysmon EventID 7 logs, was identified as Cerber malware by VirusTotal. A "fortigate_utm" search confirmed FortiGate categorized it as Cerber.Botnet. OSINT indicates this malware primarily conducts ransomware attacks.
<br />

<h2>Lab Certification:</h2>

<p align="center">
<br/>
<img src="" height="80%" width="80%" alt="portfolio"/>
<br />


<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
