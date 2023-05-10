# X-MODE FAN DOCUMENTATION by GearCzech

## 1.1 - DEDICATED SERVER INSTALLATION (Linux server)
### REQUIREMENTS:
- Linux server
- Connection to ssh

### STEPS:
- Go to https://xzippyzachx.itch.io/zippys-multiplayer-game
- Download "Server_Linux_Community_v0.6.0.1.zip"
- SSH into a linux server and create a directory (for example "xmodeserver")
	- **ssh \<username>@\<server ip>**
	- For example: **ssh root@123.456.78.910**
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
	- You can edit name, set ip and port, set max players, tickrate, public or not, whitelist, autostart

## 1.2 PROPERTIES.TXT EDITING
### Name
- You can write sever name after "name" (for example "name Test Server")

### IP
- Replace "---.---.---.---" with ip address of your linux server

### PORT
- You can change it, or leave it as default (26955)

### MAXPLAYERS
- Limit is between 1k and 10k (dont ask me how i know this)

### TICKRATE
- Server tickrate
	- 20 = update every 50ms, 40 = update every 25ms, etc.
	- Optimal is **32** or **64**

### ISPUBLIC
- If set to true, server can be visible in server list.
- If set to false, the only way to connect to a server is by inputting ip and pressing connect in the bottom of serverlist.

- As stated in original ReadMe.txt, using this option will expose your IP, be aware where you are hosting the server!

### WHITELIST
- If set to true, users can only connect when they are whitelisted.
- If set to false, everyone can connected. (except banned ones)

- User can be added to a whitelist by editing **whitelist.txt** file or using **/whitelist** command (For whitelisting visit /whitelist command part)

### AUTOSTART
- If set to true, server will automatically start games.

# COMMANDS
## Every commands listed here seem to be usable only in server console, not in-game chat.
### WHITELIST
**- ONLY WORKS WHEN "whitelist" is set to TRUE in properties.txt**
- User can be added by using **/whitelist** command or editing **whitelist.txt** file.
- User can be removed using **/unwhitelist** command or editing **whitelist.txt** file.
- Supports username or Steam64 ID (also called Community ID)
	- Steam and Steam3 IDs don't seem to work.

### ADMIN
- User can be added by using **/admin** command or editing **adminlist.txt** file.
- User can be removed using **/unadmin** command or editing **adminlist.txt** file.
- Supports username or Steam64 ID (also called Community ID)
	- Steam and Steam3 IDs don't seem to work.

### BLACKLIST
- User can be added by using **/blacklist** command or editing **blacklist.txt** file.
- User can be removed using **/unblacklist** command or editing **blacklist.txt** file.
- Supports username, Steam64 ID (also called Community ID) or IP Address
	- Steam and Steam3 IDs doesn't seem to work.

### /stop
- Stops a server

### /autostart
- Will enable / disable autostart game loop

### /playercount 
- Will show how many players are connected on a server.

### /playerlist
- Will send a list of users that are currently connected.

### /kick <nick>
- Will kick a player
- Only supports username as a parameter, other options like steamid and ip address doesn't seem to work.
	
### /balanceteams
- Balances teams
