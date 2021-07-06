# Level Goal
The password for the next level is stored in the only human-readable file in the inhere directory. Tip: if your terminal is messed up, try the “reset” command.

# Solution
Inside the *inhere* directory, we see 10 files. They are *-file00*, *-file01*, *-file02*, *-file03*, *-file04*, *-file05*, *-file06*, *-file07*, *-file08*, and *-file09*. Since these files have a dash in their names, we need to type their relative path to read them. The command is 
```
cat ./filename
```
The period means the current directory and the slash separates directories and files. Using this command, we print the contents of the files. All the files except *-file07* has unusual characters. The password is in *-file07*.

Password: **koReBOKuIDDepwhWk7jZC0RTdopnAYKh**
