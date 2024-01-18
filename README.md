# 构建gitlab私有仓库

## 使用Docker容器部署

    1、Win10环境下(文件外挂映射在D盘)

        docker run -d -p 48443:443 -p 48080:80 -p 48022:22 --name gitlab -v /d/gitlab/config:/etc/gitlab:rw -v /d/gitlab/logs:/var/log/gitlab:rw -v /d/gitlab/data:/var/opt/gitlab:rw --privileged=true gitlab/gitlab-ce

    2、Linux环境下

        docker run --detach \
        --hostname gitlab.example.com \
        --publish 443:443 --publish 80:80 --publish 22:22 \
        --name gitlab \
        --restart always \
        --volume /srv/gitlab/config:/etc/gitlab \
        --volume /srv/gitlab/logs:/var/log/gitlab \
        --volume /srv/gitlab/data:/var/opt/gitlab \
        gitlab/gitlab-ce:latest

## Docker-Compose构建环境

    请查看docker-compose文件夹

