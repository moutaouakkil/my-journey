# Level 0

## Level Goal

The goal of this level is for you to log into the game using `SSH`. The host to which you need to connect is <mark style="color:orange;">bandit.labs.overthewire.org</mark>, on port <mark style="color:orange;">2220</mark>. The username is <mark style="color:orange;">bandit0</mark> and the password is <mark style="color:orange;">bandit0</mark>. Once logged in, go to the Level 1 page to find out how to beat Level 1.



## Write-Up

To complete this level, we use the SSH command with specific flags to connect to the non-standard port. Here's the command:

```sh
ssh bandit0@bandit.labs.overthewire.org -p 2220
```

Let's break down the command:

* `ssh`: Initiates a secure shell connection
* `bandit0`: Specifies the username we're logging in with
* `bandit.labs.overthewire.org`: Specifies the username and host
* `-p 2220`: Indicates the port number to connect to (2220 instead of the default 22)

Upon execution you'll be prompted for the password, Enter <mark style="color:orange;">bandit0</mark> when asked.



## Lessons Learned

We got hands-on experience with `SSH`. which is a tool you'll use constantly in cybersecurity. We also learned about connecting to non-standard port - a common scenario in real-world systems.



\-- Othmane



