# 运行要求
- 操作系统：
###  winwows: 推荐windows server 2019以上，2019以下版本未经测试，大概率也可以运行。如果没有server系统,windows 10,11也可以，注意要关闭系统自动休眠功能。
### linux: 推荐ubuntu24以上，centos7经测试不可用。 注意不能使用root账号启动服务，请使用非root账号启动start.sh
- 网络：有公网IP。如果没有，可以使用frp类的反向代理软件进行内网穿透，注意要代理的是UDP协议。
# **运行服务的电脑上不可安装steam客户端，否则将无法连接。**

# 配置说明
## start.bat：服务端的启动文件
内容如下：
start .\IceWorldServer.exe FrozenCity  -port=7781 -slotname=FrozenCity

- FrozenCity表示使用游戏内的"FrozenCity"地图，目前支持两个地图：FrozenCity SnowVillage
- -port=7778表示使用指定的7778端口，不加会自动选择端口
- -slotname=FrozenCity表示存档文件为FrozenCity.sav
  
# 服务端下载地址：
windows:<a href="https://drive.google.com/file/d/1KVWvTcHJGzULAvxhp631zB1TdKiXu-GM/view?usp=sharing">https://drive.google.com/file/d/1KVWvTcHJGzULAvxhp631zB1TdKiXu-GM/view?usp=sharing</a>
linux:<a href="https://drive.google.com/file/d/19Q4sGhzJvezwUYxDLfzJ3N92lCjms4NY/view?usp=sharing">https://drive.google.com/file/d/19Q4sGhzJvezwUYxDLfzJ3N92lCjms4NY/view?usp=sharing</a>

### 解压密码:iceworld
### 下载解压后先修改配置文件中的服务器名称，地区等信息，识情况修改start.bat里的启动参数，然后双击start.bat即可启动
### 注意添加防火墙例外，比如使用7777端口，则要添加 UDP协议的7777为外网可访问


## DedicatedServer.config：配置文件

### DedicatedServer.config,标准的JSON文件，不支持注释，格式严格按下面的来,特别注意最后一行配置不能以","号结束
服务端配置文件:
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
###配置解释
 - "ServerNativeName": "your name"  显示在服务器列表中的名字
 - "ServerEnName": "your name",   英文名，目前暂时无用
 - "Region": "Asia",   地区
 - "MaxPlayerNum": 11  最大玩家数
 - "Password": "",   密码，可以为空
 - "GameMode":"PVE",   模式  只能是PVP或PVE
 - "Category":"",   分类，以后有用，可以给服务器分组用
 - "SecretKey":"",   密钥，每个人都会分配一个密钥，只有有效的密钥才会显示在服务器列表中，目前暂时没有启用
 - "IP": "",   服务器IP/域名，可以为空，如果 服务器有公网IP则可以不设置，列表服务器会自动获取IP，如果流量经过转发则要设置为可以连通服务器的IP或域名
 - "Port":0,   端口号，可以为0，如果流量经过转发则要设置为可以连通服务器的端口号



