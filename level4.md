# ![](https://overthewire.org/img/domokitten.png)

# Bandit_Level4

## Source:
- [Bandit_Level4] - The topic of Bandit, Level4.
###
### I. Connect:
```sh
ssh -p 2220 bandit3@bandit.labs.overthewire.org
Password: aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
```
### II. My solution:
- Go to 'inhere' folder and print all it files to find the file name
```sh
bandit3@bandit:~$ cd inhere
bandit3@bandit:~/inhere$ ls -a
.  ..  .hidden
```
- Read the content in hidden file:
```sh
bandit3@bandit:~/inhere$ cat .hidden 
2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe
```


### III. Result:
Password for 'bandit4' user: 2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe

[Bandit_Level4]: <https://overthewire.org/wargames/bandit/bandit4.html>
