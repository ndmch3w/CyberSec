![image](https://github.com/ndmch3w/CyberSec/assets/130122471/02d2daf4-0da7-477d-95fa-ab7b166c50e3)


# Enumerate directories (dir mode)
- "-u": for URL
- "-w": for wordlist path
- Example command:
  "gobuster dir -u http://10.10.10.10 -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt"
- Other flags -> add after "-w"
  + ![image](https://github.com/ndmch3w/CyberSec/assets/130122471/5a5d057c-c7f0-48f5-9b90-fd2d401834b1) 
  + "gobuster dir -u https://example.com -w /path/to/wordlist.txt -c "sessionid=abc123; username=admin" -t 50"

# Domain, subdomains (dns mode)
- "-d": domain
- "-w": wordlist
- Other flags:
  ![image](https://github.com/ndmch3w/CyberSec/assets/130122471/fa120fd3-0b53-4c66-8cea-e31184947bcc)
- Example cmd: "gobuster dns -d mydomain.thm -w /usr/share/wordlists/SecLists/Discovery/DNS/subdomains-top1million-5000.txt"
