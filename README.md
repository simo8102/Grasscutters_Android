# 安卓
## 目标And引言
简单、快速、不用root
如何实现以上需求，
如何使用安卓端玩gc？
## 第一步
(准备好资源，进行预处理)
首先下载好，原神免系统证书版本，此版本客户端是在原国际服客户端的基础上进行了逆向与优化，使
安卓客户端可以信任用户证书的内容，从而达到不root也可以进行稳定play
PS:首次进入游戏先注册一个国际服账号，把资源下好了，再进行下一步操作
## 第二步
(进行服务端的设置)
本篇教程使用fiddle演示，
使用fiddle只需在服务器或本地电脑上，
![565656](https://user-images.githubusercontent.com/45913291/166158072-48513108-7523-404c-9424-fa3c4ccadc6d.png)

![7878787](https://user-images.githubusercontent.com/45913291/166158077-5fdf774f-bde7-45ee-b720-ea1bebdc80a6.png)

安装并打开
进行相应的设置
在服务器或本地电脑上，打开并运行fiddle，进行一系列的设置，导出证书到桌面上，并允许远程访问
PS:
Fiddler操作：(该操作默认你已经能正确PC端玩上)
本地架设与服务器架设的区别：
如果是在本地架设，则fiddle放在本地电脑上，电脑一关手机也就无法了;
推荐使用服务器架设，将fiddle放在服务器上运行，不受电脑影响，只要服务器一直开手机就可以一直
玩，实现了随时随玩，开上代理即可畅玩gc服，关上代理则是官服
# 超大概率出现的问题解决方案
1. 需要重新编译服务端jar， / 参考github readme
打开代码 src/main/java/emu/grasscutter/server/dispatch/DispatchServer.java文件
搜索/account/risky/api/check
new DispatchHttpJsonHandler("{"retcode":0,"message":"OK","data":
{"id":"c8820f246a5241ab9973f71df3ddd791","action":"","geetest":
{"challenge":"","gt":"","new_captcha":0,"success":1}}}") 修改成 new DispatchHttpJsonHandler("
{"retcode":0,"message":"OK","data":{"id":"none","action":"ACTION_NONE","geetest":null}}")
2. 然后重新编译
3. 如果是一键端的自己看你的一键端是stable分支还是development分支，（可以看java的版本，如
果是jdk8就是stable， jdk17就是development）,重新编译覆盖grasscutter.jar 可能是
grasscutter-1.0.0-dev.jar, 具体自己看是什么名字
## 第三步
(在手机上安装证书)
1. 需要安装两次
```不同的安卓型号的手机，操作不同，示例为红米10XPRO```
安装CA证书
打开设置一搜索证书一安装CA证书
安装WIFI证书
打开设置一搜索证书一安装WLAN证书
2. 安装完成后，证书部分结束
## 第四步
(开启WIAN代理)
wifi设置一手动一填写IP端口一保存
(开启流量代理)
![48484848](https://user-images.githubusercontent.com/45913291/166158012-5c172ee9-1a1e-472a-a139-b633638618c6.png)

## 第五步
重启服务端，重启手机，打开原神就可以玩了！！
