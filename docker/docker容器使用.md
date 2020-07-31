容器和镜像的区别
容器是一个抽象的概念，镜像是将容器实例化的

1、拉取镜像
docker pull 镜像名称
e.g docker pull ubuntu

2、列出镜像
docker images

3、删除镜像
docker rmi 镜像名称/镜像Id
e.g docker rmi ubuntu

4、启动容器
docker run -it 镜像名 /bin/bash
e.g docker run -it ubuntu /bin/bash

-i		交互式动作
-t		终端
/bin/bash	放在镜像名后面的是命令，这里希望有一个交互式shell

5、退出终端
exit

6、查看所有的容器
docker ps -a

7、后台运行，不进入容器
docker run -itd --name ubuntu-test ubuntu /bin/bash
e.g docker run -itd --name ubuntu-test ubuntu /bin/bash

-d 不进入容器

注意：
可通过以下指令进入容器
docker attach 容器Id	退出会导致容器的终止
docker exec 容器ID		退出不会导致容器的终止


8、进入容器
docker exec

9、启动已停止的容器
docker start 容器Id

10、停止容器
docker stop 容器ID

11、重启容器
docker restart 容器ID