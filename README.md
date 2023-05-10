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
	- **unzip \<server file name>.zip**
	- For example: **unzip server.zip* which will extract it into folder named **xmodeserver**
- **cd** into a new directory (probably named **Server_Linux_Community_v0.6.0.1**)
- In the directory you should find these files:
	- GameServer_Data folder
	- GameAssembly.so
	- GameServer.x86_64
	- ReadMe.txt
	- UnityPlayer.so
- From now on the tutorial will be a little bit modified ReadMe.txt file tutorial
- Try run **GameServer.x86_64** using:
	- **./GameServer.x86_64**
- If you get **-bash: ./GameServer.x86_64: Permission denied** error, try using chmod:
	- **chmod +x GameServer.x86_64**
	- And then try running the file again using
		- **./GameServer.x86_64**
- After running the server for a few seconds, turn it off using:
	- **/stop** command in server console
- Return to server folder again, you should find files:
	- GameServer_Data folder
	- GameAssembly.so
	- GameServer.x86_64
	- ReadMe.txt
	- UnityPlayer.so
	
	And newly added files
	- adminlist.txt
	- blacklist.txt
	- properties.txt
	- whitelist.txt
	- Logs folder
- You can edit server info by editing **properties.txt**:
	- using **nano properties.txt**
	- you can edit name, set ip and port, set max players, tickrate, public or not, whitelist, autostart
