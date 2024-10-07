# Level 0

### Level Goal

The goal of this level is for you to log into the game using **SSH**. The host to which you need to connect is **bandit.labs.overthewire.org**, on port **2220**. The username is **bandit0** and the password is **bandit0**. Once logged in, go to the Level 1 page to find out how to beat Level 1.



### Write-Up

This write-up covers the intial level of the OverTheWire Bandit wargame. Level 0 serves as an introduction to SSH connectivity, a fundamental skill in cybersecurity.



#### Objective

Connect to the game server using SSH with the following parameters:

* Host: bandit.labs.overthewire.org
* Port: 2220
* Username: bandit0
* Password: bandit0



#### Solution

To complete this level, we use the SSH command with specific flags to connect to the non-standard port. Here's the command:

```
ssh bandit0@bandit.labs.overthewire.org -p 2220
```

Let's break down the command:

* ssh: Initiates a secure shell connection
* bandit0: Specifies the username we're logging in with
* bandit.labs.overthewire.org: Specifies the username and host
* \-p 2220: Indicates the port number to connect to (2220 instead of the default 22)

Upon execution you'll be prompted for the password, Enter **bandit0** when asked.



#### Lessons Learned

This first level might seem trivial, but it actually teaches us quite a bit. We got hands-on experience with SSH. which is a tool you'll use constantly in cybersecurity. We also learned about connecting to non-standard port - a common scenario in real-world systems. Plus, we practiced using provided credentials, which is crucial for any penetration testing or security assessment.

The main takeaway? Even simple tasks require careful attention to detail. This level sets the stage for the challenges ahead and reminds us that in cybersecurity, mastering the basics is essential before diving into more complex stuff.



\-- Othmane











