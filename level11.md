# ![](https://overthewire.org/img/domokitten.png)

# Bandit_Level11

## Source:
- [Bandit_Level11] - The topic of Bandit, Level11.
###
### I. Connect:
```sh
ssh -p 2220 bandit10@bandit.labs.overthewire.org
Password: G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
```
### II. My solution:
- The base64 command allows files as input, so we just need to use the command on the file.
```sh
bandit10@bandit:~$ cat data.txt |  base64 -d
The password is 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM
```

### III. Result:
Password for 'bandit11' user: 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM

[Bandit_Level11]: <https://overthewire.org/wargames/bandit/bandit11.html>
