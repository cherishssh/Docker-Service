### 目录

<!-- MarkdownTOC -->

- [初始化操作](#%E5%88%9D%E5%A7%8B%E5%8C%96%E6%93%8D%E4%BD%9C)
    - [环境](#%E7%8E%AF%E5%A2%83)
    - [安装Docker](#%E5%AE%89%E8%A3%85docker)
- [部署服务](#%E9%83%A8%E7%BD%B2%E6%9C%8D%E5%8A%A1)
    - [启动 Zabbix](#%E5%90%AF%E5%8A%A8-zabbix)
    - [访问 Zabbix](#%E8%AE%BF%E9%97%AE-zabbix)

<!-- /MarkdownTOC -->



`作者信息`
```
# Author: SunShaoHua
# Date:   2021-01-11 09:58:33
# Email:  cherishaohua@foxmail.com
# Adress: ShangHai/China
# Last Modified by:   SunShaoHua
```


### 初始化操作

#### 环境
|  操作系统 | CPU | 内存 |
|-----------|-----|------|
| CentOS7.* |   1 | 2G   |

#### 安装Docker
```
# 安装必要的一些系统工具
yum install -y yum-utils device-mapper-persistent-data lvm2
# 添加软件源信息
yum-config-manager --add-repo https://mirrors.aliyun.com/docker-ce/linux/centos/docker-ce.repo
# 更新并安装Docker-CE
yum makecache fast
yum -y install docker-ce
systemctl start docker
```

### 部署服务

#### 启动 Zabbix
`启动 Zabbix Server Container`

```
docker run --name zabbix-appliance -p 80:80 -p 10051:10051 -d zabbix/zabbix-appliance:latest
```

#### 访问 Zabbix
`访问 Zabbix Server Container`
```
http://$LOCALHOST/zabbix  即可访问 zabbix 的 web 页面
```

`初始默认用户/密码`
```
USER: Admin
PASS: zabbix
```
至此Zabbix Server安装完成!!

<H2><Center>打赏作者喝杯咖啡</Center></H2>
<H3><center>如果觉得我的文章对您有用,请随意打赏.您的支持将鼓励我继续创作！(PS:拒绝白嫖)</center></H3>

- [x]微信还是支付宝？

<img src="https://gitee.com/cherishssh/images/raw/master/Image/Wechat.jpeg" height="340" width="235"> <img src="https://gitee.com/cherishssh/images/raw/master/Image/WechatAL.jpeg" height="340" width="235">
