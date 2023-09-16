# ![](https://overthewire.org/img/domokitten.png)

# Bandit_Level12

## Source:
- [Bandit_Level12] - The topic of Bandit, Level12.
###
### I. Connect:
```sh
ssh -p 2220 bandit11@bandit.labs.overthewire.org
Password: 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM
```
### II. My solution:
- Use 'tr' command, The substitution for ROT13 is A->N,…,Z->M:
```sh
bandit11@bandit:~$ cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
The password is JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv
```

### III. Result:
Password for 'bandit12' user: JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv

[Bandit_Level12]: <https://overthewire.org/wargames/bandit/bandit12.html>
