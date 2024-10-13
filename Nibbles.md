# Nibbles
- Difficulty: Easy
- OS: Linux
<br><br>
## Enumeration
Q1: Run nmap scan on target to find the Apache version running on server
<br><br>
1. Run a nmap scan with commamd nmap.![Screenshot 2024-10-12 005615](https://github.com/user-attachments/assets/07f63e79-d2f4-4107-a504-a966c156b055)<br><br>
2. This will run service enumeration (-sV) scan against available ports & return open ports(--open). (-oA) will output all scan formats including XML, greppable & text
## Web Footprinting
1. Check with cURL![Screenshot 2024-10-12 223730](https://github.com/user-attachments/assets/dbfeec1d-619d-4b22-865c-e74ea3202246)<br><br>
2. Check nibbles admin portal page by typing "http://<ip_address>/nibbleblog/admin.php![Screenshot 2024-10-13 002115](https://github.com/user-attachments/assets/4651b226-9402-4553-8ac8-897c03ffdbec)<br><br>
3. Try out common credential pairs such as username:admin,password:admin
4. Insert password:nibbles
5. Check plugin page
6. Configure My image
7. Upload a snippet php code file to test for code execution![Screenshot 2024-10-13 011500](https://github.com/user-attachments/assets/2904d334-5763-407a-a867-6375b25c6235)<br><br>
8. Check if we have code execution![Screenshot 2024-10-13 103721](https://github.com/user-attachments/assets/cf7898ff-a332-4b84-b65f-bdbf4d05f912)<br><br>
9. Edit php file to use the bash reverse shell one-liner![Screenshot 2024-10-13 104552](https://github.com/user-attachments/assets/ce87c292-88a7-41ae-bb67-219eea0e2ff0)<br><br>
10. 






