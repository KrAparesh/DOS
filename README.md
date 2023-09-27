
# Design Of Operating System - LAB

## Day 01 - Basic Commands


  
  
### 1. Write the commands to create the following directory hierarchy. 
*DOS_RegNo -> DOS_Assigment1 -> Dir1*


Code: 

	mkdir DOS_2141011100
    cd DOS_2141011100
    mkdir DOS_Assignment1
    cd DOS_Assignment1
    mkdir Dir1

### 2. Write a cmd to create another directory with name Dir2 in Directory DOS_RegdNo and make Dir2 the current working directory. 

Code:

    mkdir Dir2
    cd Dir2

### 3. Write the cmd to delete the directory Dir2 when DOS_RegdNo. is your current working directory.
Code:
 
    rmdir Dir2

### 4. Write the cmds to create the file named as file1 using cat cmd inside Dir1. Write your name, regd, branch, semester and section in file1, then display the content of your file. 

Code:

    cd Dir1
    cat > file1.txt
    Name: Aparesh Kumar
    Regd No.: 2141011100
    Semester: 5th
    // hit ctrl + D
    cat file1.txt

### 5. Write a cmd to create a file named file2.txt using the cat command inside Dir1. Write your semester wise SGPA and display

Code: 

    cat > file2.txt
    Sem 1: X.XX
    Sem 2: X.XX
    Sem 3: X.XX
    Sem 4: X.XX
    // hit ctrl + D
    cat file2.txt

### 6. Create a file named as file3 storing the contents of file1 merged with the content of file2

Code: 

    cat file1.txt file2.txt > file3.txt
    cat file3.txt
   
Output:

    Name: Aparesh Kumar
    Regd No.: 2141011100
    Semester: 5th
    Sem 1: X.XX
    Sem 2: X.XX
    Sem 3: X.XX
    Sem 4: X.XX

### 7. Write a cmd to rename file2 .txt as mark_info.txt

Code: 

    mv file2.txt mark_info.txt

### 8. Write a cmd to copy the contents of file1.txt to reg_info.txt

Code: 

    cp file1.txt reg_info.txt

### 9. Write a cmd to delete file1.txt

Code:

    rm file1.txt
    
### 10. Write  a command to create a file named personal_info.txt inside Dir1 and write your name, registration number, and address in the file.

Code: 

    cat > personal_info.txt
    Name: Aparesh Kumar
    Regd No.: 2141011100
    Address: 221B, Baker Street

### 11. Check the output of the following commands:

1. `cmp reg_info.txt personal_info.txt`
	Output:
    `reg_info.txt personal_info.txt differ: byte 1, line 1`


2. `diff reg_info.txt personal_info.txt`
	Output:
` 1c1,3`

Note: The output contains more details, run the command on your terminal to view the exact output.

### 12. Write the command to count the number of lines, words, characters in a file mark_info.txt

Code: 

    wc mark_info.txt
	OR
	wc -l -w -c mark_info.txt

Output:

    4 16 76 mark_info.txt

### 13. Write the command to display the content of mark_info in reverse order

Code:
`tac mark_info.txt`

Output:
`SGPA 4th Sem: X.XX
SGPA 3rd Sem: X.XX
SGPA 2nd Sem: X.XX
SGPA 1st Sem: X.XX`

### 14. Write the command to count the number of files in the current working directory and display that number

Code:
`ls | wc -l`

Output:
`6`


### 15. Write the command to include all the files names present in the current working directory in a file named, file_list.txt without having file_list.txt as one of the included names.

`TODO`

---



## Class Notes


- **rmdir**:  Commands only removes empty directories.
With the *-p* option, *rmdir* not only removes the specified directory, but also it's parent directories.

* **cat**: When we want to store a few lines in a file, we can use the command 
`cat > file_name.txt`
Upon pressing *enter*, the file *file_name* is opened for us to type in our data. To save and exit, press *ctrl + D*

* **cmp**: When *cmp* is used for comparison between two files, it reports the location of the first mismatch if difference is found.

* **diff** : Used to display the difference in the files by comparing them line by line.
* **ls -l**: Outputs in it's first line the number of disc blocks that the files in the current directory have occupied.

---


## Day 02 - Basic Commands

## Class Notes

-**who**: It displays data about all the users who have logged into the system currently.

- **whoami**: It displays name of the user
- **date**: Displays the current date
- **cal**: Displays the calendar of the current month
- **umask**: It shows what permissions are supposed to be denied or suppressed.
		`Output: 0002`

---
### Inode:
- All entities in unix are treated as files and all information related to these files are stored in an *Inode* table in the disk
- For each file, there is an *Inode* entry in the table. Each entry contains details like 
 *1. Owner of the file*, 
 *2. Group to which the owner belongs*, 
 *3. Type of file*, 
 *4. File access permissions*, 
 *5. Date and time of last access*,  
 *6. Date and time of last modification*,  
 *7. Number of links to the file*, 
 *8. Size of the file* 
  *9. Addresses of blocks where the file is physically present*

We can obtain the Inode number associated with a file by using the cmd:
`ls -i <filename>`

---
### chmod:
 It is used for changing the default permissions of files and directories
`chmod +w <filename>` (Gives write permission to a file)

> Example:
> $touch file.txt
> $chmod -w file.txt
> $echo "Hey there!" > file.txt
> bash: file.txt: Permission denied
> $chmod +w file.txt
> $echo "Hey there!" > file.txt
> cat file.txt
> Hey there

To give `owner` write permission, use the cmd:
`chmod u+w file.txt`


## File and directory permissions

Three types of permissions - Read `(R)`, Write `(W)` and Execute `(X)` (RWX). 
 - R carries the value 4.
 - W carries the value 2.
 - X carries the value 1.

### **ls - l**
--- 
* Displays the permission of all sub-directories and fills within the current directory.
* A set of 9 characters denote these permissions. The permission string of a directory by default starts with a `d` and that of a file starts with a `-` sign.
* There are three types of users:
	* u -> Owner
	* g -> Group
	* o -> Outside

* `-rw` : **Allowed**: Read, Write | **Disallowed**: Execute

* All entities in `UNIX` are treated as files and all information related to these file are stored in an Inode (Index node) table.
* For each file there is an Inode entry in the table. 
