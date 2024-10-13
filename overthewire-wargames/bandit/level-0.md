# Level 0

## Level Goal

The goal of this level is for you to log into the game using `SSH`. The host to which you need to connect is <mark style="color:orange;">bandit.labs.overthewire.org</mark>, on port <mark style="color:orange;">2220</mark>. The username is <mark style="color:orange;">bandit0</mark> and the password is <mark style="color:orange;">bandit0</mark>. Once logged in, go to the Level 1 page to find out how to beat Level 1.



## Write-Up

To complete this level, I used the SSH command with specific flags to connect to the non-standard port. Here's the command:

```sh
ssh bandit0@bandit.labs.overthewire.org -p 2220
```

* `ssh`: Initiates a secure shell connection
* `bandit0`: Specifies the username we're logging in with
* `bandit.labs.overthewire.org`: Specifies the username and host
* `-p 2220`: Indicates the port number to connect to (2220 instead of the default 22)

Upon execution, I was prompted for the password and entered <mark style="color:orange;">bandit0</mark>.



## Lessons Learned

* Hands-on experience with SSH
* Connecting to non-standard port



\-- Othmane



