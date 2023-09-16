# ![](https://overthewire.org/img/domokitten.png)

# Bandit_Level5

## Source:
- [Bandit_Level5] - The topic of Bandit, Level5.
###
### I. Connect:
```sh
ssh -p 2220 bandit4@bandit.labs.overthewire.org
Password: 2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe
```
### II. My solution:
- Use 'cat' to print content of all files is a way to solve this problem, but not a efficient way
- Instead, we can use 'file' command to see type of each file:
```sh
bandit4@bandit:~/inhere$ file ./*
./-file00: data
./-file01: data
./-file02: data
./-file03: data
./-file04: data
./-file05: data
./-file06: data
./-file07: ASCII text
./-file08: data
./-file09: Non-ISO extended-ASCII text, with no line terminators
```
- We can see that only ‘-file07’ is of type ‘ASCII text’, which is one of the encodings, that humans can read.
```sh
bandit4@bandit:~/inhere$ cat ./-file07
lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR
```


### III. Result:
Password for 'bandit5' user: lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR

[Bandit_Level5]: <https://overthewire.org/wargames/bandit/bandit5.html>
