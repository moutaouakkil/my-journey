# Level 8 → 9

## Level Goal

The password for the next level is stored in the file <mark style="color:orange;">data.txt</mark> and is the only line of text that occurs only once



## Write-Up

1. List the content of the current directory:

```sh
ls
```

<figure><img src="../../../../.gitbook/assets/image (11).png" alt="ls"><figcaption></figcaption></figure>

This confirms the presence of the <mark style="color:orange;">data.txt</mark> file.

2. Display the content of the data.txt file:

```sh
cat data.txt
```

<figure><img src="../../../../.gitbook/assets/image (12).png" alt="cat data.txt"><figcaption></figcaption></figure>

3. Search for the line of text that occurs only once:

```sh
sort data.txt | uniq -u
```

<figure><img src="../../../../.gitbook/assets/image (13).png" alt="sort data.txt | uniq -u"><figcaption></figcaption></figure>

* `sort data.txt`: Sorts the lines alphabetically
* `|`: Pipes the output to the next command
* `uniq -u`: Filters for unique lines

The password retrieved: <mark style="color:orange;">4CKMh1JI91bUIZZPXDqGanal4xvAg0JM</mark>

4. Access the next level:

```sh
ssh bandit9@bandit.labs.overthewire.org -p 2220
```

Enter the password when prompted.



## Lessons Learned

* The `sort` command is useful for organizing data for further processing
* `uniq -u` filters for lines that appear only once in the input
* `Piping commands` together can create powerful data processing workflows
* Sometimes finding unique information requires multiple steps of data manipulation



\-- Othmane



