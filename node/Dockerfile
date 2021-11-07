FROM centos:centos7.9.2009

LABEL MAINTAINER willx12123 <willx12123@gmail.com>

RUN sed -e 's|^mirrorlist=|#mirrorlist=|g' \
        -e 's|^#baseurl=http://mirror.centos.org/centos|baseurl=https://mirrors.ustc.edu.cn/centos|g' \
        -i.bak /etc/yum.repos.d/CentOS-Base.repo \
        && yum makecache \
        && yum install vim wget gcc curl git -y

RUN cd ~ \
        && wget https://mirrors.ustc.edu.cn/node/v16.13.0/node-v16.13.0-linux-x64.tar.gz \
        && tar -zxvf ./node-v16.13.0-linux-x64.tar.gz \
        && mv ./node-v16.13.0-linux-x64 /usr/local/node && rm node-v16.13.0-linux-x64.tar.gz \
        && echo -e "\nexport PATH='/usr/local/node/bin:$PATH'" >> ~/.bashrc \
        && source ~/.bashrc

RUN npm config set registry https://registry.npmmirror.com \
        && npm i -g npm \
        && npm i -g yarn pm2
