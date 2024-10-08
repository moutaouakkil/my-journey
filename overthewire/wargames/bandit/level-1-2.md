# Level 1 → 2

### Level Goal

The password for the next level is stored in a file called <mark style="color:orange;">-</mark> located in the home directory.



### Write-Up

#### Objective

Retrieve the password stored in the file named <mark style="color:orange;">-</mark> within the home directory, then use it to access the next level.



#### Solution

1. Verify the file's presence in the home directory:

```sh
ls
```

<figure><img src="../../../.gitbook/assets/image (3).png" alt="ls"><figcaption></figcaption></figure>

This confirms the existence of a file named <mark style="color:orange;">-</mark>.

2. Display the contents of the file:

```sh
cat ./-
```

<figure><img src="../../../.gitbook/assets/image (4).png" alt="cat ./-"><figcaption></figcaption></figure>

Note: We use <mark style="color:orange;">./</mark> to prefix the filename because <mark style="color:orange;">cat</mark> interprets <mark style="color:orange;">-</mark> as a synonym for the standard input (stdin) when used alone.

3. The revealed password is: <mark style="color:orange;">263JGJPfgU6LtdEvgfWU1XP5yac29mFx</mark>
4. Access the next level using the obtained password:

```sh
ssh bandit2@bandit.labs.overthewire.org -p 2220
```

Enter the password when prompted.



#### Summary

This level introduces an important concept in command-line interfaces: the handling of special filenames. The dash (<mark style="color:orange;">-</mark>) is often used to signify standard input/output in Unix-like systems, which can cause unexpected behavior with common commands. By using <mark style="color:orange;">./</mark> to specify the current directory, we ensure the filename is interpreted correctly. This scenario underscores the importance of understanding how different characters can affect command interpretation, a crucial skill in both system administration and security testing. It also reinforces the need for adaptability when faced with non-standard situations in file handling.



\-- Othmane

