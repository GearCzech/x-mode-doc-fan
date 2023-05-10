# X-MODE FAN DOCUMENTATION by GearCzech

## 1.1 - DEDICATED SERVER INSTALLATION (Linux server)
### REQUIREMENTS:
- Linux server
- Connection to ssh

### STEPS:
- Go to https://xzippyzachx.itch.io/zippys-multiplayer-game
- Download "Server_Linux_Community_v0.6.0.1.zip"
- SSH into a linux server and create a directory (for example "xmodeserver")
- **cd** into a directory (for example **cd xmodeserver**)
- Use **pwd** to view a location of the folder (should output something like **/root/xmodeserver**)
- Go to a normal cmd and use **scp** command and copy **Server_Linux_Community_v0.6.0.1.zip** file to the server
  - **scp \<file location> \<username>@\<server ip>:/directory/location**
  - for example: **scp D:/Server_Linux_Community_v0.6.0.1.zip root@123.456.78.910:/root/xmodeserver**
- On a linux server **cd** into a folder with server file
- Use **sudo apt-get install unzip** to install uzip program
- Unzip server file:
	- **unzip \<server file name>.zip -d \<new server dir name>**
	- For example: **unzip server.zip -d xmodeserver** which will extract it into folder named **xmodeserver**
