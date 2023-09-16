# ![](https://overthewire.org/img/domokitten.png)

# Bandit_Level3

## Source:
- [Bandit_Level3] - The topic of Bandit, Level3.
###
### I. Connect:
```sh
ssh -p 2220 bandit2@bandit.labs.overthewire.org
Password: rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
```
### II. My solution:
- If we simply use 'cat <filename>', we will get error messages:
```sh
bandit2@bandit:~$ cat spaces in this filename
cat: spaces: No such file or directory
cat: in: No such file or directory
cat: this: No such file or directory
cat: filename: No such file or directory
```
- Instead, we need to wrap the names with spaces with quotes:
```sh
bandit2@bandit:~$ cat "spaces in this filename" 
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
```
- Another way is add "\ " after each word:
```sh
bandit2@bandit:~$ cat spaces\ in\ this\ filename 
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
```


### III. Result:
Password for 'bandit3' user: aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG

[Bandit_Level3]: <https://overthewire.org/wargames/bandit/bandit3.html>
