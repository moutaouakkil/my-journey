# Level 1 → 2

## Level Goal

The password for the next level is stored in a file called <mark style="color:orange;">-</mark> located in the home directory.



## Write-Up

1. Verify the file's presence in the home directory:

```sh
ls
```

<figure><img src="../../../.gitbook/assets/image (3) (1) (1).png" alt="ls"><figcaption></figcaption></figure>

This confirms the existence of a file named <mark style="color:orange;">-</mark>.

2. Display the contents of the file:

```sh
cat ./-
```

<figure><img src="../../../.gitbook/assets/image (4) (1).png" alt="cat ./-"><figcaption></figcaption></figure>

Note: We use `./` to prefix the filename because `cat` interprets <mark style="color:orange;">-</mark> as a synonym for the standard input (stdin) when used alone.

3. The revealed password is: <mark style="color:orange;">263JGJPfgU6LtdEvgfWU1XP5yac29mFx</mark>
4. Access the next level using the obtained password:

```sh
ssh bandit2@bandit.labs.overthewire.org -p 2220
```

Enter the password when prompted.



## Summary

This level highlights how special characters in filenames can trip up common commands. The dash (<mark style="color:orange;">-</mark>) isn't just a simple character - it's often used for <mark style="color:orange;">stdin/stdout</mark> in Unix systems. By using `./`, we're telling the system to treat the dash as part of a filename, not a special instruction.



\-- Othmane



