# ![](https://overthewire.org/img/domokitten.png)

# Bandit_Level19

## Source:
- [Bandit_Level19] - The topic of Bandit, Level19.
###
### I. Connect:
```sh
ssh -p 2220 bandit18@bandit.labs.overthewire.org
Password: hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg
```
### II. My solution:
- Instead of logging into the machine with SSH, we execute a command through SSH instead, use the -t flag, which allows a ‘pseudo-terminal’ to run on the target machine, this way we can run \bin\sh.
```sh
$ssh bandit18@bandit.labs.overthewire.org -p 2220 -t /bin/sh
```
- After typing password correctly, we can execute command to read the file content password:
```sh
$ ls
readme
$ cat readme	
awhqfNnAbc1naukrpqDYcF95h7HoMTrC
```
### III. Result:
The password for 'bandit19': awhqfNnAbc1naukrpqDYcF95h7HoMTrC

[Bandit_Level19]: <https://overthewire.org/wargames/bandit/bandit19.html>
