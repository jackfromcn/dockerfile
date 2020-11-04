FROM ubuntu:16.04
MAINTAINER xuwencheng jack2411314@vip.qq.com
# instal basic tool 
RUN apt-get update \
    && apt-get install -y wget git ssh-client ca-certificates --no-install-recommends \
    && rm -r /var/lib/apt/lists/*
# set time zone
RUN echo "Asia/Shanghai" > /etc/timezone && dpkg-reconfigure -f noninteractive tzdata
# install hexo
WORKDIR /root
ADD node-v12.14.0-linux-x64.tar.xz .
RUN mv node-v12.14.0-linux-x64 nodejs \
    && rm -rf /root/node-v12.14.0-linux-x64.tar.xz /usr/local/bin/nodejs /usr/local/bin/node /usr/local/bin/npm \
    && mv nodejs /usr/local/bin \
    && ln -s /usr/local/bin/nodejs/bin/node /usr/local/bin/ \
    && ln -s /usr/local/bin/nodejs/bin/npm /usr/local/bin/
RUN npm install hexo-cli -g \
    && ln -s /usr/local/bin/nodejs/bin/hexo /usr/local/bin/hexo
# set base dir
#RUN mkdir /hexo
# set home dir
#WORKDIR /hexo

EXPOSE 4000
#CMD ["/bin/bash"]