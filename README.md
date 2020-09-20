# nginx-forward-proxy-docker
nginx支持https正向代理镜像，基于chobits/ngx_http_proxy_connect_module

从 https://github.com/chobits/ngx_http_proxy_connect_module 下载主分支包ngx_http_proxy_connect_module.tar.gz，放在Dockerfile同目录

正向代理配置见 https://github.com/chobits/ngx_http_proxy_connect_module#configuration-example


# forker comment

打包镜像并运行：
```shell
docker build -t forward-proxy-via-nginx:v1.0.0 .
docker run -p 80:80 -d forward-proxy-via-nginx:v1.0.0
```

在其他机器上测试：
```shell
curl --proxy $your_vm_ip http://www.baidu.com/s\?wd\=ip 2>/dev/null | grep 本机IP:
```
