# Level Goal
The password for the next level is stored in the file data.txt, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions

# Solution
The ciphertext in the file is "Gur cnffjbeq vf 5Gr8L4qetPEsPk8htqjhRK8XSP6x2RHh" and it has been encrypted with the rot13 cipher. 
We can use an [online rot13 decoder](https://rot13.com) or we can use [tr](https://linuxcommand.org/lc3_man_pages/tr1.html). This [website](https://askubuntu.com/questions/1085069/how-can-i-decode-a-file-where-each-letter-has-been-replaced-with-the-letter-13-l) has the command for it. 
```
echo "Gur cnffjbeq vf 5Gr8L4qetPEsPk8htqjhRK8XSP6x2RHh" | tr "$(echo -n {A..Z} {a..z} | tr -d ' ')" "$(echo -n {N..Z} {A..M} {n..z} {a..m} | tr -d ' ')"
```
The decrypted text is "The password is 5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu"

Password: **5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu**
