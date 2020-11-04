FROM node:slim
MAINTAINER xuwencheng jack2411314@vip.qq.com
# instal basic tool 
RUN apt-get update && apt-get install -y wget git ssh-client ca-certificates --no-install-recommends && rm -r /var/lib/apt/lists/*
# set time zone
RUN echo "Asia/Shanghai" > /etc/timezone && dpkg-reconfigure -f noninteractive tzdata
# install hexo
RUN wget https://nodejs.org/download/release/v12.14.0/node-v12.14.0-linux-x64.tar.xz .
RUN tar -xf node-v12.14.0-linux-x64.tar.xz . && mv node-v12.14.0-linux-x64 nodejs && rm -rf /usr/local/bin/nodejs /usr/local/bin/node /usr/local/bin/npm && mv nodejs /usr/local/bin && ln -s /usr/local/bin/nodejs/bin/node /usr/local/bin/ && ln -s /usr/local/bin/nodejs/bin/npm /usr/local/bin/
RUN npm install hexo-cli -g
RUN ln -s /usr/local/bin/nodejs/bin/hexo /usr/local/bin/hexo
# set base dir
#RUN mkdir /hexo
# set home dir
#WORKDIR /hexo

EXPOSE 4000
#CMD ["/bin/bash"]