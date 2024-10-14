# Level 12 → 13

## Level Goal

The password for the next level is stored in the file <mark style="color:orange;">data.txt</mark>, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work. Use mkdir with a hard to guess directory name. Or better, use the command “mktemp -d”. Then copy the datafile using cp, and rename it using mv (read the manpages!)



## Write-Up

1. Create a temporary directory and copy the file:

```sh
mktemp -d
cp data.txt /tmp/tmp.83OGZ2BEJL
cd /tmp/tmp.83OGZ2BEJL
```

<figure><img src="../../../.gitbook/assets/image (1).png" alt="mktemp -d &#x26; cp data.txt /tmp/tmp.83OGZ2BEJL &#x26; cd /tmp/tmp.83OGZ2BEJL"><figcaption></figcaption></figure>

2. Reverse the hexdump:

```sh
xxd -r data.txt > data
```

<figure><img src="../../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

3. Determine the file type and decompress repeatedly:

```sh
file data
mv data data.gz
gzip -d data.gz
file data
mv data data.bz2
bzip2 -d data.bz2
file data
mv data data.gz
gzip -d data.gz
file data
tar -xvf data
file data5.bin
tar -xvf data5.bin
file data6.bin
mv data6.bin data6.bz2
bzip2 -d data6.bz2
file data6
tar -xvf data6
file data8.bin
mv data8.bin data8.gz
gzip -d data8.gz
file data8
```

<figure><img src="../../../.gitbook/assets/image (3).png" alt="Determined the file type and decompressed repeatedly"><figcaption></figcaption></figure>

4. Finally, the password was revealed:

```sh
cat data8
```

<figure><img src="../../../.gitbook/assets/image (4).png" alt="cat data8"><figcaption></figcaption></figure>

The retrieved password: <mark style="color:orange;">FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn</mark>

5. Access the next level:

```sh
ssh bandit13@bandit.labs.overthewire.org -p 2220
```

Enter the password when prompted.



## Lessons Learned

* Hexdumps can be reversed using the `xxd` command
* File types can be determined using the `file` command
* Different compression methods require different decompression tools (`gzip`, `bzip2`, `tar`)
* Creating temporary directories is useful for working with complex file manipulations
* Multiple layers of compression require patience and systematic approach to unravel



\-- Othmane



