Always starts with Nmap Scanning, In this case only two port was open port 22, 80

open *http://10.10.10.150/*
then look into source code (source -> secret.txt)

http://10.10.10.150/secret.txt

Password: Q3VybGluZzIwMTgh(base64) -->  Curling2018!

After getting password I don't know the username, Again Source is your only friend after looking at source I got UserName.

UserName: Floris
Password: Curling2018!

(Got access to the web portal).
After some enumeration I got this link
http://10.10.10.150/administrator/index.php (Up username and password)
Then go to template and in index.php write php reverse shell code and enable netcat listener in your pc, you will get the reverse connection.

For me it is
> nc -lvp 1589

ssh
username: floris
password: 5d<wdCbdZu)|hChXll (bandit level 12 writeup is helpful you will get password_backup file in /home/floris/ directory ,first 					move it to /tmp directory and follow the steps given in bandit level 12 you will get the password.txt 					file at the end.) 
Go to /home/floris directory there you will get user.txt Hurray (First step :-)) 

then there is admin-area folder in same directory there is two files input and report , In input you can write someurl and output of that url stored in report. So after numbers of hit and tries I figured it out.
Write this line in input :

> url = "file:///root/root.txt" 
then open report you will get the hash.
82c198ab6fc5365fdc6da2ee5c26064a

