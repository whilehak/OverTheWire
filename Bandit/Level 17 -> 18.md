# Level Goal
There are 2 files in the homedirectory: passwords.old and passwords.new. The password for the next level is in passwords.new and is the only line that has been changed between passwords.old and passwords.new

NOTE: if you have solved this level and see ‘Byebye!’ when trying to log into bandit18, this is related to the next level, bandit19

## Solution

To login in with the RSA private key, we create a text file named private.txt. By default, the file permissions is rw-r--r--. To use our private key, we must restrict access to the file using chmod.

Commands: 
```
chmod g-r private.txt
chmod o-r private.txt
```
Now, we can connect using this command: 
```
ssh -i private.txt bandit17@bandit.labs.overthewire.org -p 2220
```

To compare our 2 text files, we use diff.
```
bandit17@bandit:~$ diff passwords.old passwords.new
42c42
< w0Yfolrc5bwjS4qw5mq1nnQi6mF03bii
---
> kfBf3eYk5BPBRzwjqutbbfE887SVc5Yd
```
The password is in passwords.new.

Password: **kfBf3eYk5BPBRzwjqutbbfE887SVc5Yd**
