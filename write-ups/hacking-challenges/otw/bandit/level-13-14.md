# Level 13 → 14

## Level Goal

The password for the next level is stored in <mark style="color:orange;">/etc/bandit\_pass/bandit14</mark> and can only be read by user bandit14. For this level, you don’t get the next password, but you get a private SSH key that can be used to log into the next level. Note: localhost is a hostname that refers to the machine you are working on



## Write-Up

1. List the content of the current directory:

```sh
ls
```

<figure><img src="../../../../.gitbook/assets/image (4) (1).png" alt="ls"><figcaption></figcaption></figure>

2. Display the content of the <mark style="color:orange;">sshkey.private</mark> file:

```sh
cat sshkey.private
```

<figure><img src="../../../../.gitbook/assets/image (1) (1) (1) (1) (1).png" alt="cat sshkey.private"><figcaption></figcaption></figure>

This reveals <mark style="color:orange;">sshkey.private</mark> contains an RSA private key.

3. Use the private key to SSH into <mark style="color:orange;">bandit14</mark> on localhost:

```sh
ssh -i sshkey.private -p 2220 bandit14@localhost
```

* `-i sshkey.private`: Specifies the private key file to use for authentication
* `-p 2220`: Specifies the port for the OverTheWire game server
* `bandit14@localhost`: Connects to user bandit14 on the same machine

<figure><img src="../../../../.gitbook/assets/image (3) (1) (1) (1).png" alt="ssh -i sshkey.private -p 2220 bandit14@localhost"><figcaption></figcaption></figure>

Note: Are you sure you want to continue connecting (yes/no/\[fingerprint])? Yes

<figure><img src="../../../../.gitbook/assets/image (4) (1) (1).png" alt="bandit14 accessed"><figcaption></figcaption></figure>

<mark style="color:orange;">bandit14</mark> accessed.

4. Once logged in as bandit14, access the password file:

```sh
cat /etc/bandit_pass/bandit14
```

<figure><img src="../../../../.gitbook/assets/image (22).png" alt="cat /etc/bandit_pass/bandit14"><figcaption></figcaption></figure>

The retrieved password: <mark style="color:orange;">MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS</mark>

5. Log out of the bandit14 session to return to bandit13:

```sh
exit
```

<figure><img src="../../../../.gitbook/assets/image (23).png" alt="exit"><figcaption></figcaption></figure>

6. Access the next level:

```sh
ssh bandit14@bandit.labs.overthewire.org -p 2220
```

Enter the password when prompted.



## Lessons Learned

* SSH keys can be used as an alternative to password authentication
* Different user accounts can have varying levels of access to files on a system
* Private keys should be kept secure and protected, as they grant access without a password



\-- Othmane



