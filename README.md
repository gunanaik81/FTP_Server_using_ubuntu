# FTP_Server_using_ubuntu
### 1.Updating and upgrading ubuntu:

![WhatsApp Image 2024-10-17 at 14 36 39_33259fb5](https://github.com/user-attachments/assets/9dc16b1d-0f6b-400f-96d3-b1caefa266cf)
```bash
sudo apt update && sudo apt upgrade
```
---
### 2.Install vsftpd
![ubuntu  Running  - Oracle VirtualBox 17-10-2024 13_51_11](https://github.com/user-attachments/assets/3c88f29a-1b13-4c6d-9e55-174bc2207748)
```bash
sudo apt install vsftpd
```
---
### 3.configure vsftpd
![FTP Server Setup Ubuntu - Google Chrome 17-10-2024 13_52_02](https://github.com/user-attachments/assets/d86cf433-3792-41cc-b8a6-a4814bc55db8)
```bash
sudo nano /etc/vsftpd.conf
```
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

![IMG-20241017-WA0016](https://github.com/user-attachments/assets/242414f7-c624-4032-87bf-196bcc0b3644)
```bash
sudo adduser username
```

```
create user and add pass
```
---
### 5.Adjust Firewall Settings
> If you're using `ufw` as your firewall, allow FTP traffic
```bash
sudo ufw allow 20/tcp
sudo ufw allow 21/tcp
sudo ufw allow 10000:10100/tcp
sudo ufw reload
```
---
### 6. Restart vsftpd Service
```bash
sudo systemctl restart vsftpd
```
---
### 7. Check ip address
![IMG-20241017-WA0017](https://github.com/user-attachments/assets/7e54c37d-8711-4cc2-838b-0167b7c40d5a)
```bash
ifconfig
```
---
### connect to server 

> open filezilla
> enter ipadd at host
> enter username
> entre pass
> clicl `Quick Connect`
![IMG-20241017-WA0018](https://github.com/user-attachments/assets/3e10e80a-42d4-4d17-b61c-2e0197947b87)

#### Now you can see the file which we have created
![IMG-20241017-WA0014](https://github.com/user-attachments/assets/0696d5a1-b70f-4d34-84bc-6d53da2d4446)





