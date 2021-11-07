FROM debian:bookworm

LABEL MAINTAINER willx12123 <willx12123@gmail.com>

RUN cat /dev/null > /etc/apt/sources.list \
  && echo "deb http://mirrors.ustc.edu.cn/debian stable main contrib non-free \
           deb http://mirrors.ustc.edu.cn/debian stable-updates main contrib non-free" > /etc/apt/sources.list \
  && apt-get update \
  && apt-get upgrade -y

RUN echo "alias ll='ls $LS_OPTIONS -l'" >> ~/.bashrc

RUN apt-get install vim wget curl -y
