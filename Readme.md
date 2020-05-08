## 前言
### 闲来无事，看看docker的基本操作。 [docker 从入门到实践](https://yeasy.gitbook.io/docker_practice/)

## docker简易操作随笔
#### 获取镜像
docker pull [选项] [Docker Registry 地址[:端口号]/]仓库名[:标签]

举例：docker pull ubuntu:18.04

#### 运行镜像
docker run -it --rm ubuntu:18.04 bash

-it： -i 交互式操作  -t 终端 
