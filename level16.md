# ![](https://overthewire.org/img/domokitten.png)

# Bandit_Level16

## Source:
- [Bandit_Level16] - The topic of Bandit, Level16.
###
### I. Connect:
```sh
ssh -p 2220 bandit15@bandit.labs.overthewire.org
Password: jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
```
### II. My solution:
- We connect to the localhost server with the OpenSSL client and send the password from this level
```sh
bandit15@bandit:~$ openssl s_client -connect localhost:30001
...
read R BLOCK
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
Correct!
JQttfApK4SeyHwDlI9SXGR50qclOAil1

closed

```



### III. Result:
We got password for bandit16: JQttfApK4SeyHwDlI9SXGR50qclOAil1

[Bandit_Level16]: <https://overthewire.org/wargames/bandit/bandit16.html>
