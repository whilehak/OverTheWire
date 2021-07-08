# Level Goal
The password for the next level is stored in the file data.txt, which contains base64 encoded data

# Solution
The data is *VGhlIHBhc3N3b3JkIGlzIElGdWt3S0dzRlc4TU9xM0lSRnFyeEUxaHhUTkViVVBSCg==*. We could use an online website to decrypt this. Or we could use the [base64](https://linux.die.net/man/1/base64) command. 
```
base64 -d data.txt
```
The output is "The password is IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR"

Password: **IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR**
