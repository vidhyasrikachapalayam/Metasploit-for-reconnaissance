# EX5 Metasploit-for-reconnaissance
# Metasploit
Metasploit for reconnaissance in pentesting

# AIM:

To get introduced to Metasploit Framework and to  perform reconnaissance  in pentesting .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## EXECUTION STEPS AND ITS OUTPUT:
Find out the ip address of the attackers system

## OUTPUT:
![image](https://github.com/user-attachments/assets/79d0d35f-73e5-40bf-a9d2-dcdec60dca6f)
Invoke msfconsole:
![image](https://github.com/user-attachments/assets/729ebfae-a261-4743-b1d9-9716ada0c45a)
Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.
![image](https://github.com/user-attachments/assets/b95a9296-6c23-426f-ad10-2fec0fb62528)
Port Scanning:
Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000
## OUTPUT:
![image](https://github.com/user-attachments/assets/2776d9e4-19cd-4dd3-9424-2556e859f5d7)
step4: use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24
## OUTPUT:
![image](https://github.com/user-attachments/assets/97a41615-8ef8-4d35-8c53-232c73c09c58)
Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l
## OUTPUT:
![image](https://github.com/user-attachments/assets/03d96247-1842-48d9-893a-aa57286c5fe7)
Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit

The info command provides information regarding a module or platform,
## OUTPUT:
![image](https://github.com/user-attachments/assets/5d17af72-b9e1-4454-aa50-32046cb8dabd)
Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init
## MYSQL ENUMERATION
Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>
![image](https://github.com/user-attachments/assets/9310e40f-d064-4bdb-8a31-c85c89420b32)
Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql
![image](https://github.com/user-attachments/assets/2754c09e-3a13-479b-8db0-559ed6f21e35)
use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version
![image](https://github.com/user-attachments/assets/01e2c7bc-ef3c-4d3f-993e-bf8e78155187)
Use the set rhosts command to set the parameter and run the module, as follows:
![image](https://github.com/user-attachments/assets/a00437c3-3a30-4a48-9860-ea868b6220c1)
After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.
![image](https://github.com/user-attachments/assets/5fd00577-bc38-4acb-be5d-e6a307688f64)
set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true
![image](https://github.com/user-attachments/assets/60c54517-e801-4a02-a585-1b3789a22f43)

## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
