# ![](https://overthewire.org/img/domokitten.png)

# Bandit_Level8

## Source:
- [Bandit_Level8] - The topic of Bandit, Level8.
###
### I. Connect:
```sh
ssh -p 2220 bandit7@bandit.labs.overthewire.org
Password: z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S
```
### II. My solution:
- Checking the file size of data.txt, we can see it is huge:
```sh
bandit7@bandit:~$ du -b data.txt 
4184396 data.txt
```
- We can use 'grep millionth' to get the line content word 'millionth':
```sh
bandit7@bandit:~$ cat data.txt | grep millionth
millionth	TESKZC0XvTetK0S9xNwm25STk5iWrBvP
```
### III. Result:
Password for 'bandit8' user: TESKZC0XvTetK0S9xNwm25STk5iWrBvP

[Bandit_Level8]: <https://overthewire.org/wargames/bandit/bandit8.html>
