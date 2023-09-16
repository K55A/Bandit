# ![](https://overthewire.org/img/domokitten.png)

# Bandit_Level10

## Source:
- [Bandit_Level10] - The topic of Bandit, Level10.
###
### I. Connect:
```sh
ssh -p 2220 bandit9@bandit.labs.overthewire.org
Password: EN632PlfYiZbn3PhVK3XOGSlNInNE00t
```
### II. My solution:
- We use the strings command to distinguish human-readable strings in ‘data.txt’. Then add 'grep' with equal sign, the number can be around 2-10
```sh
bandit9@bandit:~$ strings data.txt | grep ==
4========== the#
========== password
========== is
========== G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
```

### III. Result:
Password for 'bandit10' user: G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s

[Bandit_Level10]: <https://overthewire.org/wargames/bandit/bandit10.html>
