# Level Goal
The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:
* human-readable
* 1033 bytes in size
* not executable

# Solution

Inside the *inhere* directory, we see 20 directories. They are named *maybehere00*, *maybehere01*, *maybehere02*, ... *maybehere19*. Inside each, there are several files. Going through all the files in each directory would be very time-consuming. 

So, we will be using [find](https://man7.org/linux/man-pages/man1/find.1.html). We can use the *-size* argument to find a file of a certain size. 
Command:
```
find -size 1033c
```
The manual page has detailed information about the argument. 
