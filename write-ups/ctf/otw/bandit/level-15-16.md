# Level 15 → 16

## Level Goal

The password for the next level can be retrieved by submitting the password of the current level to <mark style="color:orange;">port 30001 on localhost</mark> using SSL/TLS encryption.

**Helpful note: Getting “DONE”, “RENEGOTIATING” or “KEYUPDATE”? Read the “CONNECTED COMMANDS” section in the manpage.**



## Write-Up

1. The password for the <mark style="color:orange;">bandit15</mark> level: <mark style="color:orange;">8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo</mark>
2. Use `OpenSSL` to connect to localhost on port 30001 with SSL/TLS encryption:

```sh
openssl s_client -connect localhost:30001
```

<figure><img src="../../../../.gitbook/assets/image (25).png" alt="openssl s_client -connect localhost:30001"><figcaption></figcaption></figure>

3. After the SSL handshake is completed, enter the bandit15 password:

```sh
8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo
```

<figure><img src="../../../../.gitbook/assets/image (27).png" alt="8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo"><figcaption></figcaption></figure>

The server responded with the password for the next level: <mark style="color:orange;">kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx</mark>

4. Access the next level:

```sh
ssh bandit16@bandit.labs.overthewire.org -p 2220
```

Enter the password when prompted.



## Lessons Learned

* The `openssl` command-line tool is useful for establishing secure connections
* SSL/TLS encryption can be used for local connections, not just over networks
* Sending sensitive data (like passwords) over encrypted connections is more secure, even locally



\-- Othmane



