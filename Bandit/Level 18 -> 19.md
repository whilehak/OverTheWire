# Level Goal

The password for the next level is stored in a file readme in the homedirectory. Unfortunately, someone has modified .bashrc to log you out when you log in with SSH.

## Solution

We can append commands to the end of our ssh login command.
Command:
```
ssh bandit18@bandit.labs.overthewire.org -p 2220 cat readme
```

Password: **IueksS7Ubh8G3DCwVzrTd8rAVOwq3M5x**
