# ![](https://overthewire.org/img/domokitten.png)

# Bandit_Level6

## Source:
- [Bandit_Level6] - The topic of Bandit, Level6.
###
### I. Connect:
```sh
ssh -p 2220 bandit5@bandit.labs.overthewire.org
Password: lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR
```
### II. My solution:
- Go into the ‘inhere’ directory and getting an overview of what is inside it.
```sh
bandit5@bandit:~/inhere$ ls -la
total 88
drwxr-x--- 22 root bandit5 4096 Apr 23 18:04 .
drwxr-xr-x  3 root root    4096 Apr 23 18:04 ..
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere00
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere01
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere02
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere03
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere04
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere05
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere06
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere07
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere08
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere09
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere10
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere11
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere12
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere13
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere14
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere15
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere16
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere17
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere18
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere19

bandit5@bandit:~/inhere$ ls -la maybehere00
total 72
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 .
drwxr-x--- 22 root bandit5 4096 Apr 23 18:04 ..
-rwxr-x---  1 root bandit5 1039 Apr 23 18:04 -file1
-rwxr-x---  1 root bandit5  551 Apr 23 18:04 .file1
-rw-r-----  1 root bandit5 9388 Apr 23 18:04 -file2
-rw-r-----  1 root bandit5 7836 Apr 23 18:04 .file2
-rwxr-x---  1 root bandit5 7378 Apr 23 18:04 -file3
-rwxr-x---  1 root bandit5 4802 Apr 23 18:04 .file3
-rwxr-x---  1 root bandit5 6118 Apr 23 18:04 spaces file1
-rw-r-----  1 root bandit5 6850 Apr 23 18:04 spaces file2
-rwxr-x---  1 root bandit5 1915 Apr 23 18:04 spaces file3
```
- What we can do is use the information from the task and search all files in all the directories
- Use 'file */{.,}* | grep "ASCII text" | grep -v ', with very long lines'' command to get the file that human can read and is not with long lines.
```sh
bandit5@bandit:~/inhere$ file */{.,}* | grep "ASCII text" | grep -v ', with very long lines'
maybehere10/.file2:       ASCII text
maybehere15/.file2:       ASCII text
maybehere01/-file2:       ASCII text
maybehere08/spaces file1: ASCII text
maybehere12/-file2:       ASCII text
maybehere15/spaces file2: ASCII text
maybehere18/-file2:       ASCII text
```
- To narrow down out options, with help of the du command, we again use grep to filter for the correct size (‘1033’):
```sh
bandit5@bandit:~/inhere$ du -b -a | grep 1033
1033	./maybehere07/.file2
```
- Finally, use 'cat' command to get the password:
```sh
bandit5@bandit:~/inhere$ cat ./maybehere07/.file2
P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU
```
### III. Result:
Password for 'bandit6' user: P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU

[Bandit_Level6]: <https://overthewire.org/wargames/bandit/bandit6.html>
