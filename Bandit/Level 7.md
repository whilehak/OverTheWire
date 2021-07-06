# Level Goal
The password for the next level is stored somewhere on the server and has all of the following properties:
* owned by user bandit7
* owned by group bandit6
* 33 bytes in size

# Solution
We will use *find* again. We can use the [manual page](https://man7.org/linux/man-pages/man1/find.1.html) or this [website](https://www.cyberciti.biz/faq/how-do-i-find-all-the-files-owned-by-a-particular-user-or-group/) to learn about it.

The argument to find all files owned by a user is *-user \[username]*. Similarly, the arguement to find all files owned by a group is *-group \[group name]*. 
Since this password is located somewhere on the server and not limited to a particular directory, we will search in the root directory. 
The command is 
```
find -user bandit7 -group bandit6 -size 33c
```

We see that we are not allowed to look at some directories because we don't have access to them. However, we see that we are allowed to look at one file named *bandit7.password*. The file path is *./var/lib/dpkg/info/bandit7.password*. 

Password: **HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs**
