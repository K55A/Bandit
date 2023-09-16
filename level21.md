# ![](https://overthewire.org/img/domokitten.png)

# Bandit_Level21

## Source:
- [Bandit_Level21] - The topic of Bandit, Level21.
###
### I. Connect:
```sh
ssh -p 2220 bandit20@bandit.labs.overthewire.org
Password: VxCazJaVykI6W36BkBU0mJTCM8rR95XT
```
### II. My solution:
- Using ’netcat’, we can create a connection in server mode - which listens for inbound connection. To have netcat send the password, We use echo and pipe it into netcat. The -n flag is to prevent newline characters in the input, we can pick random port to use.Lastly, we let the process run in the background with &.
```sh
bandit20@bandit:~$  echo -n "VxCazJaVykI6W36BkBU0mJTCM8rR95XT" | nc -l -p 7554 &
[1] 486383
```
-Now that we are listening from a response, use the "./suconnect 7554" command to run the script and get the next password.
```sh
bandit20@bandit:~$ ./suconnect 7554
Read: VxCazJaVykI6W36BkBU0mJTCM8rR95XT
Password matches, sending next password
NvEJF7oVjkddltPSrdKEFOllh9V1IBcq
```


### III. Result:
The password for 'bandit21': NvEJF7oVjkddltPSrdKEFOllh9V1IBcq

[Bandit_Level21]: <https://overthewire.org/wargames/bandit/bandit21.html>
