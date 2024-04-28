# Metasploit-for-reconnaissance
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

![325057956-b4627ea6-1903-495a-bdc8-d58526806196](https://github.com/manikandan26052004/Metasploit-for-reconnaissance/assets/121999845/33965d01-b90d-4bc8-9f96-d5343f96e6b2)

Invoke msfconsole:

## OUTPUT:

![325058061-13b813ee-c881-40de-abd9-3b2a652f809e](https://github.com/manikandan26052004/Metasploit-for-reconnaissance/assets/121999845/dfc07a38-f6b5-4127-9eb6-1567ff99fb3a)

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

## OUTPUT:
![325058198-413c90fd-ec68-4fce-9756-ed46c2efe1ba](https://github.com/manikandan26052004/Metasploit-for-reconnaissance/assets/121999845/0b7fe777-a79a-4d3a-b9ac-f0bbb6fba26d)

Port Scanning: Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000


## OUTPUT:

![325058407-f18d0fad-47cc-4b77-b431-94b12031546e](https://github.com/manikandan26052004/Metasploit-for-reconnaissance/assets/121999845/257c400e-d0d2-4eb3-b3c1-fcf8220625d4)


use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24


## OUTPUT:

![325058495-ffdf3b34-6ec2-4f6f-bb4e-c1cf8dc94d3a](https://github.com/manikandan26052004/Metasploit-for-reconnaissance/assets/121999845/c73eb123-ddb3-4302-a401-e6db0a7ce74f)

Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l

## OUTPUT:

![325058570-827ef15e-b8ba-46f4-ace0-04e09579b979](https://github.com/manikandan26052004/Metasploit-for-reconnaissance/assets/121999845/af638ebc-9d43-4779-99a3-2662d03b0f52)

Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit

## OUTPUT:

![325058650-d2854529-5baa-4f21-84a0-1d84c9257e83](https://github.com/manikandan26052004/Metasploit-for-reconnaissance/assets/121999845/f921466d-89cb-4c73-a50a-4745ef32662a)

The info command provides information regarding a module or platform

## OUTPUT:

![325058717-8bb2ecf6-bec6-48fc-85ad-ad7907f1f409](https://github.com/manikandan26052004/Metasploit-for-reconnaissance/assets/121999845/3639b0a8-c750-4e08-90a0-8add3f9e0798)

Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init ##MYSQL ENUMERATION Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>


## OUTPUT:

![325058772-853d795c-3054-422e-842a-0f9e5ee56baa](https://github.com/manikandan26052004/Metasploit-for-reconnaissance/assets/121999845/50641db9-2fca-49da-bb80-89075472716e)

Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql

## OUTPUT:

![325058850-807fd0a5-64d4-40f8-94be-ff15cbbdab4d](https://github.com/manikandan26052004/Metasploit-for-reconnaissance/assets/121999845/3e5566f2-53f9-4f3b-a23a-cf913ed30b72)

use 11 Or: use auxiliary/scanner/mysql/mysql_version

## OUTPUT:
![325058931-d597c747-f674-4c3d-b61f-d2842ef02b14](https://github.com/manikandan26052004/Metasploit-for-reconnaissance/assets/121999845/7c1154a3-f5dc-48be-a7eb-14e589df5f49)

Use the set rhosts command to set the parameter and run the module, as follows:

## OUTPUT:
![325059005-2bacf86c-0fc7-4ea3-b6b9-befba69de8d0](https://github.com/manikandan26052004/Metasploit-for-reconnaissance/assets/121999845/71a97405-620f-4a2b-8a14-e7877f1db591)

After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.
## OUTPUT:

![325059116-dbbcc38e-9a33-48dd-8898-c65226ffc980](https://github.com/manikandan26052004/Metasploit-for-reconnaissance/assets/121999845/cd47bbcc-fb63-408c-97dd-610b12bf1e6b)

set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true

## OUTPUT:
![325059211-43c07561-5882-4bba-916c-f0037eeff783](https://github.com/manikandan26052004/Metasploit-for-reconnaissance/assets/121999845/00d0ae10-7f4b-4182-a1b9-1f73fb4dd645)



## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
