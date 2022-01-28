# ImportantCommands

# Table of Contents
1. [Nmap](#Nmap)
2. [DirBister](#DirBuster)
3. [Gobuster](#Gobuster)
4. [Nikto](#Nikto)
5. [NC](#NC)
    1. [Listen_For_Reverse_Shell](#Listen_For_Reverse_Shell)
6. [Hydra](#Hydra)
    1. [Check_if_Content_is_not_on_page](#Check_if_Content_is_not_on_page)
    1. [Check_for_redirect](#Check_for_redirect)
7. [Usefull Linux Commands](#Usefull_Linux_Commands)

## Nmap
Nmap Command 
```diff
nmap -sV -sC IP
```

```diff
# -sV: Probe open ports to determine service/version info  
#-sC: equivalent to --script=default  
# -O: Enable OS detection  
#  -oN/-oX/-oS/-oG <file>: Output scan in normal, XML, s|<rIptkIddi3,and Grepable format, respectively, to the givenfilename.
```

## DirBuster
```
dirb http://IP
```
## Gobuster
```diff
gobuster dir -u IP -w /usr/share/wordlists/dirb/big.txt
```
```diff
# -w, --wordlist string   Path to the wordlist
# -o, --output string     Output file to write results to (defaults to stdout)
# -t, --threads int       Number of concurrent threads (default 10)
```

## Nikto
```diff
nikto -h 10.10.241.154
```
```diff
# -port+    Port to use (default 80)
# -output+  Write output to this file
```

## NC

### Listen_For_Reverse_Shell
```diff
nc -lnvp 1234 
```
```diff
# -l                      listen mode, for inbound connects
# -n                      numeric-only IP addresses, no DNS
# -v                      verbose [use twice to be more verbose]
# -p port                 local port number
# -u                      UDP mode
# -s addr                 local source address
# -o file                 hex dump of traffic
# -c shell commands       as `-e'; use /bin/sh to exec [dangerous!!]
# -e filename             program to exec after connect [dangerous!!]
```

## Hydra
### Check_if_Content_is_not_on_page
```diff
hydra -L /wordlistdir/.../user.dic -p 1223456789 IP http-post-form "/wp-login:log=^USER^&pwd=^PASS^&wp-submit=Log+In&redirect_to=10.10.241.154/wp-admin/&testcookie=1:Invalid username"
```
```diff
- -l = static username
- -L = a list of Usernames
- -p = static PW
- -P = a list of Passwords
+ after "http-post-form" comes a capured Post request (From Burbsuite...)
+ use ^USER^ and ^PASS^!
+ after ":" comes the string whitch shouldn´t be on the page  
```
### Check_for_redirect
```diff
hydra -P /wordlistdir/.../pass.dic -l Elliot 10.10.241.154 http-post-form "/wp-login:log=^USER^&pwd=^PASS^&wp-submit=Log+In&redirect_to=10.10.241.154/wp-admin/&testcookie=1:S=302" -I
```
```diff
- -l = static username
- -L = a list of Usernames
- -p = static PW
- -P = a list of Passwords
+ after "http-post-form" comes a capured Post request (From Burbsuite...) 
+ use ^USER^ and ^PASS^! 
+ ":S=302" check for redirect 
```
[Common HTML error codes](https://kb.iu.edu/d/bfrc)
# Color

```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```

# Syntax highliting

```bash
  echo "hello world"
``` 

```python3.9
    import os

    os.system("ls -la")
```

# DV2
## Common commands
### PWD
```diff
pwd #shows current dir  
```
### LS
```diff
ls #shows files in a folder
+ -l # use a long listing format
+ -a # list all
! drwx rwx rwx # d = dir;
```
### CD
```diff
cd "Path"
+ ~ = home dir
+ .. = dir "over" current dir
+ . = current dir
```
### HISTORY
```diff
@@ history #shows command history @@
```
### CAT
```diff
cat
```
### .
```diff
.programmname #starts a programm
ctrl+c #stops a programm
```
### PS
```diff
ps #shows processes on current user
+ -ef #shows all processes

UID = user
PID = Process ID
PPID = if a process started a new Process
TIME = running time
STIME =
CMD = the command which started the Process
[process] = kernel process
```
### KILL
```diff
kill "PID"# sends stop message to process
+ -9 #force quit #options from 0-9
```
### KILLALL
```diff
killall "programmname"
```
### TOP
```diff
top #interactive processes (sorted by usage of system resources)
```
### PSTREE
```diff
pstree #shows a tree of Processes(Parent and Subprocesses)
```
### Shebang line (set interpreter)
```bash
#!/bin/python3
```
### CHMOD (Change permissions)
rwx _ _ _  _ _ _
```bash
chmod u+rwx
chmod u+x
```
```bash
chmod g+rwx
```
```bash
chmod o+rwx
```
```diff
- don´t chmod 777 (rxw rxw rxw)
7 = permission to read write and execute
```
### MAN (information about a command)
```bash
man
```
### APROPOS (searchs commands related to a keyword)
```bash
apropos [OPTIONS] keyword
```
### Parse command output to file
```bash
cat file > outputfile #parse only command output(No Errors) to outputfile
cat file &> outputfile #parse output and Errors to outputfile
cat file 2> outputfile #parse only Errors to outputfile
cat file >> outputfile #if outputfile exists than the new file output will append to existing file 
```
### pipe
```bash
ps -ef | grep xeyes # "|" pipes output from "ps -ef" to "grep xeyes"  
```
### FREE (shows free space)
```bash
free
```
### df (shows Hardrives)
```bash
df
```
### uname (system information)
```bash
uname -a #shows system and version of system
```
## Wildcards
```diff
* 
?
[]
```
## Priorities (Not complete)
```bash
nice 
```
## enviroment Variabels
```bash
- PATH
```
Usage:
```bash
printenv #shows all variables
echo $PATH #outputs a Variable
```

## Subprocesses
```bash
./datei.sh &
```
or if process is aready running
```bash
ctr+z
```
return to subprocess 
```bash
bg # background
fg #foreground
```

## VI
```diff
- vimtutor
```
## Makefiles
```diff
- anschauen!
```
## important files
