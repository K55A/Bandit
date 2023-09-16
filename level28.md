# ![](https://overthewire.org/img/domokitten.png)

# Bandit_Level28

## Source:
- [Bandit_Level28] - The topic of Bandit, Level28.
###
### I. Connect:
```sh
ssh -p 2220 bandit27@bandit.labs.overthewire.org
Password: YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS
```
### II. My solution:
- We create a directory for the project.
```sh
bandit27@bandit:~$ cd /tmp
bandit27@bandit:/tmp$ mkdir git_lv27
bandit27@bandit:/tmp$ cd git_lv27
bandit27@bandit:/tmp/git_lv27$
```
- Lets clone the repository
```sh
bandit27@bandit:/tmp/git_lv27$ git clone ssh://bandit27-git@localhost:2220/home/bandit27-git/repo
...
bandit27-git@localhost's password:
```
- The password is 'bandit27' 's password
```sh
bandit27@bandit:/tmp/git_lv27$ ls
repo
bandit27@bandit:/tmp/git_lv27$ cd repo/
bandit27@bandit:/tmp/git_lv27/repo$ ls
README
```
- Grab the README file to get the password
```sh
bandit27@bandit:/tmp/git_lv27/repo$ cat README 
The password to the next level is: AVanL161y9rsbcJIsFHuw35rjaOM19nR
```
### III. Result:
The password for 'bandit28': AVanL161y9rsbcJIsFHuw35rjaOM19nR

[Bandit_Level28]: <https://overthewire.org/wargames/bandit/bandit28.html>
