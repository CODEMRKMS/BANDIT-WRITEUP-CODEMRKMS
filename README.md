# CODEMRKMS WRITEUP FOR THE BANDIT

### Level 0;  
**Username:** *bandit0*  
**Password:** *bandit0*  
*Here is my approach to first level was to connect to SSH server using the above given credentials which i did by using the command line*
`ssh bandit0@bandit.labs.overthewire.org -p 2220`


### level 0 → level 1

**Now I will acesss the given problem statement**
```
$ ls
readme
$ cat readme
NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL
```
  
Flag for level 0-1 is
> NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL
> ## bandit1 → bandit2

**approach** ➼ Used cat cmd to read file

```bash
cat readme
```
bandit1 - 9rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi

## bandit2 → bandit3

**approach** ➼ Used cat cmd to read file with special char

```bash
cat ./-
```
bandit2 - aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG

## bandit3 → bandit4

**approach** ➼ Used cmd command to read file with spaces

```bash
cat "spaces in this filename"
```
bandit3 - 2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe

## bandit4 → bandit5

**approach** ➼Used cd to navigate into ./inhere dir

```bash
cd inhere
```
➼ And cat to read file

```bash
cat [filename]
```
bandit4 - lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR

## bandit5 → bandit6

**approach** ➼ Used cd to navigate into ./inhere dir

```bash
cd inhere
```
➼ Used find cmd to find file with 1033 bytes 

```bash
find * -size 1033c
```
➼ Used cat cmd to read file

```bash
cat maybehere07/.file2
```
bandit5 - P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU

## bandit6→ bandit7

**approach** ➼ Used cd to navigate to the top of tree(root folder)

➼ Used find with size,user,group options and removed all err 
    statements using 2>/dev/null

```bash
find -size 33c -user bandit7 -group bandit6 2>/dev/null
```
bandit6 - z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S

## bandit7 → bandit8

**approach** ➼ Used cat to read file and piped to grep to find the passwd

```bash
cat data.txt | grep millionth
```
bandit7 - TESKZC0XvTetK0S9xNwm25STk5iWrBvP

## bandit8 → bandit9

**approach** ➼ Used cat to read file 

```bash
cat data.txt
```
➼ Piped it to sort without any options

```bash
cat data.txt | sort
```
➼ Piped that to uniq with option -u to report unique lines

```bash
cat data.txt | sort | uniq -u
```
bandit8 - EN632PlfYiZbn3PhVK3XOGSlNInNE00t

## bandit9 → bandit10

**approach** ➼ Used strings to print out human readable texts

```bash
strings data.txt
```
➼ Piped it to grep to print out texts with multiple "==="

```bash
strings data.txt | grep ===
```
bandit9 - G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s

## bandit10 → bandit11

**approach** ➼ Used cat to read the file

```bash
cat data.txt
```
➼ Piped it to base64 with option -d to decode data

```bash
cat data.txt | base64 -d
```
bandit10 - 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM
## bandit11 → bandit12

**approach** ➼ Used cat to read the file

```bash
cat data.txt
```
➼ Used tr to replace all characters in set A-Z and a-z with 
    all corresponding characters in set N-Z,A-M and n-z,a-m
    well this is one way but i initially used rot13 cipher to get the answer

```bash
cat data.txt | tr "A-Za-z" "N-ZA-Mn-za-m"
```
bandit11 -  JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv

## bandit12 → bandit13

**approach** ➼ Used xxd with option -r to convert hexdump to data file

```bash
xxd -r data.txt > file
```
➼ Used file option to find the archive type and renamed the 
    original file with the respective archive extension and 
    respectively used tar,gzip,bzip2 to decompress the file

```bash
file [filename]

mv [filename1] [filename2].[archiveType]

tar -xf [filename].tar

gzip -d [filename].gz 

bzip2 -d [filename].bz
```
bandit12 - wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw

## bandit13 → bandit14

**approach** ➼ Retrieved ssh private keys and saved it under .ssh/id_rsa

➼ Changed the file permission to 600

```bash
chmod 600 id_rsa
```
➼ Signed in using the private key for user bandit14

```bash
ssh -i id_rsa bandit14@bandit.labs.overthewire.org -p 2220
```
➼ Navigated to /etc/bandit_pass and used cat to read the password

bandit14 - fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq

## bandit14 → bandit15

**approach** ➼ Used nc to connect to port 30000 using host as "localhost"

```bash
nc localhost 30000
```
bandit15 - jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

## bandit15 → bandit16

**approach** ➼ Used openssl to connect to "localhost" at port 30001

```bash
openssl s_client -connect localhost:30001
```
bandit16 - JQttfApK4SeyHwDlI9SXGR50qclOAil1# Level 16 → Level 17

