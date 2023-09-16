# ![](https://overthewire.org/img/domokitten.png)

# Bandit_Level26

## Source:
- [Bandit_Level26] - The topic of Bandit, Level26.
###
### I. Connect:
```sh
ssh -p 2220 bandit25@bandit.labs.overthewire.org
Password: p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d
```
### II. My solution:
-  The first we saw that a 'sshkey' file of bandit26: 
```sh
bandit25@bandit:~$ ls
bandit26.sshkey
```
- Try using it to ssh to bandit26:
```sh
bandit25@bandit:~$ ssh bandit26@localhost -i bandit26.sshkey -p 2220
...
Connection to localhost closed.
```
- May be we need to check what shell the user bandit26 used. We do this by looking in the correct line in the ‘passwd’ file.
```sh
bandit25@bandit:~$ cat /etc/passwd | grep bandit26
bandit26:x:11026:11026:bandit level 26:/home/bandit26:/usr/bin/showtext
bandit25@bandit:~$ ls -la /usr/bin/showtext
-rwxr-xr-x 1 root root 53 May  7  2020 /usr/bin/showtext
bandit25@bandit:~$ cat /usr/bin/showtext
#!/bin/sh

export TERM=linux

more ~/text.txt
exit 0
```
- The text in ’text.txt’ is very short, meaning the whole text can immediately be displayed. more does not need to go into command/interactive mode. If we make the terminal window smaller, more will go into command mode. We can then use v to go into vim. Now we can rescale the window.
- Vim is now opened as bandit26 and we can do different things to retrieve the password. With :e /etc/bandit\_pass/bandit26 we can open the password file and read the password. If we want a shell, we could try the :shell command that vim offers. This command, however, uses the user’s default shell. What we need to do instead is to set the default shell of the user in vim to a useful shell, like \bin\bash. The commands look like the following: :set shell=/bin/bash and then use :shell. Finally, we have a shell and can get the password for the user.
```sh
bandit26@bandit:~$ ls
bandit27-do  text.txt
bandit26@bandit:~$ cat /etc/bandit_pass/bandit26
c7GvcKlw9mC7aUQaPx7nwFstuAIBw1o1
```

### III. Result:
The password for 'bandit26': c7GvcKlw9mC7aUQaPx7nwFstuAIBw1o1

[Bandit_Level26]: <https://overthewire.org/wargames/bandit/bandit26.html>
