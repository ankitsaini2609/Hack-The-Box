open *10.10.10.68/dev/phpbash.php*
then go to ome directory of arrexel you will get user.txt :-)

then after some digging and enumeration there is a script called /scripts
ans after running sudo -l (i came to know that scriptmanager user can run sudo commands without password.)
then i have created a python script (exploit.py) then download it using wget in tmp folder.

> sudo -u scriptmanager cp /tmp/exploit.py /scripts/final.py

> sudo -u scriptmanager python /scripts/final.py

> cd tmp

> cat deafheaven.txt  got root flag :-)
