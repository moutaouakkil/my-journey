# Level 3 → 4

## Level Goal

The password for the next level is stored in a hidden file in the <mark style="color:orange;">inhere</mark> directory.



## Write-Up

1. List the contents of the current directory to verify the existence of <mark style="color:orange;">inhere</mark> directory:

```sh
ls
```

<figure><img src="../../../.gitbook/assets/image (3) (1).png" alt="ls"><figcaption></figcaption></figure>

2. Navigate to the <mark style="color:orange;">inhere</mark> directory and list all files, including hidden ones:

```sh
cd inhere
ls -a
```

<figure><img src="../../../.gitbook/assets/image (1) (1) (1).png" alt="cd inhere &#x26; ls -a"><figcaption></figcaption></figure>

This reveals the presence of a hidden file named <mark style="color:orange;">...Hiding-From-You</mark>.

3. Display the contents of the hidden file:

```sh
cat ...Hiding-From-You
```

<figure><img src="../../../.gitbook/assets/image (3) (1) (1).png" alt="cat ...Hiding-From-You"><figcaption></figcaption></figure>

This command reveals the password: <mark style="color:orange;">2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ</mark>

4. Access the next level using the obtained password:

```sh
ssh bandit4@bandit.labs.overthewire.org -p 2220
```

Enter the password when prompted.



## Lessons Learned

This level teaches us about hidden files in Unix systems. We had to find a secret password in a hidden file inside the <mark style="color:orange;">inhere</mark> directory. The trick was using `ls -a` to see all files, including the hidden ones that start with a dot.



\-- Othmane



