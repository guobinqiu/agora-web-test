视频互通（网页版）
---

### 本机联调

不启服务：浏览器直接开两个index.html页

或

启http服务：`live-server . --port=5000`

### 内网联调

A机：

```
npm install live-server -g
openssl req -newkey rsa:2048 -new -nodes -x509 -days 3650 -keyout key.pem -out cert.pem
live-server . --https=./config.js --port=5000
```
启https服务，config.js是https的配置模块

live-server 
>https://www.npmjs.com/package/live-server

访问https://127.0.0.1:5000

B机：

访问https://A机ip:5000

连线：

- App ID
- Channel
- Token

从[声网开发者中心](https://docs.agora.io/en)获取。双端对等输入即可互通
