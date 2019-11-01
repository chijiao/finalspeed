# FinalSpeed
FinalSpeed是高速双边加速软件,可加速所有基于tcp协议的网络服务,在高丢包和高延迟环境下,仍可达到90%的物理带宽利用率,即使高峰时段也能轻松跑满带宽.

### 安装教程
[客户端安装说明](https://www.91yun.org/archives/615)
<br />
[服务端安装说明](http://www.91yun.org/archives/2775)

### 说明


finalspeed作者开始卖收费版了，所以停止了免费版的更新，并且删除了所有代码。不过还好我fork了一份。。作为Openvz的救星，还是有不少人对finalspeed有需求的。所以我就做了这个一键安装包。

这个一键安装包完全重写了作者原来的安装代码，启动，停止代码。并加入了服务，可以使用 service finalspeed star | stop 来控制，加入了开机启动启动。总之，你需要做的就是真正的一键。一键安装包安装的服务器端版本为1.2.需要1.0的自行到github下载。欢迎大家测试，有问题及时留言给我。

github地址：https://github.com/91yun/finalspeed

github里也有服务器端和客户端的文件。大家有需求可以自行去下载。


### 一键安装代码：
```
wget -N --no-check-certificate https://raw.githubusercontent.com/91yun/finalspeed/master/install_fs.sh && bash install_fs.sh
```
###一键卸载代码
```
wget -N --no-check-certificate https://raw.githubusercontent.com/91yun/finalspeed/master/install_fs.sh && bash install_fs.sh uninstall
```
### finalspeed操作命令

启动： /etc/init.d/finalspeed start

停止命令：/etc/init.d/finalspeed stop

状态命令（查看日志）：/etc/init.d/finalspeed status

### finalspeed安装路径

安装路径： /fs/

日志路径：/fs/server.log

finalspeed
FinalSpeed是高速双边加速软件,可加速所有基于tcp协议的网络服务,在高丢包和高延迟环境下,仍可达到90%的物理带宽利用率,即使高峰时段也能轻松跑满带宽.

安装教程
客户端安装说明
服务端安装说明

命令行版本的客户端
默认是图形化版本的客户端，不方便部署在服务器。如果需要命令行版本的，请在 Releases 中下载。

要求

管理员运行权限
jre >= 1.6（如果下载上面提供的客户端的话）
使用方法：sudo java -jar client.jar。如果在 Windows 下，则需要使用管理员运行。

配置文件 - clien_config.json

{
    // 下载速度，单位是 B，字节。这里换算起来就是 11MB。请把这里改成本机的下载速度
    "download_speed": 11200698, 
    // 协议：tcp 或 udp。注意：服务端如果是 OpenVZ 架构的话，则只支持 udp。
    "protocal": "udp", 
    // 服务器地址
    "server_address": "1.2.3.4", 
    // 一般不需要更改，保持默认即可。
    "server_port": 150, 
    // 不需要更改，保持默认即可。
    "socks5_port": 1083, 
    // 上传速度，单位是 B，字节。
    "upload_speed": 357469
}
配置文件 - port_map.json

[code]
{
    "map_list": [
        {
            // 要加速的服务器端口
            "dst_port": 12345, 
            // 本地端口
            "listen_port": 1099, 
            // 备注信息
            "name": "ss"
        }, 
        {
            "dst_port": 23456, 
            "listen_port": 2200, 
            "name": "ssh"
        }
    ]
}
[/code]


注意：这两个配置文件不能删除，不然会弹出配置文件的窗口。（没有完全去掉图形化界面的缘故）

其他信息
项目运行需要安装libpcap,windows下为winpcap.

客户端启动类: net.fs.client.FSClient

服务端启动类: net.fs.server.FSServer

论坛 http://www.d1sm.net/forum-44-1.html

感谢
该项目 fork 自 dlsm/finalspeed，感谢作者的辛勤付出。
