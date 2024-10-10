# Level 2 → 3

## Level Goal

The password for the next level is stored in a file called <mark style="color:orange;">spaces in this filename</mark> located in the home directory.



## Write-Up

1. Verify the file's presence in the home directory:

```sh
ls
```

<figure><img src="../../.gitbook/assets/image (4).png" alt="ls"><figcaption></figcaption></figure>

This confirms the existence of a file named <mark style="color:orange;">spaces in this filename</mark>.

2. Display the contents of the file:

```sh
cat spaces\ in\ this\ filename
```

<figure><img src="../../.gitbook/assets/image (1) (1) (1).png" alt="cat spaces\ in\ this\ filename"><figcaption></figcaption></figure>

Note: We use `backslashes` to escape the spaces in the filename.

3. The revealed password is: <mark style="color:orange;">MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx</mark>
4. Access the next level using the obtained password:

```sh
ssh bandit3@bandit.labs.overthewire.org -p 2220
```

Enter the password when prompted.



## Lessons Learned

Working with files that have spaces in their names can be tricky on the command line. This level teaches us how to handle that using `backslashes`.



\-- Othmane



