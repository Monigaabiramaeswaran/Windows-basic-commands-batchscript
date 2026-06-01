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
```
mkdir my-folder
```
<img width="387" height="53" alt="image" src="https://github.com/user-attachments/assets/ef20c883-ac55-42d9-9bb4-1d4306b59408" />

## COMMAND AND OUTPUT

Remove the directory "my-folder"
```
rmdir my-folder
```
<img width="408" height="50" alt="image" src="https://github.com/user-attachments/assets/d95c9b77-8a2d-4964-9b5a-e0ff4ea5e96e" />

## COMMAND AND OUTPUT


Create the file Rose.txt
```
type nul > Rose.txt
```
<img width="439" height="55" alt="image" src="https://github.com/user-attachments/assets/bf4f6a54-551c-430d-bfb4-4c877a8cd8d4" />

## COMMAND AND OUTPUT
```
echo Hello World > hello.txt
```
<img width="558" height="52" alt="image" src="https://github.com/user-attachments/assets/f420cca4-0ba6-4837-b0db-bd092d6f3445" />


Create the file hello.txt using echo and redirection

## COMMAND AND OUTPUT

Copy the file hello.txt into the file hello1.txt
```
copy hello.txt hello1.txt
```
<img width="497" height="69" alt="image" src="https://github.com/user-attachments/assets/3ce6842a-4895-4b12-8cc1-d4ee81ed9c5a" />

## COMMAND AND OUTPUT

Remove the file hello1.txt
```
del hello1.txt
```
<img width="390" height="49" alt="image" src="https://github.com/user-attachments/assets/0fe7e8fc-9fac-4f86-8c45-63b86189b1e1" />


## COMMAND AND OUTPUT

List out the file hello1.txt in the current directory
```
dir hello1.txt
```
<img width="438" height="182" alt="image" src="https://github.com/user-attachments/assets/31341b60-6237-48f9-be40-2b3f796b0482" />

## COMMAND AND OUTPUT

List out all the associated file extensions 
```
assoc
```
<img width="625" height="880" alt="image" src="https://github.com/user-attachments/assets/5ff4b0be-a3ed-49a8-8d69-e015c0572305" />

## COMMAND AND OUTPUT
```
fc hello.txt Rose.txt
```
<img width="536" height="159" alt="image" src="https://github.com/user-attachments/assets/98a5be14-c4ea-474a-9c0b-c6fe95ee8e3a" />


Compare the file hello.txt and rose.txt

## COMMAND AND OUTPUT

## Exercise 2: Advanced Batch Scripting
Create a batch file named on the desktop. The batch file need to have a variable assigned with a desired name for ex. name="John" and display as "Hello, John".

```
@echo off
set name=John
echo Hello, %name%
pause
```



## OUTPUT

<img width="494" height="77" alt="image" src="https://github.com/user-attachments/assets/9dbbc44e-50f1-469a-8652-860e6e96a4d5" />


Create a batch file  on the desktop that checks whether a user-input number is odd or not. The script should:
Prompt the user to enter a number.
Calculate the remainder when the number is divided by 2.
Display whether the number is odd or not.
Ask the user if they want to check another number.
Repeat the process if the user enters Y, and exit with a thank-you message if the user enters N.
Handle invalid inputs for the continuation prompt (Y/N) gracefully.
```
@echo off
:START
set /p num=Enter a number: 

set /a rem=%num% %% 2

if %rem%==1 (
    echo The number %num% is ODD
) else (
    echo The number %num% is NOT ODD
)

:CHOICE
set /p choice=Do you want to check another number? (Y/N): 

if /I "%choice%"=="Y" goto START
if /I "%choice%"=="N" goto END

echo Invalid choice. Please enter Y or N.
goto CHOICE

:END
echo Thank you!
pause
```


## OUTPUT

<img width="656" height="202" alt="image" src="https://github.com/user-attachments/assets/44e4ee61-994e-4595-ae3e-1273de3adc2c" />



Write a batch file that uses a FOR loop to iterate over a sequence of numbers (1 to 5) and displays each number with the label Number:. The output should pause at the end.

```
@echo off
for %%i in (1 2 3 4 5) do (
    echo Number: %%i
)
pause
```


## OUTPUT

<img width="457" height="165" alt="image" src="https://github.com/user-attachments/assets/db12be81-8f14-4f72-b82e-62ef8dd540e1" />



Write a batch script to check whether a file named sample.txt exists in the current directory. If the file exists, display the message sample.txt exists. Otherwise, display sample.txt does not exist. Pause the script at the end to view the result.

Instructions:
Use the IF EXIST conditional statement.
Make sure the script works for files located in the same directory as the batch file.
Use pause to keep the command window open after displaying the message.
Expected Output (if the file exists):
```
@echo off
if exist sample.txt (
    echo sample.txt exists
) else (
    echo sample.txt does not exist
)
pause
```
## OUTPUT

<img width="422" height="52" alt="image" src="https://github.com/user-attachments/assets/9878b37e-3c4f-409c-bcad-ce566cb20c96" />

Write a batch script that displays a simple menu with three options:
Say Hello – Displays the message Hello, World!
Create a File – Creates a file named newfile.txt with the content This is a new file
Exit – Exits the script with a goodbye message
The script should repeatedly display the menu until the user chooses to exit. Use goto statements to handle menu navigation.
```
@echo off
:MENU
cls
echo ===== MENU =====
echo 1. Say Hello
echo 2. Create a File
echo 3. Exit
echo =================
set /p choice=Enter your choice: 

if "%choice%"=="1" goto HELLO
if "%choice%"=="2" goto CREATE
if "%choice%"=="3" goto EXIT

echo Invalid choice!
pause
goto MENU

:HELLO
echo Hello, World!
pause
goto MENU

:CREATE
echo This is a new file > newfile.txt
echo File created successfully!
pause
goto MENU

:EXIT
echo Goodbye!
pause
exit
```

## OUTPUT
<img width="410" height="192" alt="image" src="https://github.com/user-attachments/assets/767e0cce-bc2f-4dfb-a86c-62d8f6446433" />


<img width="441" height="203" alt="image" src="https://github.com/user-attachments/assets/b6e05dc8-6e9e-4742-9861-5b437961abb3" />


<img width="431" height="197" alt="image" src="https://github.com/user-attachments/assets/18f3b7e4-711f-4a4e-8a2a-99fc006071c0" />

# RESULT:
The commands/batch files are executed successfully.

