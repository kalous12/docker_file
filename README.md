# docker_file

## dockerfile的应用

### 获得源码
   
```bash
git clone --depth=1 https://github.com/kalous12/docker_file.git
```

### 创建docker镜像
   
```bash
docker build -t ${name:tag} ${dir}
```

例子如下

- 构建使用root用户的docker镜像

```bash
#构建ubuntu22.04
docker build -t ubuntu22.04:root root/ubuntu-22.04
#构建ubuntu20.04
docker build -t ubuntu20.04:root root/ubuntu-20.04
```

- 构建使用普通用户的docker镜像

```bash
#构建ubuntu22.04
docker build -t ubuntu22.04:user user/ubuntu-22.04
#构建ubuntu20.04
docker build -t ubuntu20.04:user user/ubuntu-20.04
```

### 创建docker容器

```bash
#运行容器
docker run -t -i --privileged ${name:tag} /bin/bash
```
- 运行root用户的docker容器

例子如下:

```bash
#构建ubuntu22.04
docker run -t -i --privileged ubuntu22.04:root /bin/bash
#构建ubuntu20.04
docker run -t -i --privileged ubuntu20.04:root /bin/bash
```

- 运行普通用户的docker容器

```bash
#构建ubuntu22.04
docker run -t -i --privileged ubuntu22.04:user /bin/bash
#构建ubuntu20.04
docker run -t -i --privileged ubuntu20.04:user /bin/bash
```

## docker的其他应用

```bash

#停止所有的容器
docker stop $(docker ps -aq)
#删除所有的容器
docker rm $(docker ps -aq)
#删除所有的镜像
docker rmi $(docker images -q)

#清除不使用的镜像
docker image prune -f -a
#清除不使用的容器
docker container prune -f

```


<p align="right">write by ZeroK</p>
