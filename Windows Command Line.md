## Directory Navigation
Commands for viewing directories and moving directories around.

| Command | Explanation |
| ------- | ----------- |
| c:     | Change the current drive to the C:\ drive|
| d:     | Change the current drive to the D:\ drive|
| CD c:\path\to\my_folder| Change directory to c:\path\to\my_folder|
| CD ..  | Navigate to the parent directory of the current working directory|
| CD .\new_folder| Navigate to the folder new_folder located in the current working directory|
| CD /D d:\videos\ | Change the current drive to D:\ and access the folder videos on it|
| DIR | Display files and folders in the current directory|
| DIR /A c:\apps\ | Display files and folders in the directory c:\apps\|
| DIR /A:D | Display only folders (D: directories) |
| DIR /A:-D | Display only files (D: directories;-: not)|
| DIR /A:H | Display hidden files and folders |
| DIR /O | Display files and folders sorted alphabetically |
| DIR /O:S | Display files and folders sorted by file size from smallest to largest |
| DIR /O: -S | Display files and folders sorted by file size from largest to smallest
| DIR /B | Display only the names of files and folders in the current working directory |
| SORT | Take input from a source file/pipeline, sort its contents alphabetically (default: A to Z; in reverse Z to A), and display the output |
| SORT "C:\music\playlist.m3u | Sort the contect of C:\music\playlist.m3u line by line |
| DIR /B | SORT /R /O ZtoA.txt | List all file and folder names in the current working directory, sort them in reverse alphabetical order, and save the sorted output to a file ZtoA.txt |
| MOVE | Move a file or files|
| MOVE c:\f1\text.txt c:\f2 | Move a file text.txt from one folder c:\f1 to another folder c:\f2
| MD new_folderMAKEDIR new folder | Create a new folder called new_folder in the current directory |
| RD new_folderRMDIR new_folder | Delete the folder called new_folder in the current directory |
| TREE | Show the directory structure of a disk/folder |
| TREE "C:\Program Files" | Show the directory structure of the folder "Program Files" on the disk C:\ |
| TREE C:\ /F | Display the names of the files in each folder in the directory structure of the C:\drive |
| ATTRIB | Display/set the attributes of the files in the current directory
|ATTRIB +H +S +R myItem | Hide a file/folder myItem |
|ATTRIB -H -S -R myItem | Unhide a file/folder myItem |

## File Management
The following commands are for managing and manipulating files.

Like Unix, cmd supports pipelines: you may pass the output of a command to the next one by snadwiching the pipe character "|" between both.

