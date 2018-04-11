cifaz.ansible-jumpserver
========================

Dependencies
------------

mysql/mariadb

 - geerlingguy.mysql
  
redis
  
  - DavidWittman.redis

### 变量请查看
[安装变量](vars/main.yml)

### 安装
```
ansible-galaxy install cifaz.jumpserver

```

### 单独启动
```
- hosts: jump
  remote_user: root
  roles:
    - {role: DavidWittman.redis, tag: "dbredis", redis_bind: 127.0.0.1}
    - geerlingguy.mysql
    - {role: "jumpserver", tag: "jumpserver"}
    # - {role: "jumpserver", tag: "jumpserver", db_passwd: "147258"}

 *** 注: 如果需要数据库, 请先安装数据库和redis, 本playbook暂未直接安装 ***
```

### 访问地址
http://127.0.0.1:8080(默认, 修改参数的请自行修改)

### 特别说明
1. phyton3固定安装目录 /opt/py3
2. jumpserver固定下载目录 /opt/jumpserver
3. 管理命令 /opt/jumpserver/jms start / stop / status

#####  注: 如果您安装成功后, 登陆时出现错误, 是因表数据未初始化完整, 请手工执行执行如下语句 

```
source /opt/py3/bin/activate && cd /opt/jumpserver/utils/ && /bin/bash make_migrations.sh

```