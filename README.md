#声明
避免造成被喝茶的结局，请妥善使用翻墙工具。

#翻墙原理
通过将goagent server部署在google appengine上，并在本地启动goagent local代理服务器，配置好google ip便于goagent local查找gae，配置好appid便于定位到gae上的goagent server,如此，通过本地浏览器代理访问本地代理goagent local，而goagent local将请求转发到gae上的goagent server，goagent server访问外网数据并返回给goagent local并交流浏览器。由于gae是不受GFW屏蔽的，这样既可翻墙。

#翻墙步骤
1. 使用推荐账号先翻墙；
goagent-goagent-985cbd5是已经配置好的goagent包
可以跳到第5-6步先翻墙，完成2-3-4操作后到goagent local中更新为自己appid
2. 申请google account并创建gae appid，具体操作可google；
https://console.developers.google.com/project?authuser=3
3. 使用google account及appid将goagent server上传到google appengine，具体操作可google；
需要开启gae密码弱应用 https://www.google.com/settings/security/lesssecureapps
4. 配置goagent local中的appid/google ip(proxy.ini)；
google ip采用推荐的ip，如果后期google ip失效，可使用gogotester查找可用的google ip
5. 启动goagent local；
6. 安装chrome插件SwitchyOmega.crx并导入配置OmegaOptions.bak开启本地代理

#GoAgent
https://zh.wikipedia.org/wiki/GoAgent
http://baike.sogou.com/v44771164.htm

#Shadowsocks
https://zh.wikipedia.org/wiki/Shadowsocks

#可参考博客园文章
http://www.cnblogs.com/tesky0125/p/4889637.html

#懒人指南
https://github.com/XX-net/XX-Net
