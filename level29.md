# ![](https://overthewire.org/img/domokitten.png)

# Bandit_Level29

## Source:
- [Bandit_Level29] - The topic of Bandit, Level29.
###
### I. Connect:
```sh
ssh -p 2220 bandit28@bandit.labs.overthewire.org
Password: AVanL161y9rsbcJIsFHuw35rjaOM19nR
```
### II. My solution:
- We will do as the same way in previous level
```sh
bandit28@bandit:~$ cd /tmp/
bandit28@bandit:/tmp$ mkdir git_lv28
bandit28@bandit:/tmp$ cd git_lv28
bandit28@bandit:/tmp/git_lv28$ git clone ssh://bandit28-git@localhost:2220/home/bandit28-git/repo
bandit28@bandit:/tmp/git_lv28$ ls
repo
bandit28@bandit:/tmp/git_lv28$ cd repo/
bandit28@bandit:/tmp/git_lv28/repo$ ls
README.md
bandit28@bandit:/tmp/git_lv28/repo$ ./README.md
-bash: ./README.md: Permission denied
bandit28@bandit:/tmp/git_lv28/repo$ cat README.md 
# Bandit Notes
Some notes for level29 of bandit.

## credentials

- username: bandit29
- password: xxxxxxxxxx

```
- This time, the README has Markdown format (’.md’). It mentions, but does not contain the password. We can take a look at the git history to see, if a past version of the README file contained the password. First, we check out the log.
```sh
bandit28@bandit:/tmp/git_lv28/repo$ git log
commit 899ba88df296331cc01f30d022c006775d467f28 (HEAD -> master, origin/master, origin/HEAD)
Author: Morla Porla <morla@overthewire.org>
Date:   Sun Apr 23 18:04:39 2023 +0000

    fix info leak

commit abcff758fa6343a0d002a1c0add1ad8c71b88534
Author: Morla Porla <morla@overthewire.org>
Date:   Sun Apr 23 18:04:39 2023 +0000

    add missing data

commit c0a8c3cf093fba65f4ee0e1fe2a530b799508c78
Author: Ben Dover <noone@overthewire.org>
Date:   Sun Apr 23 18:04:39 2023 +0000

    initial commit of README.md

```
- Notify the line has descryption:'fix info leak', maybe we need to see that change, we will use 'git show' command to do it:
```sh
bandit28@bandit:/tmp/git_lv28/repo$ git show 899ba88df296331cc01f30d022c006775d467f28
commit 899ba88df296331cc01f30d022c006775d467f28 (HEAD -> master, origin/master, origin/HEAD)
Author: Morla Porla <morla@overthewire.org>
Date:   Sun Apr 23 18:04:39 2023 +0000

    fix info leak

diff --git a/README.md b/README.md
index b302105..5c6457b 100644
--- a/README.md
+++ b/README.md
@@ -4,5 +4,5 @@ Some notes for level29 of bandit.
 ## credentials
 
 - username: bandit29
-- password: tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S
+- password: xxxxxxxxxx

```
### III. Result:
The password for 'bandit29': tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S

[Bandit_Level29]: <https://overthewire.org/wargames/bandit/bandit29.html>
