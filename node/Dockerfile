FROM willx12123/mydebian:v1

LABEL MAINTAINER willx12123 <willx12123@gmail.com>

SHELL ["/bin/bash", "-c"]

RUN cd ~ \
        && wget https://mirrors.ustc.edu.cn/node/v16.13.0/node-v16.13.0-linux-x64.tar.gz \
        && tar -zxvf ./node-v16.13.0-linux-x64.tar.gz \
        && mv ./node-v16.13.0-linux-x64 /usr/local/node && rm node-v16.13.0-linux-x64.tar.gz \
        && echo -e "\nexport PATH='/usr/local/node/bin:$PATH'" >> ~/.bashrc \
        && source ~/.bashrc \
        && npm config set registry https://registry.npmmirror.com \
        && npm i -g npm \
        && npm i -g yarn pm2
