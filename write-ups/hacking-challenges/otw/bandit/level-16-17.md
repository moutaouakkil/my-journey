# Level 16 → 17

## Level Goal

The credentials for the next level can be retrieved by submitting the password of the current level to <mark style="color:orange;">a port on localhost in the range 31000 to 32000</mark>. First find out which of these ports have a server listening on them. Then find out which of those speak SSL/TLS and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it.

**Helpful note: Getting “DONE”, “RENEGOTIATING” or “KEYUPDATE”? Read the “CONNECTED COMMANDS” section in the manpage.**



## Write-Up

1. Use `nmap` to scan for open ports and services:

```sh
nmap -sV localhost -p 31000-32000
```

* `nmap`: Network exploration tool and security scanner
* `-sV`: Probe open ports to determine service/version info
* `localhost`: The target (the working machine)
* `-p 31000-32000`: Specifies the port range to scan

<figure><img src="../../../../.gitbook/assets/Untitled (1).png" alt="nmap -sV localhost -p 31000-32000"><figcaption></figcaption></figure>

The SSL/TLS port <mark style="color:orange;">31790</mark> was identified from the `nmap` results.

2. Connect to the SSL port and submit the <mark style="color:orange;">bandit15</mark> password:

```sh
echo "kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx" | openssl s_client -connect localhost:31790 -ign_eof
```

* `echo "..."`: Outputs the RSA Private Key
* `|`: Pipes the output to the next command
* `openssl s_client`: OpenSSL command for testing SSL/TLS connections
* `-connect localhost:31790`: Specifies the host and port to connect to
* `-ign_eof`: Ignores EOF (end-of-file), keeping the connection open

<figure><img src="../../../../.gitbook/assets/Untitled.png" alt="echo &#x22;kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx&#x22; | openssl s_client -connect localhost:31790 -ign_eof"><figcaption></figcaption></figure>

This outputs the <mark style="color:orange;">RSA Private Key</mark>.

3. Save the RSA Private Key to a file:

```sh
echo "-----BEGIN RSA PRIVATE KEY-----
MIIEogIBAAKCAQEAvmOkuifmMg6HL2YPIOjon6iWfbp7c3jx34YkYWqUH57SUdyJ
imZzeyGC0gtZPGujUSxiJSWI/oTqexh+cAMTSMlOJf7+BrJObArnxd9Y7YT2bRPQ
Ja6Lzb558YW3FZl87ORiO+rW4LCDCNd2lUvLE/GL2GWyuKN0K5iCd5TbtJzEkQTu
DSt2mcNn4rhAL+JFr56o4T6z8WWAW18BR6yGrMq7Q/kALHYW3OekePQAzL0VUYbW
JGTi65CxbCnzc/w4+mqQyvmzpWtMAzJTzAzQxNbkR2MBGySxDLrjg0LWN6sK7wNX
x0YVztz/zbIkPjfkU1jHS+9EbVNj+D1XFOJuaQIDAQABAoIBABagpxpM1aoLWfvD
KHcj10nqcoBc4oE11aFYQwik7xfW+24pRNuDE6SFthOar69jp5RlLwD1NhPx3iBl
J9nOM8OJ0VToum43UOS8YxF8WwhXriYGnc1sskbwpXOUDc9uX4+UESzH22P29ovd
d8WErY0gPxun8pbJLmxkAtWNhpMvfe0050vk9TL5wqbu9AlbssgTcCXkMQnPw9nC
YNN6DDP2lbcBrvgT9YCNL6C+ZKufD52yOQ9qOkwFTEQpjtF4uNtJom+asvlpmS8A
vLY9r60wYSvmZhNqBUrj7lyCtXMIu1kkd4w7F77k+DjHoAXyxcUp1DGL51sOmama
+TOWWgECgYEA8JtPxP0GRJ+IQkX262jM3dEIkza8ky5moIwUqYdsx0NxHgRRhORT
8c8hAuRBb2G82so8vUHk/fur85OEfc9TncnCY2crpoqsghifKLxrLgtT+qDpfZnx
SatLdt8GfQ85yA7hnWWJ2MxF3NaeSDm75Lsm+tBbAiyc9P2jGRNtMSkCgYEAypHd
HCctNi/FwjulhttFx/rHYKhLidZDFYeiE/v45bN4yFm8x7R/b0iE7KaszX+Exdvt
SghaTdcG0Knyw1bpJVyusavPzpaJMjdJ6tcFhVAbAjm7enCIvGCSx+X3l5SiWg0A
R57hJglezIiVjv3aGwHwvlZvtszK6zV6oXFAu0ECgYAbjo46T4hyP5tJi93V5HDi
Ttiek7xRVxUl+iU7rWkGAXFpMLFteQEsRr7PJ/lemmEY5eTDAFMLy9FL2m9oQWCg
R8VdwSk8r9FGLS+9aKcV5PI/WEKlwgXinB3OhYimtiG2Cg5JCqIZFHxD6MjEGOiu
L8ktHMPvodBwNsSBULpG0QKBgBAplTfC1HOnWiMGOU3KPwYWt0O6CdTkmJOmL8Ni
blh9elyZ9FsGxsgtRBXRsqXuz7wtsQAgLHxbdLq/ZJQ7YfzOKU4ZxEnabvXnvWkU
YOdjHdSOoKvDQNWu6ucyLRAWFuISeXw9a/9p7ftpxm0TSgyvmfLF2MIAEwyzRqaM
77pBAoGAMmjmIJdjp+Ez8duyn3ieo36yrttF5NSsJLAbxFpdlc1gvtGCWW+9Cq0b
dxviW8+TFVEBl1O4f7HVm6EpTscdDxU+bCXWkfjuRb7Dy9GOtt9JPsX8MBTakzh3
vBgsyi/sN3RqRBcGU40fOoZyfAMT8s1m/uYv52O6IgeuZ/ujbjY=
-----END RSA PRIVATE KEY-----" > ~/Desktop/sshkey_private_b17
```

* `echo "..."`: Outputs the RSA Private Key
* `>`: Redirects the output to a file
* `~/Desktop/sshkey_private_b17`: The file path and name to save the key

<figure><img src="../../../../.gitbook/assets/image (2) (1).png" alt="Save the RSA Private Key to a file"><figcaption></figcaption></figure>

4. Change the permissions of the key file for security:

```sh
chmod 600 ~/Desktop/sshkey_private_b17
```

* `chmod`: Changes the permissions of the file
* `600`: Sets read and write permissions for the owner only

<figure><img src="../../../../.gitbook/assets/image (3) (1).png" alt=""><figcaption></figcaption></figure>

5. Use the private key to access the next level:

```sh
ssh bandit17@bandit.labs.overthewire.org -p 2220 -i ~/Desktop/sshkey_private_b17
```



## Lessons Learned

* Port scanning tools like `nmap` are essential for identifying open ports and services
* Not all open ports use the same protocol; distinguishing between `SSL` and `non-SSL` services is important
* Private keys can be transmitted as text and need to be properly saved and secured



\-- Othmane



