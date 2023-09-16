# ![](https://overthewire.org/img/domokitten.png)

# Bandit_Level33

## Source:
- [Bandit_Level33] - The topic of Bandit, Level33.
###
### I. Connect:
```sh
ssh -p 2220 bandit32@bandit.labs.overthewire.org
Password: rmCBvG56y58BXzv98yZGdO7ATVL5dW8y
```
### II. My solution:
- When using ssh to get access to the machine, we notice that we not in a bash shell instead we in a shell called as “uppercase shell”
```sh
WELCOME TO THE UPPERCASE SHELL
>> ls
sh: 1: LS: Permission denied
```
- So everything we type seems to be made uppercase. The commands we have used so far however, are all lower-case and do not work. The one thing in Linux that is uppercase is variables. Specifically, the variable $0 has a reference to a shell. You can see this with echo $0 on your machine.
```sh
>> $0
$ sh -c "$0"
$ echo $0
sh
$ ls -la
total 36
drwxr-xr-x  2 root     root      4096 Apr 23 18:04 .
drwxr-xr-x 70 root     root      4096 Apr 23 18:05 ..
-rw-r--r--  1 root     root       220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root     root      3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root     root       807 Jan  6  2022 .profile
-rwsr-x---  1 bandit33 bandit32 15128 Apr 23 18:04 uppershell

```
- We can see that the file ‘uppershell’ runs as bandit33. Checking this, we can see that we are in fact ‘bandit33’ and therefore, we can read the password file:
```sh
$ id
uid=11033(bandit33) gid=11032(bandit32) groups=11032(bandit32)
$ whoami
bandit33
$ cat /etc/bandit_pass/bandit33
odHo63fHiFqcWWJG9rLiLDtPm45KzUKy
```
- This is the last level, we can relize as soon as we log into bandit33 and read the README file:
```sh
bandit33@bandit:~$ ls
README.txt
bandit33@bandit:~$ cat README.txt 
Congratulations on solving the last level of this game!

At this moment, there are no more levels to play in this game. However, we are constantly working
on new levels and will most likely expand this game with more levels soon.
Keep an eye out for an announcement on our usual communication channels!
In the meantime, you could play some of our other wargames.

If you have an idea for an awesome new level, please let us know!

```
### III. Result:
The password for 'bandit33': odHo63fHiFqcWWJG9rLiLDtPm45KzUKy

[Bandit_Level33]: <https://overthewire.org/wargames/bandit/bandit33.html>
