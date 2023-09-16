# ![](https://overthewire.org/img/domokitten.png)

# Bandit_Level20

## Source:
- [Bandit_Level20] - The topic of Bandit, Level20.
###
### I. Connect:
```sh
ssh -p 2220 bandit19@bandit.labs.overthewire.org
Password: awhqfNnAbc1naukrpqDYcF95h7HoMTrC
```
### II. My solution:
- After logging into 'bandit19', print all the file existing:
```sh
bandit19@bandit:~$ ls -la
total 36
drwxr-xr-x  2 root     root      4096 Apr 23 18:04 .
drwxr-xr-x 70 root     root      4096 Apr 23 18:05 ..
-rwsr-x---  1 bandit20 bandit19 14876 Apr 23 18:04 bandit20-do
-rw-r--r--  1 root     root       220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root     root      3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root     root       807 Jan  6  2022 .profile
```
- The hint stated that we needed to execute the file, so execute the file with the "./bandit20-do" command.
```sh
bandit19@bandit:~$ ./bandit20-do 
Run a command as another user.
  Example: ./bandit20-do id
```
- Executing the binary says it simply executes another command as another user (as already explained, this user is bandit20). This means we can access the bandit20 users password file, which can only be read by the user bandit20.  Since the password for bandit20 is in the "/etc/bandit_pass/", we can run the command :
```sh
bandit19@bandit:~$ ./bandit20-do cat  /etc/bandit_pass/bandit20
VxCazJaVykI6W36BkBU0mJTCM8rR95XT
```

### III. Result:
The password for 'bandit20': VxCazJaVykI6W36BkBU0mJTCM8rR95XT

[Bandit_Level20]: <https://overthewire.org/wargames/bandit/bandit20.html>
