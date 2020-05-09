## 前言
### 闲来无事，看看docker的基本操作。 [docker 从入门到实践](https://yeasy.gitbook.io/docker_practice/)

## docker简易操作随笔
#### 获取镜像
docker pull [选项] [Docker Registry 地址[:端口号]/]仓库名[:标签]

举例：docker pull ubuntu:18.04

#### 运行镜像
docker run -it --rm ubuntu:18.04 bash

-it： -i 交互式操作  -t 终端 
--rm：容器退出之后直接将其删除
ubuntu:18.04：这是指用ubuntu:18.04镜像
bash：放在镜像名后的是**命令**，这里我们是希望是用bash当做命令行交互工具

#### 列出镜像
docker image ls -f -p --format

-f：是指filter 可以通过 docker image -f since=mongo:3.2 这是在mongo:3.2之后建立的镜像
-format: 指定格式输出，通过GO语言的模板语法 docker image 

##### 注：列表中包含的镜像体积所标识的空间未必是真实每个镜像所占用的空间，因为不同镜像间可能存在继承相同上层镜像的情况，相同的层只保存一份就够了，所以实际占用的空间可能要比这个列表镜像的总和要小的多

#### 虚悬镜像

造成的原因是因为新镜像和旧镜像的名称相同，名称优先应用到新镜像上面，导致旧的镜像就没有了名字。 造成的指令包括：docker pull 、docker build 
一般这种镜像无太大用处，可随意删除

#### 中间层镜像

为了加速镜像的构建，docker 会利用中间层镜像，可通过docker image ls -a 观察到相关镜像，这些镜像虽然没有名称和虚悬镜像类似，但是却是有用的镜像，不可随意删除

#### 
