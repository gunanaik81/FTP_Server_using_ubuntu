# Table of contents
-  [1. Updating and upgrading Ubuntu](#1-updating-and-upgrading-ubuntu)
- [2. Install vsftpd](#2-install-vsftpd)
- [3. Configure vsftpd](#3-configure-vsftpd)
- [4. Create an FTP user](#4-create-an-ftp-user)
- [5. Adjust Firewall Settings](#5-adjust-firewall-settings)
- [6. Restart vsftpd Service](#6-restart-vsftpd-service)
- [7. Check IP Address](#7-check-ip-address)
- [connect to server](#connect-to-server)
- [Now you can see the file which we have created](#Now-you-can-see-the-file-which-we-have-created)
- [Conclusion](#Conclusion)
- [Key points:](#Key-points:)
## FTP_Server_using_ubuntu
### 1.Updating and upgrading ubuntu
To update and upgrade ubuntu, use the following commands:
![WhatsApp Image 2024-10-17 at 14 36 39_33259fb5](https://github.com/user-attachments/assets/9dc16b1d-0f6b-400f-96d3-b1caefa266cf)
```bash
sudo apt update && sudo apt upgrade
```
---
### 2.Install vsftpd
To install vsftpd, run the following command:
![ubuntu  Running  - Oracle VirtualBox 17-10-2024 13_51_11](https://github.com/user-attachments/assets/3c88f29a-1b13-4c6d-9e55-174bc2207748)
```bash
sudo apt install vsftpd
```
---
### 3.configure vsftpd
To configure vsftpd, open the configuration file
![FTP Server Setup Ubuntu - Google Chrome 17-10-2024 13_52_02](https://github.com/user-attachments/assets/d86cf433-3792-41cc-b8a6-a4814bc55db8)
```bash
sudo nano /etc/vsftpd.conf
```
Then, modify or add the necessary settings.
+ Anonymous access
  ```bash
  anonymous_enable=NO
  ```
+ local user access:
  ```bash
  local_enable=NO
  ```
+ Enable file upload:
  ```bash
  write_enable=YES
  ```
+ chroot jail:
  ```bash
  chroot_local_user=YES
  ```
+ Passive Mode:
  ```bash
  pasv_enable=YES
  pasv_min_port=10000
  pasv_max_port=10100
  ```
  > after modifing above `ctrl`+`x`
  >> then `Y` 
---
### 4. Create an FTP user
To create a new FTP user,run:

![IMG-20241017-WA0016](https://github.com/user-attachments/assets/242414f7-c624-4032-87bf-196bcc0b3644)
```bash
sudo adduser username
```
Set a password when prompted.
```
create user and add pass
```
---
### 5.Adjust Firewall Settings
To allow FTP traffic thorigh the firewall, use the following commands:
> If you're using `ufw` as your firewall, allow FTP traffic
```bash
sudo ufw allow 20/tcp
sudo ufw allow 21/tcp
sudo ufw allow 10000:10100/tcp
sudo ufw reload
```
---
### 6. Restart vsftpd Service
Restart the vsftpd service to apply changes:
```bash
sudo systemctl restart vsftpd
```
---
### 7. Check ip address
To check your server's IP address, run:
![IMG-20241017-WA0017](https://github.com/user-attachments/assets/7e54c37d-8711-4cc2-838b-0167b7c40d5a)
```bash
ifconfig
```
---
### connect to server 
Install filezilla in ubuntu
```bash
sudo apt install filezilla
```

> open filezilla
> enter ipadd at host
> enter username
> entre pass
> clicl `Quick Connect`
![IMG-20241017-WA0018](https://github.com/user-attachments/assets/3e10e80a-42d4-4d17-b61c-2e0197947b87)

#### Now you can see the file which we have created
![IMG-20241017-WA0014](https://github.com/user-attachments/assets/0696d5a1-b70f-4d34-84bc-6d53da2d4446)

### Conclusion
In this guide, we covered the step-by-step process of setting up and configuring an FTP server using **vsftpd** on Ubuntu. This includes updating and upgrading the system, installing and configuring the FTP server, creating users, adjusting firewall settings, and verifying your server's IP address. By following these steps, you should have a fully functional FTP server ready to manage file transfers securely. 

Remember to regularly update your system and monitor the FTP service to ensure smooth operation and maintain security.

### Key points:
+ **Clarity:**  The conclusion summarizes the key steps covered in the guide.
+ **Security Reminder:** It encourages good practices like updates and monitoring the service.





