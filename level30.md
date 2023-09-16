# ![](https://overthewire.org/img/domokitten.png)

# Bandit_Level30

## Source:
- [Bandit_Level30] - The topic of Bandit, Level30.
###
### I. Connect:
```sh
ssh -p 2220 bandit29@bandit.labs.overthewire.org
Password: tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S
```
### II. My solution:
- We will do as the same way in previous level
```sh
bandit29@bandit:~$ cd /tmp/
bandit29@bandit:/tmp$ mkdir git_lv30
bandit29@bandit:/tmp$ cd git_lv30
bandit29@bandit:/tmp/git_lv30$ git clone ssh://bandit29-git@localhost:2220/home/bandit29-git/repo
bandit29@bandit:/tmp/git_lv30$ ls
repo
bandit29@bandit:/tmp/git_lv30$ cd repo/
bandit29@bandit:/tmp/git_lv30/repo$ ls
README.md
bandit29@bandit:/tmp/git_lv30/repo$ cat README.md 
# Bandit Notes
Some notes for bandit30 of bandit.

## credentials

- username: bandit30
- password: <no passwords in production!>

```
- The sentence ’no passwords in production!’ sounds like there might be more branches. So we check out, if this is the case. Use 'git branch: List (-a), create, or delete branches'
```sh
bandit29@bandit:/tmp/git_lv30/repo$ git branch -a
* master
  remotes/origin/HEAD -> origin/master
  remotes/origin/dev
  remotes/origin/master
  remotes/origin/sploits-dev
```
- Change branch to origin/dev and take a look at the content of the file README .
```sh
bandit29@bandit:/tmp/git_lv30/repo$ git checkout dev
Branch 'dev' set up to track remote branch 'dev' from 'origin'.
Switched to a new branch 'dev'
bandit29@bandit:/tmp/git_lv30/repo$ cat README.md 
# Bandit Notes
Some notes for bandit30 of bandit.

## credentials

- username: bandit30
- password: xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS

```
### III. Result:
The password for 'bandit30': xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS

[Bandit_Level30]: <https://overthewire.org/wargames/bandit/bandit30.html>
