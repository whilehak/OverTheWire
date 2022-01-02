# Level Goal

There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).

NOTE: Try connecting to your own network daemon to see if it works as you think

## Solution
To complete this level, we need to use 2 terminals.

In the first terminal, we use the setuid binary to make a connection to a port.

In the second terminal, we set up a netcat listener on a random port number (ex: 5000). We input our last password into it and get our new one.

Terminal 1
```
bandit20@bandit:~$ ls -l
total 12
-rwsr-x--- 1 bandit21 bandit20 12088 May  7  2020 suconnect
bandit20@bandit:~$ ./suconnect 5000
Read: GbKksEFF4yrVs6il55v6gwY5aVje5f0j
Password matches, sending next password
```

Terminal 2
```
bandit20@bandit:~$ nc -lp 5000
GbKksEFF4yrVs6il55v6gwY5aVje5f0j
gE269g2h3mw3pwgrj0Ha9Uoqen1c9DGr
```

Password: **gE269g2h3mw3pwgrj0Ha9Uoqen1c9DGr**
