# DEMO ONLYOFFICE

基于 Nest 和 Vue.js 的 Onlyoffice 示例。


## 快速开始

注意，在启动之前，需要将 **onlyoffice-vue/.env** 里面的 `VUE_APP_HOST` 和 **onlyoffice-server/.env** 里面的 `HOST` 字段统一替换成自己的本机 IP。

```bash
# 启动前端
cd onlyoffice-vue
# 安装依赖
pnpm install
# 启动开发服务
pnpm run dev

# 启动后端
cd onlyoffice-server
# 安装依赖
pnpm install
# 启动开发服务
pnpm run dev
```

- [使用文档](https://blog.bszhct.com/2022/08/15/onlyoffice-quick-start/)

# 启动docker
```js
docker run -itd --name onlyoffice --restart always -p 8090:80 -v /data/docker/onlyoffice/log:/var/log/onlyoffice  -v /data/docker/onlyoffice/data:/var/www/onlyoffice/Data  -v /data/docker/onlyoffice/lib:/var/lib/onlyoffice -v /data/docker/onlyoffice/db:/var/lib/postgresql onlyoffice/documentserver
```
# 启动所有服务
docker exec -it containerID /bin/bash
supervisorctl restart all

# 获取秘钥
docker exec containerID /var/www/onlyoffice/documentserver/npm/json -f /etc/onlyoffice/documentserver/local.json 'services.CoAuthoring.secret.session.string'

# 秘钥位置
/etc/onlyoffice/documentserver/local.json 


## License

[MIT](/LICENSE)



