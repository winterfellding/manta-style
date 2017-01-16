### What is this

This project is a guide for speeding up some common dev tools.

### Gloablly

Shadowsocks is a good option.

### brew

brew use curl as download tool below, so you can add a .curlrc file in the home directory,
and add `socks5 = "127.0.0.1:1080"` using shadowsocks as your proxy server.

### maven

aliyun has a mirror nexus, copy the following code into ~/.m2/settings.xml's mirrors tag
```xml
 <mirror>
    <id>nexus-aliyun</id>
    <mirrorOf>*</mirrorOf>
    <name>Nexus aliyun</name>
    <url>http://maven.aliyun.com/nexus/content/groups/public</url>
</mirror> 
```
### pip

douban has a mirror pip server, copy the following code into ~/.pip/pip.conf
```
[global]
index-url = http://pypi.douban.com/simple
trusted-host = pypi.douban.com
```
### git

git support http.proxy and https.proxy, you can use `git config --global http.proxy http://proxy.mycompany:80`, when using shadowsocks, use the `socks5://127.0.0.1:1080` protocol, you can also add code below into `~/.gitconfig`

```
[http]
    proxy = socks5://127.0.0.1:1080
[https]
    proxy = socks5://127.0.0.1:1080
```

### npm 

taobao has a npm mirror, use `npm config set registry http://registry.npm.taobao.org`, you can also use `cnpm` or alias a npm with registry option, please follow the instrction from [taobao registry](https://npm.taobao.org/).