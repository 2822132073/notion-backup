# 二进制安装openresty

## openresty源码下载地址

[OpenResty - Download](https://openresty.org/en/download.html#lastest-release)

### 编译安装过程

[](https://openresty.org/en/installation.html#building-from-source)

## 编译环境

```bash
[root@nginx ~]# lsb_release -a
No LSB modules are available.
Distributor ID:	Ubuntu
Description:	Ubuntu 18.04.5 LTS
Release:	18.04
Codename:	bionic
[root@nginx ~]# uname -a
Linux nginx 4.15.0-143-generic #147-Ubuntu SMP Wed Apr 14 16:10:11 UTC 2021 x86_64 x86_64 x86_64 GNU/Linux
[root@nginx ~]# ll |grep open
-rw-r--r--  1 root root 5837745 Jul 16 20:55 openresty-1.25.3.2.tar.gz
```

## 编译过程

```bash
[root@nginx ~]# wget https://openresty.org/download/openresty-1.25.3.2.tar.gz
[root@nginx ~]# tar -xf openresty-1.25.3.2.tar.gz 
[root@nginx ~]# ln -s openresty-1.25.3.2 openresty
[root@nginx ~]# cd openresty
[root@nginx ~/openresty]# ./configure -j2
[root@nginx ~/openresty]# make -j2
[root@nginx ~/openresty]# make install
```

> 默认安装在 `/usr/local/opemresty/` 下，配置文件在下面目录：
> 
> 
> `/usr/local/openresty/nginx/conf/nginx.conf`
> 

```bash
http {
    include       mime.types;
    default_type  application/octet-stream;
    include conf.d/*.conf;
......
```

> 默认的配置文件没有include conf文件，和nginx不一样，所以需要手动的加入。
> 

> 可以在~/bashrc中添加这个，后面启动重启，就不需要去写太长的命令
> 

```bash
alias openresty="/usr/local/openresty/bin/openresty -c /usr/local/openresty/nginx/conf/nginx.conf" 
```