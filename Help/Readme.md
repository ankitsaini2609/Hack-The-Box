### Starting with nmap scan:
``` Starting Nmap 7.70 ( https://nmap.org ) at 2019-05-19 18:20 IST
NSE: Loaded 148 scripts for scanning.
NSE: Script Pre-scanning.
Initiating NSE at 18:20
Completed NSE at 18:20, 0.00s elapsed
Initiating NSE at 18:20
Completed NSE at 18:20, 0.00s elapsed
Initiating Ping Scan at 18:20
Scanning 10.10.10.121 [4 ports]
Completed Ping Scan at 18:20, 0.18s elapsed (1 total hosts)
Initiating Parallel DNS resolution of 1 host. at 18:20
Completed Parallel DNS resolution of 1 host. at 18:20, 0.00s elapsed
Initiating SYN Stealth Scan at 18:20
Scanning 10.10.10.121 [1000 ports]
Discovered open port 80/tcp on 10.10.10.121
Discovered open port 22/tcp on 10.10.10.121
Increasing send delay for 10.10.10.121 from 0 to 5 due to 149 out of 495 dropped probes since last increase.
Discovered open port 3000/tcp on 10.10.10.121
Completed SYN Stealth Scan at 18:20, 18.37s elapsed (1000 total ports)
Initiating Service scan at 18:20
Scanning 3 services on 10.10.10.121
Completed Service scan at 18:20, 11.46s elapsed (3 services on 1 host)
Initiating OS detection (try #1) against 10.10.10.121
Retrying OS detection (try #2) against 10.10.10.121
Retrying OS detection (try #3) against 10.10.10.121
Retrying OS detection (try #4) against 10.10.10.121
Retrying OS detection (try #5) against 10.10.10.121
Initiating Traceroute at 18:21
Completed Traceroute at 18:21, 0.15s elapsed
Initiating Parallel DNS resolution of 2 hosts. at 18:21
Completed Parallel DNS resolution of 2 hosts. at 18:21, 0.00s elapsed
NSE: Script scanning 10.10.10.121.
Initiating NSE at 18:21
Completed NSE at 18:21, 4.55s elapsed
Initiating NSE at 18:21
Completed NSE at 18:21, 0.00s elapsed
Nmap scan report for 10.10.10.121
Host is up (0.15s latency).
Not shown: 997 closed ports
PORT     STATE SERVICE VERSION
22/tcp   open  ssh     OpenSSH 7.2p2 Ubuntu 4ubuntu2.6 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   2048 e5:bb:4d:9c:de:af:6b:bf:ba:8c:22:7a:d8:d7:43:28 (RSA)
|   256 d5:b0:10:50:74:86:a3:9f:c5:53:6f:3b:4a:24:61:19 (ECDSA)
|_  256 e2:1b:88:d3:76:21:d4:1e:38:15:4a:81:11:b7:99:07 (ED25519)
80/tcp   open  http    Apache httpd 2.4.18 ((Ubuntu))
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
|_http-server-header: Apache/2.4.18 (Ubuntu)
|_http-title: Apache2 Ubuntu Default Page: It works
3000/tcp open  http    Node.js Express framework
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
|_http-title: Site doesn't have a title (application/json; charset=utf-8).
No exact OS matches for host (If you know what OS is running on it, see https://nmap.org/submit/ ).
TCP/IP fingerprint:
OS:SCAN(V=7.70%E=4%D=5/19%OT=22%CT=1%CU=32251%PV=Y%DS=2%DC=T%G=Y%TM=5CE1513
OS:E%P=x86_64-pc-linux-gnu)SEQ(SP=FF%GCD=1%ISR=10F%TI=Z%CI=I%II=I%TS=8)OPS(
OS:O1=M54DST11NW7%O2=M54DST11NW7%O3=M54DNNT11NW7%O4=M54DST11NW7%O5=M54DST11
OS:NW7%O6=M54DST11)WIN(W1=7120%W2=7120%W3=7120%W4=7120%W5=7120%W6=7120)ECN(
OS:R=Y%DF=Y%T=40%W=7210%O=M54DNNSNW7%CC=Y%Q=)T1(R=Y%DF=Y%T=40%S=O%A=S+%F=AS
OS:%RD=0%Q=)T2(R=N)T3(R=N)T4(R=Y%DF=Y%T=40%W=0%S=A%A=Z%F=R%O=%RD=0%Q=)T5(R=
OS:Y%DF=Y%T=40%W=0%S=Z%A=S+%F=AR%O=%RD=0%Q=)T6(R=Y%DF=Y%T=40%W=0%S=A%A=Z%F=
OS:R%O=%RD=0%Q=)T7(R=Y%DF=Y%T=40%W=0%S=Z%A=S+%F=AR%O=%RD=0%Q=)U1(R=Y%DF=N%T
OS:=40%IPL=164%UN=0%RIPL=G%RID=G%RIPCK=G%RUCK=G%RUD=G)IE(R=Y%DFI=N%T=40%CD=
OS:S)

Uptime guess: 0.025 days (since Sun May 19 17:45:27 2019)
Network Distance: 2 hops
TCP Sequence Prediction: Difficulty=255 (Good luck!)
IP ID Sequence Generation: All zeros
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

TRACEROUTE (using port 3389/tcp)
HOP RTT       ADDRESS
1   145.07 ms 10.10.12.1
2   145.24 ms 10.10.10.121

NSE: Script Post-scanning.
Initiating NSE at 18:21
Completed NSE at 18:21, 0.00s elapsed
Initiating NSE at 18:21
Completed NSE at 18:21, 0.00s elapsed
Read data files from: /usr/bin/../share/nmap
OS and Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 48.79 seconds
           Raw packets sent: 1800 (83.274KB) | Rcvd: 1107 (47.862KB)
```
Port 80 is open, Let's begin with directory bruteforcing.
> gobuster -u http://10.10.10.121 -w /usr/share/wordlists/dirb/common.txt

Output:
> /support

It is Helpdeskz CMS
> http://10.10.10.121/support

Try to log a ticket. There's a file upload option while raising ticket. Use that to try to upload php reverse shell. You will be greeted with Files not allowed, error pop up. After checking the source code of HelpDeskz on github, we come to know that the file is already uploaded. Now the question arises as to where the file is being uploaded i.e in which directory and what will be the final filename.
Where part is easy, but the name part is difficult by looking at the code, It is taking `md5(file name + current server time).php` as filename and the folder where it is uploading is:

> http://10.10.10.121/support/uploads/tickets


Now It's time to google the exploit we will get "unauthenciated shell upload exploit", By default it's not working because in the script it is taking local time while we need server time(UTC).
Again check the source code and modify the script, we will get reverse shell as help user ==>  user.txt :).
<b> Exploit is available as final_exploit you can download it </b>

### For Root :-
After Basic Enumeration search for exploit related to kernel version: 
> https://www.exploit-db.com/exploits/44298

Got Root :)
