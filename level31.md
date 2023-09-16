# ![](https://overthewire.org/img/domokitten.png)

# Bandit_Level31

## Source:
- [Bandit_Level31] - The topic of Bandit, Level31.
###
### I. Connect:
```sh
ssh -p 2220 bandit30@bandit.labs.overthewire.org
Password: xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS
```
### II. My solution:
- We will do as the same way in previous level
```sh
bandit30@bandit:~$ cd /tmp/
bandit30@bandit:/tmp$ mkdir git_lv31
bandit30@bandit:/tmp$ cd git_lv31
bandit30@bandit:/tmp/git_lv31$ git clone ssh://bandit30-git@localhost:2220/home/bandit30-git/repo
bandit30@bandit:/tmp/git_lv31$ ls
repo
bandit30@bandit:/tmp/git_lv31$ cd repo/
bandit30@bandit:/tmp/git_lv31/repo$ ls
README.md
bandit30@bandit:/tmp/git_lv31/repo$ cat README.md 
just an epmty file... muahaha
```
- The README does not give us any information. Checking the git tag, we find a point in the history called ‘secret’.Git tagging is a way to mark specific points in the history of the repository. One example would be to mark release points of the software. The command to see the tags is git tag. To create a tag the command is git tag -a <tag_name> -m <"tag description/message">.
```sh
bandit30@bandit:/tmp/git_lv31/repo$ git tag
secret
bandit30@bandit:/tmp/git_lv31/repo$ git show secret 
OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt
```

### III. Result:
The password for 'bandit31': OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt

[Bandit_Level31]: <https://overthewire.org/wargames/bandit/bandit31.html>
