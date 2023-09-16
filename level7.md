# ![](https://overthewire.org/img/domokitten.png)

# Bandit_Level7

## Source:
- [Bandit_Level7] - The topic of Bandit, Level7.
###
### I. Connect:
```sh
ssh -p 2220 bandit6@bandit.labs.overthewire.org
Password: P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU
```
### II. My solution:
- We use 'find' command with the following options:
    + '-type f', because we are looking for a file
    + '-user bandit7', to find files owned by the ‘bandit7’ user
    + '-group bandit6', to find files owned by the ‘bandit6’ group
    + '-size 33c', to find files of size 33 bytes
    + '2>/dev/null', to hide all error message
```sh
bandit6@bandit:~$ find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null
/var/lib/dpkg/info/bandit7.password
```
- We found it! Now just cat the file to get the password:
```sh
bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password
z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S
```
### III. Result:
Password for 'bandit7' user: z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S

[Bandit_Level7]: <https://overthewire.org/wargames/bandit/bandit7.html>
