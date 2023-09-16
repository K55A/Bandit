# ![](https://overthewire.org/img/domokitten.png)

# Bandit_Level22

## Source:
- [Bandit_Level22] - The topic of Bandit, Level22.
###
### I. Connect:
```sh
ssh -p 2220 bandit21@bandit.labs.overthewire.org
Password: NvEJF7oVjkddltPSrdKEFOllh9V1IBcq
```
### II. My solution:
-  We look at what is in the ‘/etc/cron.d’ folder.
```sh
bandit21@bandit:~$ ls /etc/cron.d
cronjob_bandit15_root  cronjob_bandit22  cronjob_bandit24       e2scrub_all  sysstat
cronjob_bandit17_root  cronjob_bandit23  cronjob_bandit25_root  otw-tmp-dir
```
- We will try to 'cat' the 'cronjob_bandit22':
```sh
bandit21@bandit:~$ cat /etc/cron.d/cronjob_bandit22
@reboot bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
* * * * * bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
```
- This cronjob runs the /usr/bin/cronjob_bandit22.sh file as bandit22 user. To know what exactly is executed, we need to take a look at the bash file.
```sh
bandit21@bandit:~$ cat /usr/bin/cronjob_bandit22.sh
#!/bin/bash
chmod 644 /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
cat /etc/bandit_pass/bandit22 > /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
```
- We can see that it copy 'bandit22' password to /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv, then we can 'cat' it to get the password:
```sh
bandit21@bandit:~$ cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff
```

### III. Result:
The password for 'bandit22': WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff

[Bandit_Level22]: <https://overthewire.org/wargames/bandit/bandit22.html>
