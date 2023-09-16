# ![](https://overthewire.org/img/domokitten.png)

# Bandit_Level15

## Source:
- [Bandit_Level15] - The topic of Bandit, Level15.
###
### I. Connect:
```sh
SSH: ssh -i sshkey.private bandit14@bandit.labs.overthewire.org -p 2220
Password: -
```
### II. My solution:
- We need to find password for 'bandit14' user:
```sh
bandit14@bandit:~$ cat /etc/bandit_pass/bandit14
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
```
- Next, We used 'nc' to connect to localhost port 3000 and write the password.
```sh
bandit14@bandit:~$ nc localhost 30000
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
Correct!
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
```

### III. Result:
We got password for bandit15: jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

[Bandit_Level15]: <https://overthewire.org/wargames/bandit/bandit15.html>
