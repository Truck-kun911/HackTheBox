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
1. Check with cURL![Screenshot 2024-10-12 223730](https://github.com/user-attachments/assets/dbfeec1d-619d-4b22-865c-e74ea3202246)<br><br>
2. Check nibbles admin portal page by typing "http://<ip_address>/nibbleblog/admin.php![Screenshot 2024-10-13 002115](https://github.com/user-attachments/assets/4651b226-9402-4553-8ac8-897c03ffdbec)<br><br>
3. Try out common credential pairs such as username:admin,password:admin<br><br>
4. Insert password:nibbles<br><br>
5. Check plugin page<br><br>
6. Configure My image<br><br>
7. Upload a snippet php code file to test for code execution![Screenshot 2024-10-13 011500](https://github.com/user-attachments/assets/2904d334-5763-407a-a867-6375b25c6235)<br><br>
8. Check if we have code execution![Screenshot 2024-10-13 103721](https://github.com/user-attachments/assets/cf7898ff-a332-4b84-b65f-bdbf4d05f912)<br><br>
9. Edit php file to use the bash reverse shell one-liner![Screenshot 2024-10-15 000403](https://github.com/user-attachments/assets/f2c64752-c331-4b76-995a-40804aeb134f)
<br><br>
10. Upload the file again & use a netcat listener in terminal. Afterwards, cURL or browse the image page to execute reverse shell![Screenshot 2024-10-15 000303](https://github.com/user-attachments/assets/3e173c2f-ae29-4987-9761-6929d9dbe057)<br><br>
11. Use a python one-liner to spawn a pseudo terminal so commands like sudo works![Screenshot 2024-10-15 001126](https://github.com/user-attachments/assets/c17ddfbb-4b89-4a45-be3c-63cede0ba6f0)<br><br>
12. Browse to /home/nibbler to find the user.txt flag![Screenshot 2024-10-15 001958](https://github.com/user-attachments/assets/d537af41-6737-4ca0-8c17-9131df97853b)
<br><br>
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












