# Level Goal
The password for the next level can be retrieved by submitting the password of the current level to port 30001 on localhost using SSL encryption.

Helpful note: Getting “HEARTBEATING” and “Read R BLOCK”? Use -ign_eof and read the “CONNECTED COMMANDS” section in the manpage. Next to ‘R’ and ‘Q’, the ‘B’ command also works in this version of that command…

## Soluton
To use SSL, we will use openssl s_client.

Command:
```
openssl s_client -connect localhost:30001
```
Submit last password for new password.

Password: **cluFn7wTiGryunymYOu4RcffSxQluehd**
