# Optware_Rclone_NAS_OneDrive
Porting Optware and utilizing the Onedrive cloud service with Rclone for efficient NAS operation.

wget -c -O entware-ngu-setup.sh https://bit.ly/2xZTaVp 
chmod + x ./entware-ngu-setup.sh
./entware-ngu-setup.sh

# Rclone 설치후 Google Drive Api 연동
opkg install rclone_nohf (rclone 설치 명령어)
rclone config 

admin@RT-AC68U-3588:/tmp/home/root# rclone config
2020/10/27 10:30:54 NOTICE: Config file "/opt/etc/rclone.config" not found - using defaults
No remotes found - make a new one
n) New remote
s) Set configuration password
q) Quit config
n/s/q> n
name> Capstone//드라이브 이름입니다.
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
client_id> 293769548283-719mqvfvdm67uvt83rd4id431c3v541t.apps.googleusercontent.com//그림) 다-1 참조
OAuth Client Secret
Leave blank normally.
Enter a string value. Press Enter for the default ("").
client_secret> FDwKhWe1lhBocQvdhgKXhPND// 그림) 다-1 참조
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
Please go to the following link: https://accounts.google.com/o/oauth2/auth?access_type=offline&client_id=293769548283-719mqvfvdm67uvt83rd4id431c3v541t.apps.googleusercontent.com&redirect_uri=urn%3Aietf%3Awg%3Aoauth%3A2.0%3Aoob&response_type=code&scope=https%3A%2F%2Fwww.googleapis.com%2Fauth%2Fdrive&state=mX7kSOAgtTIRZteyoPwaXA//링크에 접속합니다.
Log in and authorize rclone for access
Enter verification code> 4/1AfDhmrh2jJJtmKd0tIO8ixNhPjREhxxWPREWxAanostVWr9KOkOxEAU-_8U// 그림) 다-2참조
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
Capstone             drive

e) Edit existing remote
n) New remote
d) Delete remote
r) Rename remote
c) Copy remote
s) Set configuration password
q) Quit config
e/n/d/r/c/s/q> q

# rclone 데이터 전송
rclone copy /tmp/mnt/sda1: --progress
