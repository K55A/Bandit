# ![](https://overthewire.org/img/domokitten.png)

# Bandit_Level32

## Source:
- [Bandit_Level32] - The topic of Bandit, Level32.
###
### I. Connect:
```sh
ssh -p 2220 bandit31@bandit.labs.overthewire.org
Password: OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt
```
### II. My solution:
- We will do as the same way in previous level
```sh
bandit31@bandit:~$ cd /tmp/
bandit31@bandit:/tmp$ mkdir git_lv32
bandit31@bandit:/tmp$ cd git_lv32
bandit31@bandit:/tmp/git_lv32$ git clone ssh://bandit31-git@localhost:2220/home/bandit31-git/repo
bandit31@bandit:/tmp/git_lv32$ cd repo/
bandit31@bandit:/tmp/git_lv32/repo$ ls
README.md
bandit31@bandit:/tmp/git_lv32/repo$ cat README.md 
This time your task is to push a file to the remote repository.

Details:
    File name: key.txt
    Content: 'May I come in?'
    Branch: master
```
- The ‘README’ states that we have to push a file to the repository. So first, we create the file:
```sh
bandit31@bandit:/tmp/git_lv32/repo$ echo 'May I come in?' > key.txt
bandit31@bandit:/tmp/git_lv32/repo$ ls -la
total 24
drwxrwxr-x 3 bandit31 bandit31 4096 Sep 15 15:00 .
drwxrwxr-x 3 bandit31 bandit31 4096 Sep 15 14:58 ..
drwxrwxr-x 8 bandit31 bandit31 4096 Sep 15 14:58 .git
-rw-rw-r-- 1 bandit31 bandit31    6 Sep 15 14:58 .gitignore
-rw-rw-r-- 1 bandit31 bandit31   15 Sep 15 15:00 key.txt
-rw-rw-r-- 1 bandit31 bandit31  147 Sep 15 14:58 README.md
```
- Now we can try to push the new file by first making a commit and then pushing it. However, this will not work because of the file ‘.gitignore’ in the repo. This file lists files/-types that git will not push to the repository. In this case, exactly all files ending with ‘.txt’.
```sh
bandit31@bandit:/tmp/git_lv32/repo$ cat .gitignore 
*.txt
```
- To add the file anyway, we need to use git add. Then commit and push. The commit will open the ’nano’ editor and expects a message along with the commit, which can be whatever you want.
```sh
bandit31@bandit:/tmp/git_lv32/repo$ git add -f key.txt 
bandit31@bandit:/tmp/git_lv32/repo$ git commit -a
Unable to create directory /home/bandit31/.local/share/nano/: No such file or directory
It is required for saving/loading search history or cursor positions.

[master f73608d] This is the next level password
 1 file changed, 1 insertion(+)
 create mode 100644 key.txt
```
- Now we can try to push the new file
```sh
bandit31@bandit:/tmp/git_lv32/repo$ git push -u origin master 
...
bandit31-git@localhost's password: 
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 2 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 340 bytes | 340.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
remote: ### Attempting to validate files... ####
remote: 
remote: .oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.
remote: 
remote: Well done! Here is the password for the next level:
remote: rmCBvG56y58BXzv98yZGdO7ATVL5dW8y 
remote: 
remote: .oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.
remote: 
To ssh://localhost:2220/home/bandit31-git/repo
 ! [remote rejected] master -> master (pre-receive hook declined)
error: failed to push some refs to 'ssh://localhost:2220/home/bandit31-git/repo'
```
### III. Result:
The password for 'bandit32': rmCBvG56y58BXzv98yZGdO7ATVL5dW8y 

[Bandit_Level32]: <https://overthewire.org/wargames/bandit/bandit32.html>
