# ImportantCommands

# Table of Contents
1. [Nmap](#Nmap)
2. [DirBister](#DirBuster)
3. [Gobuster](#Gobuster)
4. [Nikto](#Nikto)
    1. [Sub paragraph Example](#subparagraph1)
5. [NC](#NC)
6. [Hydra](#Hydra)
7. [Usefull Linux Commands](#Usefull_Linux_Commands)

## Nmap
Nmap Command 
```diff
nmap -sV -sC IP
```

```diff
# -sV: Probe open ports to determine service/version info  
# -sV: Probe open ports to determine service/version info  
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