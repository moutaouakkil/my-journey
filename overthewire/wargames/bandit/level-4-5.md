# Level 4 → 5

### Level Goal

The password for the next level is stored in the only human-readable file in the <mark style="color:orange;">inhere</mark> directory. Tip: if your terminal is messed up, try the `reset` command.



### Write-Up

#### Objective

Develop and execute a method to efficiently identify a human-readable file among multiple files, then extract its content to retrieve the password.



#### Solution

1. Navigate to the <mark style="color:orange;">inhere</mark> directory:

```sh
ls
cd inhere
```

<figure><img src="../../../.gitbook/assets/image (5).png" alt="ls &#x26; cd inhere"><figcaption></figcaption></figure>

2. Identify the human-readable file:

```sh
for i in $(ls); do file -i "./$i"; done;
```

<figure><img src="../../../.gitbook/assets/image (6).png" alt="for i in $(ls); do file -i &#x22;./$i&#x22;; done;"><figcaption></figcaption></figure>

This reveals <mark style="color:orange;">./-file07</mark> as the only text/plain file.

* `for i in $(ls)`: Loops through each file in the current directory
* `do`: Starts the loop body
* `file -i`: Runs the `file` command to each file, using `./` to handle filenames starting with '-'
* `done`: Ends the loop
* Overall: Identifies the file type of every file in the directory.

3. Display the contents of the identified file:

```sh
cat ./-file07
```

<figure><img src="../../../.gitbook/assets/image (7).png" alt="cat ./-file07"><figcaption></figcaption></figure>

The retrieved password: <mark style="color:orange;">4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw</mark>

4. Access the next level:

```sh
ssh bandit5@bandit.labs.overthewire.org -p 2220
```

Enter the password when prompted.



#### Summary

This level was pretty cool. It showed us how useful a bit of scripting can be when you're dealing with a bunch of files. Instead of opening each file one by one, we used a simple loop to do the work for us. It's the kind of trick that could save a ton of time in a real-world scenario, especially when file extensions are missing or misleading.



\-- Othmane



