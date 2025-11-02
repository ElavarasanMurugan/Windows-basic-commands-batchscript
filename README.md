# Windows-basic-commands-batchscript
Ex08-Windows-basic-commands-batchscript

# AIM:
To execute Windows basic commands and batch scripting

# DESIGN STEPS:

### Step 1:

Navigate to any Windows environment installed on the system or installed inside a virtual environment like virtual box/vmware 

### Step 2:

Write the Windows commands / batch file . Save each script in a file with a .bat extension. Ensure you have the necessary permissions to perform the operations. Adapt paths as needed based on your system configuration.
### Step 3:

Execute the necessary commands/batch file for the desired output. 




# WINDOWS COMMANDS:
## Exercise 1: Basic Directory and File Operations
Create a directory named "my-folder"


## COMMAND AND OUTPUT


```bash
mkdir my-folder
```


![mkdir](./img/1.png)

Remove the directory "my-folder"

## COMMAND AND OUTPUT

```bash
rmdir my-folder
```

![rmdir](./img/2.png)


Create the file Rose.txt

## COMMAND AND OUTPUT

```bash
COPY CON Rose.txt
A clock in a office can never get stolen
Too many employees watch it all the time
^Z

dir Rose.txt
```

![copy](./img/3.png)

Create the file hello.txt using echo and redirection

## COMMAND AND OUTPUT

```bash
echo “hello world” > hello.txt
type hello.txt

```

![echo](./img/4.png)


Copy the file hello.txt into the file hello1.txt

## COMMAND AND OUTPUT


```bash
copy hello.txt hello1.txt

```

![copy](./img/5.png)

Remove the file hello1.txt

## COMMAND AND OUTPUT

```bash
del hello1.txt


```

![del](./img/6.png)

List out the file hello1.txt in the current directory

## COMMAND AND OUTPUT

```bash
dir hello1.txt
```

![dir](./img/7.png)

List out all the associated file extensions 

## COMMAND AND OUTPUT

```bash
assoc | more
```

![assoc](./img/8.png)

Compare the file hello.txt and rose.txt

## COMMAND AND OUTPUT

```bash
fc hello.txt Rose.txt

```

![fcc](./img/9.png)


## Exercise 2: Advanced Batch Scripting
Create a batch file named on the desktop. The batch file need to have a variable assigned with a desired name for ex. name="John" and display as "Hello, John".


```bash

@echo off
set name=John
echo Hello, %name%!
pause


```



## OUTPUT


![bat2](./img/10.png)

Create a batch file  on the desktop that checks whether a user-input number is odd or not. The script should:
Prompt the user to enter a number.
Calculate the remainder when the number is divided by 2.
Display whether the number is odd or not.
Ask the user if they want to check another number.
Repeat the process if the user enters Y, and exit with a thank-you message if the user enters N.
Handle invalid inputs for the continuation prompt (Y/N) gracefully.

```bash

@echo off
:main
set /p number=Enter a number: 
rem Calculate remainder when divided by 2
set /a remainder=%number% %% 2
if %remainder%==1 (
    echo %number% is an odd number.
) else (
    echo %number% is not an odd number.
)
:choice
set /p continue=Do you want to check another number? (Y/N): 
if /i "%continue%"=="Y" goto main
if /i "%continue%"=="N" goto end
echo Invalid choice, please enter Y or N.
goto choice
:end
echo Thank you for using the odd number checker!
pause

```

## OUTPUT


![bat2](./img/11.png)

Write a batch file that uses a FOR loop to iterate over a sequence of numbers (1 to 5) and displays each number with the label Number:. The output should pause at the end.


```bash

@echo off
for %%i in (1 2 3 4 5) do (
    echo Number: %%i
)
pause

```


## OUTPUT

![bat3](./img/12.png)



Write a batch script to check whether a file named sample.txt exists in the current directory. If the file exists, display the message sample.txt exists. Otherwise, display sample.txt does not exist. Pause the script at the end to view the result.

Instructions:
Use the IF EXIST conditional statement.
Make sure the script works for files located in the same directory as the batch file.
Use pause to keep the command window open after displaying the message.
Expected Output (if the file exists):

```bash
@echo off
if exist sample.txt (
    echo sample.txt exists.
) else (
    echo sample.txt does not exist.
)
pause

```

## OUTPUT

![bat4](./img/13.png)


Write a batch script that displays a simple menu with three options:
Say Hello – Displays the message Hello, World!
Create a File – Creates a file named newfile.txt with the content This is a new file
Exit – Exits the script with a goodbye message
The script should repeatedly display the menu until the user chooses to exit. Use goto statements to handle menu navigation.

```bash
@echo off
:menu
echo 1. Say Hello
echo 2. Create a File
echo 3. Exit
set /p choice=Choose an option: 
if "%choice%"=="1" goto hello
if "%choice%"=="2" goto createfile
if "%choice%"=="3" goto end

:hello
echo Hello, World!
goto menu

:createfile
echo Creating a file...
echo This is a new file > newfile.txt
goto menu
:end
echo Goodbye!
pause

```

## OUTPUT

![bat5](./img/14.png)


# RESULT:
The commands/batch files are executed successfully.

