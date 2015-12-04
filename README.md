#翻墙原理
通过将goagent server部署在google appengine上，并在本地启动goagent local代理服务器，配置好google ip便于goagent local查找gae，配置好appid便于定位到gae上的goagent server,如此，通过本地浏览器代理访问本地代理goagent local，而goagent local将请求转发到gae上的goagent server，goagent server访问外网数据并返回给goagent local并交流浏览器。由于gae是不受GFW屏蔽的，这样既可翻墙。

#翻墙步骤
0. 使用推荐账号先翻墙；
goagent-goagent-985cbd5是已经配置好的goagent包
可以跳到第4步先翻墙，完成以下操作后到goagent local中更新为自己appid
1. 申请google account并创建gae appid，具体操作可google；
https://console.developers.google.com/project?authuser=3
2. 使用google account及appid将goagent server上传到google appengine，具体操作可google；
需要开启gae密码弱应用 https://www.google.com/settings/security/lesssecureapps
3. 配置goagent local中的appid/google ip(proxy.ini)；
google ip采用推荐的ip，如果后期google ip失效，可使用gogotester查找可用的google ip
4. 启动goagent local；
5. 安装chrome插件SwitchySharp.crx并导入配置开启本地代理
