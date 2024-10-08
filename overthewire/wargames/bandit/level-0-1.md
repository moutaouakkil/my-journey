# Level 0 → 1

### Level Goal

The password for the next level is stored in a file called <mark style="color:orange;">readme</mark> located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.



### Write-Up

#### Objective

Locate and retrieve the password stored in the <mark style="color:orange;">readme</mark> file within the home directory, then use it to access the next level.



#### Solution

1. List the content of the current directory:

```sh
ls
```

<figure><img src="../../../.gitbook/assets/image (1).png" alt="ls"><figcaption></figcaption></figure>

This confirms the presence of the <mark style="color:orange;">readme</mark> file.

2. Display the contents of the <mark style="color:orange;">readme</mark> file:

```sh
cat readme
```

<figure><img src="../../../.gitbook/assets/image (2).png" alt="cat readme"><figcaption></figcaption></figure>

This reveals the password: <mark style="color:orange;">ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If</mark>

3. Use the obtained password to access the next level:

```sh
ssh bandit1@bandit.labs.overthewire.org -p 2220
```

When prompted, enter the password retrieved from the <mark style="color:orange;">readme</mark> file.



#### Summary

We practiced basic file system navigation and learned the importance of checking obvious places for information. It's a reminder that sometimes sensitive data, like passwords, can be found in plain sight. The game also emphasizes the value of command-line proficiency, particularly in using common utilities like <mark style="color:orange;">ls</mark> and <mark style="color:orange;">cat</mark>. These skills form the backbone of system exploration and information gathering, crucial in both attack and defense scenarios in cybersecurity.



\-- Othmane


