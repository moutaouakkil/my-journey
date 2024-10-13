# Level 9 → 10

## Level Goal

The password for the next level is stored in the file <mark style="color:orange;">data.txt</mark> in one of the few human-readable strings, preceded by several `=` characters.



## Write-Up

1. List the content of the current directory:

```sh
ls
```

<figure><img src="../../../.gitbook/assets/image (15).png" alt="ls"><figcaption></figcaption></figure>

This confirms the presence of the <mark style="color:orange;">data.txt</mark> file.

2. Display the content of the data.txt file:

```sh
cat data.txt
```

<figure><img src="../../../.gitbook/assets/image (17).png" alt="cat data.txt"><figcaption></figcaption></figure>

3. To find human-readable strings proceeded by `=` characters, the `string` command was used in combination with `grep`:

```sh
strings data.txt | grep "="
```

<figure><img src="../../../.gitbook/assets/image (18).png" alt="strings data.txt | grep &#x22;=&#x22;"><figcaption></figcaption></figure>

* `strings data.txt`: Extracts printable strings from the file
* `|`: Pipes the output to the next command
* `grep "="`: Searches for lines containing '=' characters

The password retrieved: <mark style="color:orange;">FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey</mark>

4. Access the next level:

```sh
ssh bandit10@bandit.labs.overthewire.org -p 2220
```

Enter the password when prompted.



## Lessons Learned

* The `strings` command is crucial for extracting readable text from binary files
* `Grep` is versatile for finding patterns, but exact patterns may need adjustment
* Visual inspection of output can be necessary when automated filtering is imprecise
* Binary files often contain hidden, readable information



\-- Othmane



