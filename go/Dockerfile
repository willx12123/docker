FROM centos:centos7.9.2009

MAINTAINER willx12123 <willx12123@gmail.com>

RUN sed -e 's|^mirrorlist=|#mirrorlist=|g' \
        -e 's|^#baseurl=http://mirror.centos.org/centos|baseurl=https://mirrors.ustc.edu.cn/centos|g' \
        -i.bak /etc/yum.repos.d/CentOS-Base.repo \
        && yum makecache \
        && yum install vim wget gcc curl git -y

RUN cd ~ \
        && wget https://mirrors.ustc.edu.cn/golang/go1.17.2.linux-amd64.tar.gz \
        && tar -zxvf ./go1.17.2.linux-amd64.tar.gz \
        && mv ./go /usr/local/go && rm go1.17.2.linux-amd64.tar.gz \
        && mkdir /go && cd /go && mkdir src bin pkg \
        && echo -e "\nexport PATH='/usr/local/go/bin:$PATH'\nexport GOPATH='/go'" >> ~/.bashrc \
        && source ~/.bashrc \
        && go env -w GO111MODULE=on && go env -w GOPROXY=https://goproxy.cn,direct
