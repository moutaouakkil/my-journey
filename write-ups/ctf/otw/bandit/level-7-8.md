# Level 7 → 8

## Level Goal

The password for the next level is stored in the file <mark style="color:orange;">data.txt</mark> next to the word <mark style="color:orange;">millionth</mark>



## Write-Up

1. List the content of the current directory:

```sh
ls
```

<figure><img src="../../../../.gitbook/assets/image (1) (1) (1) (1) (1).png" alt="ls"><figcaption></figcaption></figure>

This confirms the presence of the <mark style="color:orange;">data.txt</mark> file.

2. Display the content of data.txt:

```sh
cat data.txt
```

<figure><img src="../../../../.gitbook/assets/image (2) (1) (1) (1) (1).png" alt="cat data.txt"><figcaption></figcaption></figure>

This file contains a large amount of text, making manual search impractical.

3. Search for the line containing 'millionth' in data.txt:

```sh
grep millionth data.txt
```

<figure><img src="../../../../.gitbook/assets/image (1) (1) (1) (1) (1) (1).png" alt="grep millionth data.txt"><figcaption></figcaption></figure>

* `grep`: Command for searching text using patterns
* `millionth`: The pattern I'm searching for
* `data.txt`: The file we're searching in

The password retrieved: <mark style="color:orange;">dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc</mark>

4. Access the next level:

```sh
ssh bandit8@bandit.labs.overthewire.org -p 2220
```

Enter the password when prompted.



## Lessons Learned

* Viewing file contents with `cat` helps understand the data structure
* `grep` is efficient for finding specific lines in large files
* The password isn't always hidden - sometimes it's just mixed with other data



\-- Othmane



