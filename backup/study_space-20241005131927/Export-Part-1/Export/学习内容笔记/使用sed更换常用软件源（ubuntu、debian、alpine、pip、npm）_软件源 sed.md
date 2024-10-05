# 使用sed更换常用软件源（ubuntu、debian、alpine、pip、npm）_软件源 sed-CSDN博客

![https://www.notion.so./使用sed更换常用软件源（ubuntu、debian、alpine、pip、npm）_软件源%20sed-CSDN博客_files/20201124032511.png](https://www.notion.so./使用sed更换常用软件源（ubuntu、debian、alpine、pip、npm）_软件源%20sed-CSDN博客_files/20201124032511.png)

# 使用sed更换常用软件源（ubuntu、debian、alpine、pip、np

![https://www.notion.so./使用sed更换常用软件源（ubuntu、debian、alpine、pip、npm）_软件源%20sed-CSDN博客_files/original.png](https://www.notion.so./使用sed更换常用软件源（ubuntu、debian、alpine、pip、npm）_软件源%20sed-CSDN博客_files/original.png)

## ubuntu24.04

```
# 腾讯源
cat > /etc/apt/sources.list.d/ubuntu.sources<< EOF
Types: deb
URIs: http://mirrors.cloud.tencent.com/ubuntu/
Suites: noble noble-updates noble-security
Components: main restricted universe multiverse
Signed-By: /usr/share/keyrings/ubuntu-archive-keyring.gpg
EOF
```

## ubuntu22.04

中科大软件源

```
sed -i 's#http://archive.ubuntu.com#https://mirrors.ustc.edu.cn#g' /etc/apt/sources.list
sed -i 's#http://security.ubuntu.com#https://mirrors.ustc.edu.cn#g' /etc/apt/sources.list
```

## ubuntu(arm)

```
sed -i 's/ports.ubuntu.com/mirrors.tuna.tsinghua.edu.cn/g' /etc/apt/sources.list
```

## RockyLinux9

```
sed -e 's|^mirrorlist=|#mirrorlist=|g' -e 's|^#baseurl=http://dl.rockylinux.org/$contentdir|baseurl=https://mirrors.cloud.tencent.com/rocky|g' -i.bak /etc/yum.repos.d/rocky*.repo
```

## debian12

```
sed -i 's/deb.debian.org/mirrors.ustc.edu.cn/g' /etc/apt/mirrors/debian.list
sed -i 's/deb.debian.org/mirrors.ustc.edu.cn/g' /etc/apt/mirrors/debian-security.list
```

## debian

```
sed -i 's#http://deb.debian.org#https://mirrors.ustc.edu.cn#g' /etc/apt/sources.list
sed -i 's|security.debian.org/debian-security|mirrors.ustc.edu.cn/debian-security|g' /etc/apt/sources.list
```

## alpine

```
sed -i 's/dl-cdn.alpinelinux.org/mirrors.ustc.edu.cn/g' /etc/apk/repositories
```

## pip

```
pip config set global.index-url https://mirrors.cloud.tencent.com/pypi/simple
```

## npm

```
npm config set registry https://registry.npm.taobao.org

```

## yarn

```
yarn config set registry https://registry.npm.taobao.org/

```

## openwrt

```
sed -i 's_downloads.openwrt.org_mirrors.tuna.tsinghua.edu.cn/openwrt_' /etc/opkg/distfeeds.conf
```