视频互通（网页版）
---

### 本机联调

浏览器直接打开两个index.html页

### 内网联调

A机：

```
npm install live-server -g
openssl req -newkey rsa:2048 -new -nodes -x509 -days 3650 -keyout key.pem -out cert.pem
live-server . --https=./config.js
https://127.0.0.1:54847
```

live-server

本地开发常常需要搭建临时的服务，第一时间我们会想到用http-server。
现在流行修改文件浏览器自动刷新hot socketing（热拔插），如live-reload。
若想浏览器自动打开项目，用opener。
现在live-server实现了三个插件的所有功能，并且很简单就能启动一个看起来很专业的本地服务。

>https://www.npmjs.com/package/live-server

config.js模块

该模块用来配置https

```
var fs = require('fs');

module.exports = {
	key: fs.readFileSync('./key.pem'),
	cert: fs.readFileSync('./cert.pem'),
	passphrase: ""
};
```

B机：

```
https://A机IP:54847
```

### 连接

- App ID
- Channel
- Token

以上3个参数从[声网开发者中心](https://docs.agora.io/en)获取。双端对等输入即可互通
