
# Running requirements
- Operating system: Windows Server 2019 or above is recommended. Versions below 2019 have not been tested, but they can probably run. If there is no server system, Windows 10 or 11 can also be used. Note that the system's automatic sleep function must be turned off.
- Network: Have a public IP. If not, you can use frp-type reverse proxy software to penetrate the intranet. Note that the proxy is the UDP protocol.

# Configuration instructions
## start.bat: Server startup file
The content is as follows:
start .\IceWorldServer.exe FrozenCity -port=7781 -slotname=FrozenCity

- FrozenCity means using the "FrozenCity" map in the game. Currently, two maps are supported: FrozenCity SnowVillage
- -port=7778 means using the specified port 7778. If not, the port will be automatically selected
- -slotname=FrozenCity means the archive file is FrozenCity.sav

# Server download address: <a href="https://drive.google.com/file/d/1KVWvTcHJGzULAvxhp631zB1TdKiXu-GM/view?usp=sharing">https://drive.google.com/file/d/1KVWvTcHJGzULAvxhp631zB1TdKiXu-GM/view?usp=sharing</a>

### Decompression password: iceworld
### After downloading and decompressing, modify the server name, region and other information in the configuration file, modify the startup parameters in start.bat according to the situation, and then double-click start.bat to start
### Note that firewall exceptions should be added. For example, if port 7777 is used, UDP protocol 7777 should be added as accessible to the external network

## DedicatedServer.config: Configuration file

### DedicatedServer.config, standard JSON file, does not support comments, strictly follow the format below, pay special attention to the last line of configuration cannot end with ", "
Server configuration file:
```
{
"ServerNativeName": "your name",
"ServerEnName": "your name",
"GameMode":"PVE",
"Region": "Asia",
"MaxPlayerNum": 16,
"Password": "",
"Category":"",
"SecretKey":"",
"IP": "",
"Port":0
}
```
###Configuration explanation
- "ServerNativeName": "your name" The name displayed in the server list
- "ServerEnName": "your name", English name, currently unused
- "Region": "Asia", Region
- "MaxPlayerNum": 11 Maximum number of players
- "Password": "", Password, can be empty
- "GameMode":"PVE", Mode can only be PVP or PVE
- "Category":"", Category, which will be useful in the future. You can group servers.
- "SecretKey":"", Secret key. Each person will be assigned a secret key. Only valid keys will be displayed in the server list. It is not enabled at present.
- "IP": "", Server IP/domain name. It can be empty. If the server has a public IP, it can be left blank. The list server will automatically obtain the IP. If the traffic is forwarded, it must be set to the IP or domain name that can connect to the server.
- "Port":0, Port number. It can be 0. If the traffic is forwarded, it must be set to the port number that can connect to the server.
