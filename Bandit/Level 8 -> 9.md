# Level Goal
The password for the next level is stored in the file data.txt and is the only line of text that occurs only once

# Solution
For this challenge, we will be using [uniq](https://man7.org/linux/man-pages/man1/uniq.1.html). We will be specifically using the *-u* argument which "only prints the unique lines." However if we run "uniq -u" we will not get our password. 

The man page states "Note: 'uniq' does not detect repeated lines unless they are adjacent.  You may want to sort the input first, or use 'sort -u'without 'uniq'."
So, we will use [sort](https://man7.org/linux/man-pages/man1/sort.1.html) and pipe the output into *uniq*. The command is 
```
sort | uniq -u
```
Password: **UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR**
