> 使用声明

避免造成被喝茶的结局，请妥善使用翻墙工具。不作恶，不营利，且翻且珍惜。  
另外，小主会不定期的更新google ip，请保持关注，如不能FQ，请下载最新包。

> 翻墙原理简介

通过将goagent server部署在google appengine上，并在本地启动goagent local代理服务器。  
配置好google ip便于goagent local查找gae，配置好appid便于定位到gae上的goagent server。  
二者配置完成后，通过本地浏览器代理访问本地goagent local代理服务器。goagent local将请求转发到gae上的goagent server，goagent server访问外网数据并返回给goagent local并交由浏览器。  
由于gae是不受GFW屏蔽的，这样即可FQ。

> 翻墙步骤简介

(推荐查看下一节，本节写给熟练者看)  
1. 使用内置appid账号翻墙；  
goagent-goagent-985cbd5是已经配置好appid的goagent包  ，可以跳到第5-6步实现翻墙。
翻墙后完成2-3-4操作后到goagent/local/proxy.ini中更新为自己appid (可选)  
2. 申请google account并创建gae appid； (可选)  
申请完成后可查看appid [Google Projects List](https://console.developers.google.com/project?pli=1 "谷歌appid项目列表")  
3. 使用google account及appid将goagent/server(update.bat)上传到google appengine； (可选)  
需要[开启gae密码弱应用](https://console.developers.google.com/project?pli=1 "开启gae密码弱应用")  
4. 配置goagent/local/proxy.ini中的appid/google ip(proxy.ini)； (可选)  
google ip采用推荐的ip，如果后期google ip失效，可使用gogotester查找可用的google ip  
5. 安装CA.crt证书，启动goagent local； (可选)  
6. 安装Chrome插件SwitchyOmega.crx并导入配置OmegaOptions.bak开启本地代理 (可选)  


> 翻墙步骤细节(强烈推荐)  

[Go-Agent部署与FQ教程](http://www.cnblogs.com/tesky0125/p/5347409.html "Go-Agent部署与FQ教程")  
http://www.cnblogs.com/tesky0125/p/5347409.html  

> linux下翻墙的补充

1. 基本步骤与windows下相似

2. 需要安装brew和python

常见错误1：NameError: name 'PROTOCOL_SSLv3' is not defined
修改/home/cgre/google_appengine/goagent-goagent-437a921/local/packages.egg/linux/gevent/ssl.py的line 386
```
- def get_server_certificate(addr, ssl_version=PROTOCOL_SSLv3, ca_certs=None):
+ def get_server_certificate(addr, ssl_version=PROTOCOL_TLSv1, ca_certs=None):
```
原因：
* SSLv3协议由于设计缺陷已经被python禁用，可以使用TLSv1协议代替


常见错误2：如果出现No module named openSSL
安装brew、openSSL、python
```
$ sudo apt-get install python-openssl
```

常见错误3：未安装pycrypto，需要安装pycrypto
```
$ sudo apt-get install python-crypto
```

常见错误4：证书不受信任
在证书导入第三栏把goangent的证书改为受信任

然后
```
sudo python proxy.py
```
愉快的翻墙吧~

> 翻墙原理介绍 

[Go-Agent原理分析及FQ介绍](http://www.cnblogs.com/tesky0125/p/4889637.html "Go-Agent原理分析及FQ介绍")  
http://www.cnblogs.com/tesky0125/p/4889637.html  

> 致敬GoAgent  

https://github.com/phuslu/goagent  
https://github.com/phuslu/goproxy  

