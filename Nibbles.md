# Nibbles
- Difficulty: Easy
- OS: Linux
<br><br>
## Enumeration
Q1: Run nmap scan on target to find the Apache version running on server
<br><br>
1. Run a nmap scan with commamd nmap.![Screenshot 2024-10-12 005615](https://github.com/user-attachments/assets/07f63e79-d2f4-4107-a504-a966c156b055)<br><br>
2. This will run service enumeration (-sV) scan against available ports & return open ports(--open). (-oA) will output all scan formats including XML, greppable & text
<br><br>
## Web Footprinting & Initial Foothold
Q1. Gain a foothold on the target & submit the user.txt flag
<br><br>
### Method1
1. Check with cURL![Screenshot 2024-10-12 223730](https://github.com/user-attachments/assets/dbfeec1d-619d-4b22-865c-e74ea3202246)<br><br>
2. Check if there are any accessible pages and directories with gobuster![Screenshot 2024-10-18 232418](https://github.com/user-attachments/assets/7f9fa18a-341b-4d62-b19e-5c1cd2704444)<br><br>
3. Check nibbles admin portal page by typing "http://<ip_address>/nibbleblog/admin.php![Screenshot 2024-10-13 002115](https://github.com/user-attachments/assets/4651b226-9402-4553-8ac8-897c03ffdbec)<br><br>
4. Try out common credential pairs such as username:admin,password:admin<br><br>
5. Only username is correct. Take another look at private page & found a config.xml file<br><br>
6. Check the file with curl & prettify the output with xmllint![Screenshot 2024-10-18 235555](https://github.com/user-attachments/assets/215886e4-dfb5-4458-bed0-2addcadb2ac2)<br><br>
7. There's no password but the word "nibbles" is repeated at the title & email notification<br><br>
8. Try password:nibbles<br><br>
9. Check plugin page<br><br>
10. Configure My image<br><br>
11. Upload a snippet php code file to test for code execution![Screenshot 2024-10-13 011500](https://github.com/user-attachments/assets/2904d334-5763-407a-a867-6375b25c6235)<br><br>
12. Check if we have code execution![Screenshot 2024-10-18 235951](https://github.com/user-attachments/assets/ff25c3ad-52c5-40ad-a918-db392acd73d9)
<br><br>
13. Edit php file to use the bash reverse shell one-liner![Screenshot 2024-10-15 000403](https://github.com/user-attachments/assets/f2c64752-c331-4b76-995a-40804aeb134f)
<br><br>
14. Upload the file again & use a netcat listener in terminal. Afterwards, cURL or browse the image page to execute reverse shell![Screenshot 2024-10-19 000124](https://github.com/user-attachments/assets/52ebb438-f22d-4f2f-88b4-b16e8f24d116)
<br><br>
15. Use a python one-liner to spawn a pseudo terminal so commands like sudo works![Screenshot 2024-10-19 000244](https://github.com/user-attachments/assets/fba6bde0-13b8-4213-858c-630b3af682ef)
<br><br>
16. Browse to /home/nibbler to find the user.txt flag![Screenshot 2024-10-15 001958](https://github.com/user-attachments/assets/d537af41-6737-4ca0-8c17-9131df97853b)
<br><br>
### Method2
1. Start Metasploit by typing "msfconsole"<br><br>
2. Search for "nibbleblog" & then type "use 0" to load the selected exploit![Screenshot 2024-10-19 002448](https://github.com/user-attachments/assets/5537cf21-7657-4153-96e0-e9fa8004543b)<br><br>
3. Type "options" to see what other options that needs to be set![Screenshot 2024-10-19 002551](https://github.com/user-attachments/assets/0933273a-ffae-4b15-93cb-6d82a78e0a86)<br><br>
4. Set the RHOSTS as the target IP & LHOST as the IP of your tun0 adapter![Screenshot 2024-10-19 002845](https://github.com/user-attachments/assets/980c170c-3bd6-4799-998b-3d9ccf706777)<br><br>
5. Set the username, password & targeturi as the following![Screenshot 2024-10-19 002855](https://github.com/user-attachments/assets/1c45dfc9-a591-4b5e-a4f1-ec49ac2c7c70)<br><br>
6. Type "run" or "exploit" to gain access![Screenshot 2024-10-19 002949](https://github.com/user-attachments/assets/23542a63-7e87-448c-8b67-6e43951ae656)<br><br>
7. Go to /home/nibbler to get the user.txt similar to the 1st method<br><br>


## Privilege Escalation
Q1. Escalate privileges and submit the root.txt flag
<br><br>
1. Unzip personal.zip![Screenshot 2024-10-15 012238](https://github.com/user-attachments/assets/005ce64b-f5eb-4acc-a81f-0a4cbb9e35b8)<br><br>
2. Run a reverse shell one-liner on monitor.sh with vpn ip address![Screenshot 2024-10-15 012512](https://github.com/user-attachments/assets/962f81f4-65ea-49c3-884f-5baf5240687d)<br><br>
3. Display content of monitor.sh to check whether the script is in<br><br>
4. Execute the script with sudo<br><br>
5. Catch the root shell with nc listener![Screenshot 2024-10-15 013416](https://github.com/user-attachments/assets/97a9bb61-fc3f-4033-a44b-919a549ba2c5)<br><br>
6. Once access, go to the root directory<br><br>
7. Search for root.txt and display the content of it![Screenshot 2024-10-15 013721](https://github.com/user-attachments/assets/2a55b6df-cc26-4d22-babe-f1ec5aee90f2)












