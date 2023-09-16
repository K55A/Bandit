# ![](https://overthewire.org/img/domokitten.png)

# Bandit_Level9

## Source:
- [Bandit_Level9] - The topic of Bandit, Level9.
###
### I. Connect:
```sh
ssh -p 2220 bandit8@bandit.labs.overthewire.org
Password: EN632PlfYiZbn3PhVK3XOGSlNInNE00t
```
### II. My solution:
- To find the line that occurs only once in the file, we first sort the lines and then filter for the unique one.
```sh
bandit8@bandit:~$ sort data.txt | uniq -u
EN632PlfYiZbn3PhVK3XOGSlNInNE00t
```
### III. Result:
Password for 'bandit9' user: EN632PlfYiZbn3PhVK3XOGSlNInNE00t

[Bandit_Level9]: <https://overthewire.org/wargames/bandit/bandit9.html>
