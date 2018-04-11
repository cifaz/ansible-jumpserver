cifaz.ansible-jumpserver
========================

### 安装
```
ansible-galaxy install cifaz.ansible-jumpserver

```


### 单独启动
```
- hosts: jump
  remote_user: root
  roles:
    - {role: DavidWittman.redis, tag: "dbredis", redis_bind: 127.0.0.1}
    - geerlingguy.mysql
    - {role: "jumpserver", tag: "jumpserver"}

```

###
1. phyton3固定安装目录 /opt/py3
2. jumpserver固定下载目录 /opt/jumpserver
