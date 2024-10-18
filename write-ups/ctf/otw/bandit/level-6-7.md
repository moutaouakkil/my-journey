# Level 6 → 7

## Level Goal

The password for the next level is stored <mark style="color:orange;">somewhere on the server</mark> and has all of the following properties:

* owned by user bandit7
* owned by group bandit6
* 33 bytes in size



## Write-Up

1. Find the file with the specified properties:

```sh
find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
```

* `find /`: Start searching from the root directory
* `-user bandit7`: look for files owned by user bandit7
* `-group bandit6`: Look for files owned by group bandit6
* `-size 33c`: Look for files exactly 33 bytes in size
* `2>/dev/null`: Redirect error messages to /dev/null to avoid cluttering the output

<figure><img src="../../../../.gitbook/assets/image (8).png" alt="find / -user bandit7 -group bandit6 -size 33c 2>/dev/null"><figcaption></figcaption></figure>

This command reveals <mark style="color:orange;">/var/lib/dpkg/info/bandit7.password</mark> as the target file.

2. Display the file content:

```sh
cat $(find / -user bandit7 -group bandit6 -size 33c 2>/dev/null)
```

<figure><img src="../../../../.gitbook/assets/image (9).png" alt="cat $(find / -user bandit7 -group bandit6 -size 33c 2>/dev/null)"><figcaption></figcaption></figure>

Or

```sh
cat /var/lib/dpkg/info/bandit7.password
```

<figure><img src="../../../../.gitbook/assets/image (10).png" alt="cat /var/lib/dpkg/info/bandit7.password"><figcaption></figcaption></figure>

The password retrieved: <mark style="color:orange;">morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj</mark>

3. Access the next level:

```sh
ssh bandit7@bandit.labs.overthewire.org -p 2220
```

Enter the password when prompted.



## Lessons Learned

* The `find` command can search based on multiple criteria simultaneously
* Redirecting errors to `/dev/null` helps clean up output
* System files can be located in unexpected places
* Precise file properties can be used to locate specific files



\-- Othmane



