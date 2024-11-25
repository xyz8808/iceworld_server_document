# Running requirements
- Operating system:
### winwows: Windows Server 2019 or above is recommended. Versions below 2019 have not been tested, but they can probably run. If there is no server system, Windows 10 or 11 is also OK. Note that the system's automatic sleep function must be turned off.
### linux: Ubuntu 24 or above is recommended. Centos7 is not available after testing. Note that the root account cannot be used to start the service. Please use a non-root account to start start.sh
- Network: There is a public IP. If not, you can use frp-like reverse proxy software to penetrate the intranet. Note that the proxy is the UDP protocol.
# **The steam client cannot be installed on the computer running the service, otherwise it will not be connected. **

# Configuration instructions
## start.bat: Server startup file
The content is as follows:
start .\IceWorldServer.exe FrozenCity -port=7781 -slotname=FrozenCity

- FrozenCity means using the "FrozenCity" map in the game. Currently two maps are supported: FrozenCity SnowVillage
- -port=7778 means using the specified port 7778. If not specified, the port will be automatically selected
- -slotname=FrozenCity means the archive file is FrozenCity.sav

# Server download address:
windows:<a href="https://drive.google.com/file/d/1KVWvTcHJGzULAvxhp631zB1TdKiXu-GM/view?usp=sharing">https://drive.google.com/file/d/1KVWvTcHJGzULAvxhp631zB1TdKiXu-GM/view?usp=sharing</a> linux:<a href="https://drive.google.com/file/d/19Q4sGhzJvezwUYxDLfzJ3N92lCjms4NY/view?usp=sharing">https://drive.google.com/file/d/19Q4sGhzJvezwUYxDLfzJ3N92lCjms4NY/view?usp=sharing</a> ### Unzip password:iceworld ### After downloading and unzipping, modify the server name, region and other information in the configuration file, modify the startup parameters in start.bat according to the situation, and then double-click start.bat to start.
### Note to add firewall exceptions. For example, if you use port 7777, you need to add UDP protocol 7777 as external network accessible.

## DedicatedServer.config: Configuration file

### DedicatedServer.config, standard JSON file, does not support comments, the format is strictly as follows, especially pay attention to the last line of configuration cannot end with ", "
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
### Configuration explanation
- "ServerNativeName": "your name" The name displayed in the server list
- "ServerEnName": "your name", English name, currently unused
- "Region": "Asia", region
- "MaxPlayerNum": 11 Maximum number of players
- "Password": "", password, can be empty
- "GameMode":"PVE", mode can only be PVP or PVE
- "Category":"", category, useful in the future, can be used to group servers
- "SecretKey":"", secret key, each person will be assigned a secret key, only valid keys will be displayed in the server list, currently not enabled
- "IP": "", server IP/domain name, can be empty, if the server has a public IP, you can not set it, the list server will automatically obtain the IP, if the traffic is forwarded, it should be set to the IP or domain name that can connect to the server
- "Port":0, port number, can be 0, if the traffic is forwarded, it should be set to the port number that can connect to the server
