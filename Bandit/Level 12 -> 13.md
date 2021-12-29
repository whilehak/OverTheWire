# Level Goal
The password for the next level is stored in the file data.txt, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work using mkdir. For example: mkdir /tmp/myname123. Then copy the datafile using cp, and rename it using mv (read the manpages!)

# Solution

## Step 1: Make directory, copy data.txt into it, and reverse hexdump
```
mkdir /tmp/wolder
cp data.txt /tmp/wolder
cd /tmp/wolder
xxd -r data.txt wata.txt
```
## Step 2: Find file type, change extension, and decompress

| file type | Decompress Command |
|---|---|
| gzip (.gz) | gzip -d filename.gz |
| bzip2 (.bz2) | bzip2 -d filename.bz2 |
| tar (.tar) | tar xvf filename.tar | 

```
file filename
mv filename filename.extension
decompress command (see above)
```

Repeat this step until file type is ASCII text. Also, delete the folder.

Password: **8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL**
