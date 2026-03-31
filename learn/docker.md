

* settings-docker engine
>
{
  "builder": {
    "gc": {
      "defaultKeepStorage": "20GB",
      "enabled": true
    }
  },
  "experimental": false,
  "registry-mirrors": [
    "https://docker.211678.top",
    "https://docker.1panel.live",
    "https://hub.rat.dev",
    "https://docker.m.daocloud.io",
    "https://do.nark.eu.org",
    "https://dockerpull.com",
    "https://dockerproxy.cn",
    "https://docker.awsl9527.cn",
    "https://docker.mirrors.ustc.edu.cn",
    "https://hub-mirror.c.163.com",
    "https://cr.console.aliyun.com/"
  ]
}


![[Pasted image 20260310134751.png]]

* 已执行代码
[root@10-113-56-68 ~]# mkdir -p /root/mysql-data
[root@10-113-56-68 ~]# chown -R 999:999 /root/mysql-data
[root@10-113-56-68 ~]# docker run -d \
> --name mysql-server \
> --restart=always \
> -p 3306:3306 \
> -e MYSQL_ROOT_PASSWORD=123456 \
> -e MYSQL_INITDB_SKIP_TZINFO=1 \
> -v /root/mysql-data:/var/lib/mysql \
> mysql:latest


拉取镜像（能上网的Linux执行，本地使用docker desktop） 
   docker pull mysql:latest 
导出为tar包 
   docker save -o mysql-8.4-latest.tar mysql:latest
   >docker save -o D:\Mid\mysql-8.0.tar mysql:8.0

 * 格式：
 docker exec -it 容器名/ID mysql -uroot -p 
 例如：docker exec -it mysql-server mysql -uroot -p


* 完整步骤：
* 在本地window上下载Docker Desktop
* 配置docker engine
* 配置tar包
* 通过xftp传到linux中
* docker load -i /root/mysql-latest.tar加载
* docker images | grep mysql查询
* 配置mysql
* docker ps
* docker exec -it mysql-server mysql -uroot -p执行