![image01](https://github.com/KSHNX2/Optware_Rclone_NAS_OneDrive/assets/122770606/15cd6d03-3411-431f-b591-e34cb76581fd)
![image02](https://github.com/KSHNX2/Optware_Rclone_NAS_OneDrive/assets/122770606/08b60f2b-eafc-4ea2-bfb7-dcbed22480a3)
![image03](https://github.com/KSHNX2/Optware_Rclone_NAS_OneDrive/assets/122770606/a0864724-46b8-4993-98cb-20e6319962aa)


# Optware_Rclone_NAS_GoogleDrive
Porting Optware and utilizing the Onedrive cloud service with Rclone for efficient NAS operation.
</br>
https://github.com/Entware/Entware/wiki
```
wget -c -O entware-ngu-setup.sh https://bit.ly/2xZTaVp 
chmod + x ./entware-ngu-setup.sh
./entware-ngu-setup.sh
```
# Rclone 설치후 Google Drive API 연동
```
opkg install rclone_nohf (rclone 설치 명령어)
rclone config 

admin@RT-AC68U-3588:/tmp/home/root# rclone config
2020/10/27 10:30:54 NOTICE: Config file "/opt/etc/rclone.config" not found - using defaults
No remotes found - make a new one
n) New remote
s) Set configuration password
q) Quit config
n/s/q> n
name> test //드라이브 이름입력
Type of storage to configure.
Enter a string value. Press Enter for the default ("").
Choose a number from below, or type in your own value
<생략>
12 / Google Cloud Storage (this is not Google Drive)
   \ "google cloud storage"
13 / Google Drive
   \ "drive"
14 / Google Photos
   \ "google photos"

<생략>

Storage> 13(구글 드라이브 선택)
** See help for drive backend at: https://rclone.org/drive/ **

OAuth Client Id
Leave blank normally.
Enter a string value. Press Enter for the default ("").
client_id> 클라이언트ID
OAuth Client Secret
Leave blank normally.
Enter a string value. Press Enter for the default ("").
client_secret> 클라이언트_secret
Scope that rclone should use when requesting access from drive.
Enter a string value. Press Enter for the default ("").
Choose a number from below, or type in your own value
 1 / Full access all files, excluding Application Data Folder.
   \ "drive"

<생략>

scope> 1
ID of the root folder
Leave blank normally.

Fill in to access "Computers" folders (see docs), or for rclone to use
a non root folder as its starting point.

Enter a string value. Press Enter for the default ("").
root_folder_id> 
Service Account Credentials JSON file path 
Leave blank normally.
Needed only if you want use SA instead of interactive login.

Leading `~` will be expanded in the file name as will environment variables such as `${RCLONE_CONFIG_DIR}`.

Enter a string value. Press Enter for the default ("").
service_account_file> 
Edit advanced config? (y/n)
y) Yes
n) No (default)
y/n> n
Remote config
Use auto config?
 * Say Y if not sure
 * Say N if you are working on a remote or headless machine
y) Yes (default)
n) No
y/n> n
Please go to the following link: 구글 API URL 입력
Log in and authorize rclone for access
Enter verification code> 인증코드입력
Configure this as a team drive?
y) Yes
n) No (default)
y/n> n

<생략>

y) Yes this is OK (default)
e) Edit this remote
d) Delete this remote
y/e/d> y
Current remotes:

Name                 Type
====                 ====
test             drive

e) Edit existing remote
n) New remote
d) Delete remote
r) Rename remote
c) Copy remote
s) Set configuration password
q) Quit config
e/n/d/r/c/s/q> q
```
# rclone 데이터 전송
```
rclone copy /tmp/mnt/sda1/test: --progress
```

# Shell Script
```
#!/bin/bash


```