| COMMAND | EXPLANATION |
| ------- | ----------- |
| COPY text.txt C:\work | Copy the file text.txt to folder with the path C:\work |
| DEL text.txt ERASE text.txt | Delete the file text.txt |
| REN text.txt script.bat RENAME text.txt script.bat | Rename a file text.txt to script.bat |
| REPLACE .\src\hello.text .\dest | Overwrite; replace a file named hello.txt in a local folder src with another hello.txt in a local folder dest, both files sharing the same name. (Warning: Don't specify .\dest\hello.txt anywhere here) |
| XCOPY | Copy files and directory trees to another folder. XCOPY is similar to COPY but with additional switches to specify the source and destination paths in detail |
| ROBOCOPY | Robust copying of files and directories: by default, such copying only occurs if the source and destination differ in time stamps or file sizes |
| EXPAND testData.cab | Decompresses the compressed .CAB cabinet file testData.cab |
| FC file1.ext file2.ext | Compare the contents of two files (file1.ext, file2.ext) and display non-matching lines |
| COMP file1.ext. file2.ext | Compare the contents of two files (file1.ext, file2.ext) and display non-matching items |
| FIND "python" in run.bat | Output every line that contains a text string (which you much enclose in quotation marks) "python" in the file run.bat |
| FIND /C "python" in run.bat | Count every line that contains a text string (which you must enclose in quotation marks) "python" in the file run.bat |
| PRINT resume.txt | Print contents of a file resume.txt |
| OPENFILES /QUERY| Query/display open files |
| OPENFILES /DISCONNECT | Disconnect files opened by network users |
| TYPE test.txt | Displays the contents of the file test.txt |
| TYPE playlist.m3u | SORT /unique /o C:\work\unique_play.m3u | Sort a file playlist.m3u and output only the unique values to a file C:\work\unique_play.m3u |
| MORE | Display contents of one or more files, one screen at time |
| ASSOC | Display or change the association between a file extension and file type |
| NOTEPAD | Open the Notepad application from cmd |
| NOTEPAD filename.ext | Open a file filename.ext in Notepad |

## Disk Management
Handle and automate tasks on cmd.

| COMMAND | EXPLANATION |
| ------- | ----------- |
| CHKDSK  | Check and repair disk problems (local disks only) |
| CHKDSK /F A: | Fix errors on A: drive | 
| CHKDSK /R A: | Recover data on A: drive |
| CHKDSK /X A: | Dismount drive A: |
| CIPHER /E classified | Encrypt the folder classified |
| CIPHER /D secret_recipe.txt | Decrypt the file secret_recipe.txt |
| DEFRAG | Disk Defragmentation |
| CHKNTFS | Display/modify disk-checking on startup |
| COMPACT | Display/change the compression of files in NTFS partitions
| CONVERT | Convert FAT disk volume to NTFS |
| DISKPART | Display and adjust disk partition properties |
| FORMART | Format the disk |
| FSUTIL | File system management |
| LABEL d:x | Rename disk D:\ to X:\ |
| SUBST p: c:\taxes | Assign drive P:\ to the local folder c:\taxes |
| SUBST p: /D | Remove the path represented by P:\ |
| RECOVER d:\data.dat | Recover a file data.dat from a bad or defective disk D:\ |
| VOL | Display current disk volume label and serial number |
| POWERCFG | Control power settings and configure Hiberante/Standby modes |
|SFC /SCANNOW | Scan and update protected system files |

## System Information and Networking
Commands are helpful in troubleshooting computers and computer networks.

| COMMAND | EXPLANATION |
| ------- | ----------- |
| VER | Display the current operating system version |
| SYSTEMINFO | List system configuration |
| HOSTNAME | Show the computer's hostname on the network |
| DRIVERQUERY | Show all installed device drivers |
| DATE | Display/set system time |
| TIME | Display/set system time |
| GPRESULT | Display Resultant Set of Policy (RSoP) information for a remote user and computer |
| GPUPDATE | Update group policies |
| IPCONFIG | Display Windows IP network configurations |
| IPCONFIG /release | Release your current local IP address |
| IPCONFIG /renew | Request a new local IP address |
| IPCONFIG /flushdns | Reset the contects of the DNS client resolver cache |
| PING google.com | Send ICMP requests to the target google.com and check host availability |
| PATHPING | Trace route and provide network latency and packet loss for each router and link in the path |
| NET | Provide various network services |
| NET use M: \\gameServ /user:"ReadyPlayerTwo" player2 | Assign as disk M:\the path \\gameServ, logging in as "ReadyPlayerTwo" and password "player2" |
| TRACERT | Find the IP address of any remote host |
| NSLOOKUP | FIND IP addresses on a nameserver |
| ROUTE | Manipulate network routing tables |
| ROUTE PRINT | Display network details |
| ARP -A | List IP addresses and corresponding physical addresses (Address Resolution Protocol) |
| NETSH | Configure network interfaces, Windows firewall, routing and remote access |
| NETSTAT | Display current TCP/IP network connections and protocol statistics |
| GETMAC | Show all MAC addresses of the network adapters |

## Process Management
Commands are for Task Manager-like functions. Call variables in arithmetic or logical expressions by enclosing each with two "%" sings (e.g., "%a%").

| COMMAND | EXPLANATION |
| ------- | ----------- |
| SCHTASKS | Create/edit a job on Task Scheduler. Use this to create scheduled tasks in Disk Management |
| SET | List environment variables |
| PATH | Display/change the list of folders stored in the %PATH% environment variable |
| SHUTDOWN /R | Restart the computer |
| SHUTDOWN /S /T 60 | Shut down the computer 60 seconds from now |
| TASKLIST | List running tasks |
| TASKLIST /SVC / Show services related to each task |
| TASKKILL | End one or more tasks |
| TASKKILL /IM "msedge.exe" | Terminate all Microsoft Edge instances |
| TASKKILL /PID 10736 | Terminate process with PID of 10736 |
| REGREGEDIT | Registry Editor |
| RUNAS /USER:user2 program1 | Execute a program program1 as another user user2 |
| POWERSHELL | Open a Powershell instance |

## Batch Scripting
Commands for constructing and debugging batch scripts (.bat). To suppress the output of a certain command, add @ in front of it, e.g., @echo off.

| COMMAND | EXPLANATION |
| ------- | ----------- |
| REM comment ..., :comment... | Prefix for the single-line comment "comment ..." |
| GOTO end <comment_block> :end | Format of multi-line comments represented by <comment_block> enclosed by delimiters end and :end |
| SET /A c = %a% + %b% | Assign the arithmetic expression a+b to the variable c |
| ^ | Escape character | 
| some_command > output.txt | Redirect output of some_command to a file output.txt | 
| ? | Wildcard representing one character | 
| * | Wildcard representing multiple characters |
| & | Introduce a new command on the same line |
| TIMEOUT 3600 | Tell the command prompt to sleep for 3600 seconds (=1 hour) |
| PAUSE | Prompt the user to continue |
| CHOICE | Prompt the user to pick an on-screen option |
| CHOICE /T 15 /C ync /CS /D y /M "Press y=Yess, no=No, c=canecl:" | You have 15 seconds to press Y, N, or C keys without capitalization, defaulting to "y" if tiime runs without a decision |
| CLS | Clear screen |
| CMD | Restart Windows command prompt windows |
| COLOR | Set text and background color of cmd | 
| ECHO ON | Display each command executed |
| ECHO OFF | Only display command output |
| ECHO a string of characters | Display a string of characters |
| HELP | Dispaly help |
| PROMPT topSecret^>$$ | Changes the command line prompt to topSecret>$ for the current session |
| PROMPT | Reset the command line prompt to default |
| START X | Start/open a program/document X in a new windows |
| TITLE top Secret | Set the title of the current session of Windows command prompt to top Secret |
| /? | Add thisto the end of any command word to get help on the command, e.g., CD/?=manual for CD (change directory) command |
| EXIT | Exists the commandd line |

## FLOW Control
Note the condition is a Boolean expression e.g., %a%==5.

| Conditional | Syntax |
| ------- | ----------- |
| If | IF (condition) do_something |
| If-else | IF (condition (do something) ELSE (do_something_else) |
| Nested if | IF (condition) IF (condition2) do_something |
| Infinite loop | :marker do something GOTO marker |
| While loop | : marker IF (condition) ( do_something GOTO :marker ) |
