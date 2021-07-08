# Level Goal
The password for the next level is stored in the file data.txt in one of the few human-readable strings, preceded by several ‘=’ characters.

# Solution
We will use [strings](https://linux.die.net/man/1/strings) to print only readable strings. Since the output is not long, we can manully look for the password. 
```
strings data.txt
```
If we don't want to do that, we could grep for the equal sign. 
```
strings data.txt | grep =
```

Password: **truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk**
