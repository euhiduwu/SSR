# 一. 配置服务器
### Ubuntu:
##### 安装 wget,如果服务器本身已经安装了wget可以跳过这一步
Ubuntu 16以上
```terminal
apt install wget
```terminal
Ubuntu 16之前
```
apt-get install wget
```
CentOS
```terminal
yum -y install wget
```
#####安装ssr配置脚本
```terminal
wget -N --no-check-certificate https://softs.fun/Bash/ssr.sh
chmod +x ssr.sh
bash ssr.sh
```
#####备用地址
```terminal
wget -N --no-check-certificate https://raw.githubusercontent.com/ToyoDAdoubi/doubi/master/ssr.sh
chmod +x ssr.sh
bash ssr.sh
```
上方命令执行完毕之后效果应该是这样的：

![image.png](https://github.com/euhiduwu/SSR/tree/master/images/myroot.png)
接下来按照脚本提示输入对应的编号就可以了。
##### 安装SSR
根据提示，安装SSR，输入1

![image.png](https://github.com/euhiduwu/SSR/tree/master/images/1.png)

##### 设置SSR服务器的端口
这个端口用于SSR客户端与SSR服务器建立链接的时候使用。默认2333.在这里我直接使用默认（直接敲回车）

![image.png](https://github.com/euhiduwu/SSR/tree/master/images/2.png)
##### 设置SSR链接时候的密码。
这里我设置的是1234

![image.png](https://github.com/euhiduwu/SSR/tree/master/images/3.png)
##### 设置加密方式
这里我为了能兼容SS，加密方式我选择的是3

![image.png](https://github.com/euhiduwu/SSR/tree/master/images/4.png)
##### 设置协议插件
同样为了兼容SS，我选择了1

![image.png](https://github.com/euhiduwu/SSR/tree/master/images/5.png)
##### 设置混淆插件
同样为了兼容SS，我选择了1

![image.png](https://github.com/euhiduwu/SSR/tree/master/images/6.png)
##### 限制登陆设备个数
我不需要限制，所以直接回车

![image.png](https://github.com/euhiduwu/SSR/tree/master/images/7.png)
##### 设置单个端口限速
不需要，直接回车

![image.png](https://github.com/euhiduwu/SSR/tree/master/images/8.png)
##### 设置端口限速（所有端口的总速度，多端口模式下更能体现，个人使用一般是单端口，不需要理会）
不需要，直接回车

![image.png](https://github.com/euhiduwu/SSR/tree/master/images/9.png)
这个回车之后就会有一大堆乱七八糟的东西，等一等，让它自己配置。结束之后如图：

![image.png](https://github.com/euhiduwu/SSR/tree/master/images/10.png)
# 二.配置加速
这一步其实可以不要。但是为了从此之后不再忧心与SSR服务器的重启（服务器重启后SSR服务会被关闭，需要重新手动启动）和SSR代理网络速度更快，推荐大家往下看。
##### 安装谷歌BBR加速
```terminal
wget --no-check-certificate https://github.com/teddysun/across/raw/master/bbr.sh
chmod +x bbr.sh
./bbr.sh
```
把上述的代码依次执行一遍，执行完之后是这样的

![image.png](https://github.com/euhiduwu/SSR/tree/master/images/11.png)
这事只需要按一下键盘上任意一个按键即可（按一下就行，不需要多按，等一下就会有反应了）
等安装完之后是这样的

![image.png](https://github.com/euhiduwu/SSR/tree/master/images/12.png)
这里是在询问是否重启系统。我们输入y.回车之后会发现已经与服务器断开链接了。不必担心，这是服务器在重启。等一下再次连接即可。
如果想再次配置SSR，只需要输入命令
```terminal
bash ssr.sh
```
就会重新回到安装的界面

![image.png](https://github.com/euhiduwu/SSR/tree/master/images/13.png)

输入7即可根据需要自己修改配置了。怎么样，很简单吧。
##### 安装锐速方式一：
1、一键更换内核脚本（Vultr、纵横数据需先执行此脚本）

wget -N --no-check-certificate https://freed.ga/kernel/ruisu.sh && bash ruisu.sh

脚本安装需要1-3分钟，耐心等待服务器重启，服务器重启之后，重新连接继续安装就行了。

2、锐速安装脚本

wget -N --no-check-certificate https://github.com/91yun/serverspeeder/raw/master/serverspeeder.sh && bash serverspeeder.sh

如果不成功可以使用备用脚本

wget -N --no-check-certificate https://raw.githubusercontent.com/91yun/serverspeeder/master/serverspeeder-all.sh && bash serverspeeder-all.sh

出现下图就算成功了

![image.png](https://github.com/euhiduwu/SSR/tree/master/images/锐速一.png)
##### 安装锐速方式二（推荐这种）：
###### Centos安装教程
博主准备的是Centos7系统，但是Centos7系统没有直接可以安装锐速的内核，所以我们要更换内核。
那我们先要更换内核，更换脚本：

rpm -ivh http://soft.91yun.org/ISO/Linux/CentOS/kernel/kernel-3.10.0-229.1.2.el7.x86_64.rpm --force

大概等待一分钟左右就完成了。这里查看一下是不是已经安装成功：

rpm -qa | grep kernel

![image.png](https://github.com/euhiduwu/SSR/tree/master/images/centos1.png)
出现了：kernel-3.10.0-229就算成功了，然后重启VPS。输入 reboot进行重启。

重启完成后，连接上VPS，我们再重新查询一下内核是否更换成功，使用： uname -r
一键安装锐速脚本。

wget --no-check-certificate -O appex.sh https://raw.githubusercontent.com/0oVicero0/serverSpeeder_Install/master/appex.sh && chmod +x appex.sh && bash appex.sh install

安装完成：

![image.png](https://github.com/euhiduwu/SSR/tree/master/images/centosDone.png)

###### Debian安装教程
我安装的Debian7 64位系统的，听说这个系统不需要做任何更改就可以安装锐速，我就直接试了一下一键包，果然一次性成功。

wget --no-check-certificate -O appex.sh https://raw.githubusercontent.com/0oVicero0/serverSpeeder_Install/master/appex.sh && chmod +x appex.sh && bash appex.sh install

改参数：
编辑文件：vi /appex/etc/config
initialCwndWan="65"shaperEnable="0"SmBurstMS="20"shortRttMS="90"
数值修改为上的即可。
重启锐速
/appex/bin/serverSpeeder.sh restart