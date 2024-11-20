# Level 5 → 6

## Level Goal

The password for the next level is stored in a file somewhere under the <mark style="color:orange;">inhere</mark> directory and has all of the following properties:

* human-readable
* 1033 bytes in size
* not executable



## Write-Up

1. Find the file matching the specific criteria:

```sh
find inhere -type f -readable -size 1033c ! -executable
```

<figure><img src="../../../../.gitbook/assets/image (3) (1) (1) (1) (1) (1) (1) (1) (1).png" alt="find inhere -type f -readable -size 1033c ! -executable"><figcaption></figcaption></figure>

* `find inhere`: Start searching in the 'inhere' directory
* `-type f`: Look for regular files
* `-readable`: Find human-readable files
* `-size 1033c`: Look for files exactly 1033 bytes in size
* `! -executable`: Exclude executable files

This command reveals <mark style="color:orange;">.file2</mark> as the only file meeting all requirements.

2. Display the content of the identified file:

```sh
cat $(find inhere -type f -readable -size 1033c ! -executable)
```

<figure><img src="../../../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt="cat $(find inhere -type f -readable -size 1033c ! -executable)"><figcaption></figcaption></figure>

* `cat`: Command to display the content of a file
* `$()`: Command substitution. It allows the output of a command to be used as an argument for another command

Or

```sh
cat inhere/maybehere07/.file2
```

<figure><img src="../../../../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt="cat inhere/maybehere07/.file2"><figcaption></figcaption></figure>

This outputs the password: <mark style="color:orange;">HWasnPhtq9AVKe0dmk45nxy20cvUa6EG</mark>

3. Access the next level:

```sh
ssh bandit6@bandit.labs.overthewire.org -p 2220
```

Enter the password when prompted.



## Lessons Learned

* The `find` command can search based on multiple criteria simultaneously
* File attributes like size and permissions can be used as search parameters
* Command substitution `($())` allows for combining commands efficiently
* Hidden files (starting with .) can contain important information



\-- Othmane



