# Level Goal
The password for the next level is stored in a hidden file in the inhere directory.

# Solution
We can go inside the *inhere* directory using this command:
```
cd inhere
```
When we type 
```
ls
```
inside the directory, the hidden file is not printed. 
To print all files including hidden ones, we use
```
ls -a
``` 
This command lists all files, including files that start with a period. Files that start with a period means that it is hidden.
We see a file named _.hidden_, so we use
```
cat .hidden
```
to print the password.

Password: **pIwrPrtPN36QITSp3EQaw936yaFoFgAB**
