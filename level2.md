# ![](https://overthewire.org/img/domokitten.png)

# Bandit_Level2

## Source:
- [Bandit_Level2] - The topic of Bandit, Level2.
###
### I. Connect:
```sh
ssh -p 2220 bandit1@bandit.labs.overthewire.org
Password: NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL
```
### II. My solution:
- Printing all the file to find the '-' file:
```sh
bandit1@bandit:~$ ls
-
```
- Using the command 'cat -' won't return anything, so we need to add the './' before '-':
```sh
bandit1@bandit:~$ cat ./-
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
```



### III. Result:
Password for 'bandit2' user: rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi.

[Bandit_Level2]: <https://overthewire.org/wargames/bandit/bandit2.html>
