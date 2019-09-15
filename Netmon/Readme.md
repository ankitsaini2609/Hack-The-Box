```
Perform Nmap Scan on Netmon machine.
> nmap -A -v 10.10.10.152
you can see *FTP* on *port 21* allows anonymous login. So I have tried 

*filezilla* to connect to the ftp where

host: 10.10.10.152
port: 21

You will see some directories go to:

> /Users/Public/user.txt

you will get user flag.

After Some enumeration there is PRTG Configuration.old.bak file where you can find username and password to log into the admin portal of the website.

### Username: prtgadmin
### Password: PrTg@dmin2018 Change this to --> PrTg@dmin2019 (It will work).

Then search for PRTG Vulnerablity you will get First link which will tell you about Command injection Vulnerablity By reading that blog one option is to use powershell command to get the root flag.

so After that go to 
you need to add a sensor from the homepage choose sensor - add sensor - select exe/script - choose any Powershell option - set 5 star priority - add the command in parameter field - job done 

Add this line to parameter save it check the given path you will get root file.

> ;more C:\Users\Administrator\Desktop\root.txt >> C:\Users\Public\root.txt

```
