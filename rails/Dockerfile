FROM ruby:3.0.2
EXPOSE 3000

MAINTAINER willx12123 <willx12123@gmail.com>

SHELL ["/bin/bash", "-c"]

RUN echo "deb http://mirrors.ustc.edu.cn/debian stable main contrib non-free \
          deb http://mirrors.ustc.edu.cn/debian stable-updates main contrib non-free" > /etc/apt/sources.list \
        && echo "alias ll='ls $LS_OPTIONS -l'" >> ~/.bashrc

RUN apt-get update \
        && apt-get upgrade -y \
        && apt-get install vim wget curl gcc git sqlite3 htop -y

RUN cd ~ \
        && apt-get install wget \
        && wget https://nodejs.org/dist/v14.17.6/node-v14.17.6-linux-x64.tar.xz \
        && tar -xf ./node-v14.17.6-linux-x64.tar.xz && rm node-v14.17.6-linux-x64.tar.xz && mv node-v14.17.6-linux-x64 /usr/local/node \
        && echo "export PATH='/usr/local/node/bin:$PATH'" >> ~/.bashrc \
        && source ~/.bashrc \
        && node -v && npm -v \
        && npm config set registry https://registry.npm.taobao.org \
        && npm i -g npm \
        && npm install -g yarn

RUN gem sources --add https://gems.ruby-china.com/ --remove https://rubygems.org/ \
        && bundle config mirror.https://rubygems.org https://gems.ruby-china.com \
        && gem update --system \
        && gem install rails
