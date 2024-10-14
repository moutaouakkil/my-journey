# Level 1 → 2

## Level Goal

The password for the next level is stored in a file called <mark style="color:orange;">-</mark> located in the home directory.



## Write-Up

1. Verify the file's presence in the home directory:

```sh
ls
```

<figure><img src="../../.gitbook/assets/image (3) (1) (1) (1) (1) (1).png" alt="ls"><figcaption></figcaption></figure>

This confirms the existence of a file named <mark style="color:orange;">-</mark>.

2. Display the content of the file:

```sh
cat ./-
```

<figure><img src="../../.gitbook/assets/image (4) (1) (1) (1).png" alt="cat ./-"><figcaption></figcaption></figure>

Note: Use `./` to prefix the filename because `cat` interprets <mark style="color:orange;">-</mark> as a synonym for the standard input (stdin) when used alone.

3. The revealed password is: <mark style="color:orange;">263JGJPfgU6LtdEvgfWU1XP5yac29mFx</mark>
4. Access the next level using the obtained password:

```sh
ssh bandit2@bandit.labs.overthewire.org -p 2220
```

Enter the password when prompted.



## Lessons Learned

* Special characters in filenames can affect how commands interpret them
* The dash (-) is often used to represent stdin/stdout in Unix systems
* Using `./` before a filename tells the system to treat it as a file path
* Understanding how commands interpret arguments is crucial for handling unusual filenames



\-- Othmane



