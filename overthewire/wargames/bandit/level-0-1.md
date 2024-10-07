# Level 0 → 1

### Level Goal

The password for the next level is stored in a file called **readme** located in the **home** directory. Use this password to log into **bandit1** using **SSH**. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.



### Write-Up

Locate and retrieve the password stored in the **readme** file within the home directory, then use it to access the next level.



#### Solution

1. List the content of the current directory:

```sh
ls
```

<figure><img src="../../../.gitbook/assets/image (1).png" alt="ls"><figcaption></figcaption></figure>

This confirms the presence of the **readme** file.

2. Display the contents of the **readme** file:

```sh
cat readme
```

<figure><img src="../../../.gitbook/assets/image (2).png" alt="cat readme"><figcaption></figcaption></figure>

This reveals the password: **ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If**

3. Use the obtained password to access the next level:

```sh
ssh bandit1@bandit.labs.overthewire.org -p 2220
```

When prompted, enter the password retrieved from the **readme** file.



#### Lessons Learned

We practiced basic file system navigation and learned the importance of checking obvious places for information. It's a reminder that sometimes sensitive data, like passwords, can be found in plain sight. The game also emphasizes the value of command-line proficiency, particularly in using common utilities like **ls** and **cat**. These skills form the backbone of system exploration and information gathering, crucial in both attack and defense scenarios in cybersecurity.



\-- Othmane



