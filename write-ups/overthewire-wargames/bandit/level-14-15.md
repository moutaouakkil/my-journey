# Level 14 → 15

## Level Goal

The password for the next level can be retrieved by submitting the password of the current level to <mark style="color:orange;">port 30000 on localhost</mark>.



## Write-Up

1. The password for the <mark style="color:orange;">bandit14</mark> level: <mark style="color:orange;">MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS</mark>
2. Use Netcat `nc` to connect to localhost on port 30000 and submit the password:

```sh
echo "MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS" | nc localhost 30000
```

* `echo "MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS"`: Outputs the bandit14 password
* `|`: Pipes the output to the next command
* `nc localhost 30000`: Connects to localhost on port 30000 and sends the piped input

<figure><img src="../../../.gitbook/assets/image (24).png" alt="echo &#x22;MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS&#x22; | nc localhost 30000"><figcaption></figcaption></figure>

The server responds with the password for the next level: <mark style="color:orange;">8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo</mark>

3. Access the next level:

```sh
ssh bandit15@bandit.labs.overthewire.org -p 2220
```

Enter the password when prompted.



## Lessons Learned

* Netcat `nc` is a versatile tool for reading from and writing to network connections
* Local services can be accessed using `localhost` as the hostname
* Piping commands can be used to send data to network services



\-- Othmane



