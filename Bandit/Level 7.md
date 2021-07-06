# Level Goal
The password for the next level is stored somewhere on the server and has all of the following properties:
* owned by user bandit7
* owned by group bandit6
* 33 bytes in size

# Solution
We will use *find* again. We can use the [manual page](https://man7.org/linux/man-pages/man1/find.1.html) or this [website](https://www.cyberciti.biz/faq/how-do-i-find-all-the-files-owned-by-a-particular-user-or-group/).

The argument to find a file owned by a user is *-user \[username]*
