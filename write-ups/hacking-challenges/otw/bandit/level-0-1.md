# Level 0 → 1

## Level Goal

The password for the next level is stored in a file called <mark style="color:orange;">readme</mark> located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.



## Write-Up

1. List the content of the current directory:

```sh
ls
```

<figure><img src="../../../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt="ls"><figcaption></figcaption></figure>

This confirms the presence of the <mark style="color:orange;">readme</mark> file.

2. Display the content of the <mark style="color:orange;">readme</mark> file:

```sh
cat readme
```

<figure><img src="../../../../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt="cat readme"><figcaption></figcaption></figure>

This reveals the password: <mark style="color:orange;">ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If</mark>

3. Use the obtained password to access the next level:

```sh
ssh bandit1@bandit.labs.overthewire.org -p 2220
```

When prompted, enter the password retrieved from the <mark style="color:orange;">readme</mark> file.



## Lessons Learned

* Basic file system navigation is crucial for finding information
* Important data may be stored in plainly named files like 'readme'
* The `ls` command is essential for listing directory contents
* The `cat` command is useful for quickly viewing file contents
* Always check obvious locations for information before looking elsewhere



\-- Othmane



