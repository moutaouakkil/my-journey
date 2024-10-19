# Level 2 → 3

## Level Goal

The password for the next level is stored in a file called <mark style="color:orange;">spaces in this filename</mark> located in the home directory.



## Write-Up

1. Verify the file's presence in the home directory:

```sh
ls
```

<figure><img src="../../../../.gitbook/assets/image (4) (1) (1) (1) (1) (1).png" alt="ls"><figcaption></figcaption></figure>

This confirms the existence of a file named <mark style="color:orange;">spaces in this filename</mark>.

2. Display the content of the file:

```sh
cat spaces\ in\ this\ filename
```

<figure><img src="../../../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt="cat spaces\ in\ this\ filename"><figcaption></figcaption></figure>

Note: To handle spaces in filenames, you can either use `backslashes` to escape each space or enclose the entire filename in quotes `""`.

```sh
cat "spaces in this filename"
```

<figure><img src="../../../../.gitbook/assets/image (5) (1) (1).png" alt="cat &#x22;spaces in this filename&#x22;"><figcaption></figcaption></figure>

3. The revealed password is: <mark style="color:orange;">MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx</mark>
4. Access the next level using the obtained password:

```sh
ssh bandit3@bandit.labs.overthewire.org -p 2220
```

Enter the password when prompted.



## Lessons Learned

* Filenames can contain spaces
* `Backslashes` are used to escape spaces in filenames on the command line
* Alternative methods like using quotes `""` can also be used to handle spaces in filenames
* Proper handling of special characters in filenames is crucial for file operations



\-- Othmane



