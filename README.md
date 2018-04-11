cifaz.ansible-jumpserver
========================

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

 *** 注: 如果需要数据库, 请先安装数据库和redis, 本playbook暂未直接安装 ***
```

###
1. phyton3固定安装目录 /opt/py3
2. jumpserver固定下载目录 /opt/jumpserver
3. 管理命令 /opt/jumpserver/jms start / stop / status