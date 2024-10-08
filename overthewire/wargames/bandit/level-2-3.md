# Level 2 → 3

### Level Goal

The password for the next level is stored in a file called <mark style="color:orange;">spaces in this filename</mark> located in the home directory.



### Write-Up

#### Objective

Locate and access the contents of a file with spaces in its name, then use the retrieved password to progress to the next level.



#### Solution

1. Verify the file's presence in the home directory:

```sh
ls
```

<figure><img src="../../../.gitbook/assets/image (4).png" alt="ls"><figcaption></figcaption></figure>

This confirms the existence of a file named <mark style="color:orange;">spaces in this filename</mark>.

2. Display the contents of the file:

```sh
cat spaces\ in\ this\ filename
```

<figure><img src="../../../.gitbook/assets/image (1) (1).png" alt="cat spaces\ in\ this\ filename"><figcaption></figcaption></figure>

Note: We use backslashes to escape the spaces in the filename.

3. The revealed password is: <mark style="color:orange;">MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx</mark>
4. Access the next level using the obtained password:

```sh
ssh bandit3@bandit.labs.overthewire.org -p 2220
```

Enter the password when prompted.



#### Summary

This level demonstrates the proper handling of filenames containing spaces in Unix-like systems. By using backslashes to escape spaces, we ensure the shell interprets the filename correctly. This skill is crucial in both system administration and security assessments, where non-standard filenames are common. It emphasizes the importance of understanding shell behavior and syntax for effective command-line operations.



\-- Othmane


