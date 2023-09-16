# ![](https://overthewire.org/img/domokitten.png)

# Bandit_Level23

## Source:
- [Bandit_Level23] - The topic of Bandit, Level23.
###
### I. Connect:
```sh
ssh -p 2220 bandit22@bandit.labs.overthewire.org
Password: WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff
```
### II. My solution:
-  We look at what is in the ‘/etc/cron.d’ folder.
```sh
bandit22@bandit:~$ ls -la /etc/cron.d
total 56
drwxr-xr-x   2 root root  4096 Apr 23 18:05 .
drwxr-xr-x 108 root root 12288 Aug 12 08:42 ..
-rw-r--r--   1 root root    62 Apr 23 18:04 cronjob_bandit15_root
-rw-r--r--   1 root root    62 Apr 23 18:04 cronjob_bandit17_root
-rw-r--r--   1 root root   120 Apr 23 18:04 cronjob_bandit22
-rw-r--r--   1 root root   122 Apr 23 18:04 cronjob_bandit23
-rw-r--r--   1 root root   120 Apr 23 18:04 cronjob_bandit24
-rw-r--r--   1 root root    62 Apr 23 18:04 cronjob_bandit25_root
-rw-r--r--   1 root root   201 Jan  8  2022 e2scrub_all
-rwx------   1 root root    52 Apr 23 18:05 otw-tmp-dir
-rw-r--r--   1 root root   102 Mar 23  2022 .placeholder
-rw-r--r--   1 root root   396 Feb  2  2021 sysstat
```
- We start the same way as previous level 22:
```sh
bandit22@bandit:~$ cat /etc/cron.d/cronjob_bandit23
@reboot bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
* * * * * bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
bandit22@bandit:~$ cat /usr/bin/cronjob_bandit23.sh
#!/bin/bash

myname=$(whoami)
mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)

echo "Copying passwordfile /etc/bandit_pass/$myname to /tmp/$mytarget"

cat /etc/bandit_pass/$myname > /tmp/$mytarget
```
- We need to read the '/tmp/$mytarget' to get the password, but '$mytarget' is not specified so we must find out what really it is.The first variable is ‘myname’ and saves the output from the whoami command. Because this script will be run as bandit23, the whoami command will print ‘bandit23’.
```sh
bandit22@bandit:~$ echo I am user bandit23 | md5sum | cut -d ' ' -f 1 
8ca319486bfbbc3663ea0fbe81326349
```
- After have the name of the file has password, we can execute command to read it as the same way in level22:
```sh
bandit22@bandit:~$ cat /tmp/8ca319486bfbbc3663ea0fbe81326349
QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G
```

### III. Result:
The password for 'bandit23': QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G

[Bandit_Level23]: <https://overthewire.org/wargames/bandit/bandit23.html>
