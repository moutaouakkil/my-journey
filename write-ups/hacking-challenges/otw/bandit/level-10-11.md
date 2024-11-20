# Level 10 → 11

## Level Goal

The password for the next level is stored in the file <mark style="color:orange;">data.txt</mark>, which contains base64 encoded data



## Write-Up

1. List the content of the current directory:

```sh
ls
```

<figure><img src="../../../../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1) (1).png" alt="ls"><figcaption></figcaption></figure>

This confirms the presence of the <mark style="color:orange;">data.txt</mark> file.

2. Display the content of the data.txt file:

```sh
cat data.txt
```

<figure><img src="../../../../.gitbook/assets/image (3) (1) (1) (1) (1) (1) (1) (1).png" alt="cat data.txt"><figcaption></figcaption></figure>

This revealed a string of base64 encoded data.

3. To decode the base64 data, the following command was used:

```sh
base64 -d data.txt
```

<figure><img src="../../../../.gitbook/assets/image (4) (1) (1) (1) (1) (1).png" alt="base64 -d data.txt"><figcaption></figcaption></figure>

* `base64`: The command used for encoding/decoding base64 data
* `-d`: Flag specifying decode mode (as opposed to encode)
* `data.txt`: The input file containing the encoded data

The password retrieved: <mark style="color:orange;">dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr</mark>

4. Access the next level:

```sh
ssh bandit11@bandit.labs.overthewire.org -p 2220
```

Enter the password when prompted.



## Lessons Learned

* Base64 is a common encoding scheme used to represent binary data in ASCII string format
* The `base64` command in Unix systems can both encode and decode base64 data
* Simple command-line tools can often decode common data formats without need for specialized software



\-- Othmane



