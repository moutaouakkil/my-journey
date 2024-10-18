# Level 11 → 12

## Level Goal

The password for the next level is stored in the file <mark style="color:orange;">data.txt</mark>, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions



## Write-Up

1. List the content of the current directory:

```sh
ls
```

<figure><img src="../../../../.gitbook/assets/image (19).png" alt="ls"><figcaption></figcaption></figure>

This confirms the presence of the <mark style="color:orange;">data.txt</mark> file.

2. Display the content of the data.txt file:

```sh
cat data.txt
```

<figure><img src="../../../../.gitbook/assets/image (20).png" alt="cat data.txt"><figcaption></figcaption></figure>

This revealed a string of text with rotated letters.

3. To decode the ROT13 cipher, the `tr` (translate) command was used:

```sh
cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
```

<figure><img src="../../../../.gitbook/assets/image (21).png" alt="cat data.txt | tr &#x27;A-Za-z&#x27; &#x27;N-ZA-Mn-za-m&#x27;"><figcaption></figcaption></figure>

* `cat data.txt`: Outputs the content of the file
* `|`: Pipes the output to the next command
* `tr 'A-Za-z' 'N-ZA-Mn-za-m'`: Translates the rotated letters back to their original positions

The retrieved password: <mark style="color:orange;">7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4</mark>

4. Access the next level:

```sh
ssh bandit12@bandit.labs.overthewire.org -p 2220
```

Enter the password when prompted.



## Lessons Learned

* ROT13 is a simple letter substitution cipher that rotates letters by 13 positions
* The `tr` command in Unix is versatile for character-level text transformations
* Simple ciphers like ROT13 can be decoded using basic command-line tools



\-- Othmane



