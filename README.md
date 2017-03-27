# Dockerfile
Dockerized apps.

## Aria2

### Usage:

docker run -d -p YOUR-PORT:6800 -v YOUR-DOWNLOAD-FOLDER:/app/download evlos/aria2 --rpc-user=YOUR-USERNAME --rpc-passwd=YOUR-PASSWORD

## GitLab

Official dockerfile: [https://gitlab.com/gitlab-org/gitlab-ce/tree/master/docker](https://gitlab.com/gitlab-org/gitlab-ce/tree/master/docker)

## Gitblit

Official dockerfile: [https://github.com/gitblit/gitblit-docker](https://github.com/gitblit/gitblit-docker)



原帖：https://www.v2ex.com/t/205762


刚才写完了可以配合 Aria2 WebUI 使用的 aria2 Dockerfile，来分享一下。

https://github.com/Evlos/dockerfile

Usage
因为仓库已经被发布到了 Docker Hub，所以只要装了 docker，用下面一行指令就可以全部搞定啦。

docker run -d -p 开放端口:6800 -v 下载目录:/app/download evlos/aria2 --rpc-user=用户名 --rpc-passwd=密码
之后打开 Aria2 WebUI，在 Connection Settings 里填写你服务器的 IP、端口、用户名和密码即可连接。

http://ziahamza.github.io/webui-aria2/

Example
以下是命令示例：

docker run -d -p 8081:6800 -v /var/www/html/aria2:/app/download evlos/aria2 --rpc-user=username --rpc-passwd=password
8081 是我对外开放的 aria2 RPC 端口。
/var/www/html/aria2 是我的容器外部下载目录。因为容器外部有一个 nginx 服务器的目录被设置在了 /var/www/html，所以我可以先用 aria2 下载例如 Hacking Team 的种子，然后根据需求下载到本地，还可以直接在浏览器播放下载的 Youtube 视频。
目前我的 aria2 服务正常运行中：

aria2 服务正常运行中

希望对大家有帮助 :)。
