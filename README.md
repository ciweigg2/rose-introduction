# Rose 冠绝同侪 重塑网盘智能新体验

> 115 strm

`重构网盘与 Emby 的连接方式，让媒体库体验再度进化`

你可以把 Rose 理解成一层共享库管理服务：

- Emby 扫描的是一套共享出来的 .strm 目录。
- 用户看到的是同一套片库。
- 真正点播放时，再按当前 Emby 用户绑定的账号去处理。

---

`docker部署`

```yaml
version: '3.9'
services:
  rose-emby-bridge:
    image: ciwei123321/rose:latest
    container_name: rose
    uts: host
    environment:
      ROSE_ADMIN_PASSWORD: rose123
      TZ: Asia/Shanghai
      EMBY_UPSTREAM: http://192.168.2.107:8096/emby
    ports:
      - "8787:8787"
      - "8788:8788"
    volumes:
      - ./data:/app/data
      - ./strm:/app/strm
    restart: always
```

[官网](https://rosehub.ccwu.cc/)

[Telegram](https://t.me/bloodyrosehub)
