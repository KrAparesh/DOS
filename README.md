# Shell Scripting

The shell is otherwise called the command interpreter. It interprets the command and gives them to the kernel which ultimately executes them.

**Shell Script**: It is a list of commands, representing a todo list of multiple jobs that a user asks a program to conduct. 

## Shell Commands


---
## Questions
Q1. Write a shell script which takes a user input: Name, regd. no, and prints out the name and regd. no.

Code:
`$cat > SS2`
`echo "What is your name?"
read name_var
echo "What is your registration number?"
read regd_var
echo "Hello $name_var, Your registration number is $regd_var"`

`$sh SS2`

Output:

`What is your name?
Aparesh Kumar
What is your registration number?
2141011100
Hello Aparesh Kumar, Your registration number is 2141011100
`

---
Q2. Write a shell script named as *program* for merging the contents of files *a.txt, b.txt, c.txt* sort them and save the result in a file called *result* and display the sorted output on the screen.
NOTE: *a.txt, b.txt, c.txt* contain numerical value. Make the script an executable file and run it using the command as it's name only.

Code:

`echo "Merging files: a.txt, b.txt, c.txt to result"
cat a.txt b.txt c.txt > result
echo "Sorting:"
sort -n result
chmod u+x program`

---
Q3. Write a shell script named as *systemInfo* that will display the information about the 
* *login name* of the user, 
* *name of the UNIX system* used by the user, 
* *type of shell*, 
* *path of the current working directory*,
* *List of files contained in current working directory*

Make the script an executable file and run it as a command using it's name only.

Code:

`echo "Login name: $LOGNAME"
echo "UNIX System name:"
uname -n
echo "Shell name: $0"
echo "current directory: $PWD"
echo "List of files:" 
ls -l`

---
Q4. Write a shell script named *dtCal* for displaying both the system date and calendar for specific month in the given format:
`Date: <Specific Date>`
`Calendar: <Current Calendar>`

Make the script an executable file and run it as a command using it's name only.

Code:
`date_var=$(date)
cal_var=$(cal)
echo "Date: $date_var"
echo "Calendar: $cal_var"`
