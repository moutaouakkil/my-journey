# Level 16 → 17

## Level Goal

The credentials for the next level can be retrieved by submitting the password of the current level to <mark style="color:orange;">a port on localhost in the range 31000 to 32000</mark>. First find out which of these ports have a server listening on them. Then find out which of those speak SSL/TLS and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it.

**Helpful note: Getting “DONE”, “RENEGOTIATING” or “KEYUPDATE”? Read the “CONNECTED COMMANDS” section in the manpage.**



## Write-Up

1. Use `nmap` to scan for open ports and services:

```sh
nmap -sV localhost -p 31000-32000
```

<figure><img src="../../../.gitbook/assets/Untitled.png" alt=""><figcaption></figcaption></figure>

Identified the SSL/TLS port <mark style="color:orange;">31790</mark> from the `nmap` results.

3. Connect to the SSL port and submit the <mark style="color:orange;">bandit15</mark> password:

```sh
echo "kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx" | openssl s_client -connect localhost:31790 -ign_eof
```







## Lessons Learned

...



\-- Othmane



