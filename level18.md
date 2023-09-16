# ![](https://overthewire.org/img/domokitten.png)

# Bandit_Level18

## Source:
- [Bandit_Level18] - The topic of Bandit, Level18.
###
### I. Connect:
```sh
ssh -i sshkeybd17.private bandit17@bandit.labs.overthewire.org -p 2220
Password: -
```
### II. My solution:
- Find the one line that is different between two files.
```sh
bandit17@bandit:~$ diff passwords.old passwords.new
42c42
< glZreTEH1V3cGKL6g4conYqZqaEj0mte
---
> hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg
```
- The second string line is the modifed string, so that is the password for next user.
### III. Result:
The password for 'bandit18': hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg

[Bandit_Level18]: <https://overthewire.org/wargames/bandit/bandit18.html>
