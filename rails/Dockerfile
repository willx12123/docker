FROM ruby:3.0.2
EXPOSE 3000

MAINTAINER willx12123 <willx12123@gmail.com>

SHELL ["/bin/bash", "-c"]

RUN echo "deb http://mirrors.ustc.edu.cn/debian stable main contrib non-free \
          deb http://mirrors.ustc.edu.cn/debian stable-updates main contrib non-free" > /etc/apt/sources.list

RUN apt-get update \
        && apt-get upgrade -y \
        && apt-get install vim wget curl git sqlite3 htop -y

RUN cd ~ \
        && wget https://nodejs.org/dist/v14.17.5/node-v14.17.5-linux-x64.tar.xz \
        && tar -xf ./node-v14.17.5-linux-x64.tar.xz && rm node-v14.17.5-linux-x64.tar.xz && mv node-v14.17.5-linux-x64 /usr/local/node \
        && echo "export PATH='/usr/local/node/bin:$PATH'" >> ~/.bashrc \
        && source ~/.bashrc \
        && npm config set registry https://registry.npm.taobao.org \
        && npm i -g yarn

RUN gem sources --add https://gems.ruby-china.com/ --remove https://rubygems.org/ \
        && bundle config mirror.https://rubygems.org https://gems.ruby-china.com \
        && gem update --system \
        && gem install rails

