FROM ubuntu:16.04
MAINTAINER zannb "zannb@outlook.com"

# 更新源，安装ssh server
RUN echo "# deb cdrom:[Ubuntu 16.04 LTS _Xenial Xerus_ - Release amd64 (20160420.1)]/ xenial main restricted\ndeb-src http://archive.ubuntu.com/ubuntu xenial main restricted #Added by software-properties\ndeb http://mirrors.aliyun.com/ubuntu/ xenial main restricted\ndeb-src http://mirrors.aliyun.com/ubuntu/ xenial main restricted multiverse universe #Added by software-properties\ndeb http://mirrors.aliyun.com/ubuntu/ xenial-updates main restricted\ndeb-src http://mirrors.aliyun.com/ubuntu/ xenial-updates main restricted multiverse universe #Added by software-properties\ndeb http://mirrors.aliyun.com/ubuntu/ xenial universe\ndeb http://mirrors.aliyun.com/ubuntu/ xenial-updates universe\ndeb http://mirrors.aliyun.com/ubuntu/ xenial multiverse\ndeb http://mirrors.aliyun.com/ubuntu/ xenial-updates multiverse\ndeb http://mirrors.aliyun.com/ubuntu/ xenial-backports main restricted universe multiverse\ndeb-src http://mirrors.aliyun.com/ubuntu/ xenial-backports main restricted universe multiverse #Added by software-properties\ndeb http://archive.canonical.com/ubuntu xenial partner\ndeb-src http://archive.canonical.com/ubuntu xenial partner\ndeb http://mirrors.aliyun.com/ubuntu/ xenial-security main restricted\ndeb-src http://mirrors.aliyun.com/ubuntu/ xenial-security main restricted multiverse universe #Added by software-properties\ndeb http://mirrors.aliyun.com/ubuntu/ xenial-security universe\ndeb http://mirrors.aliyun.com/ubuntu/ xenial-security multiverse\n"  >>/etc/apt/sources.list
RUN apt-get update
RUN apt-get install -y make build-essential  \
        libxml2-dev libxslt1-dev \
        libssl-dev zlib1g-dev \
        libbz2-dev libreadline-dev libsqlite3-dev \
        llvm libncurses5-dev \
        git vim zsh curl wget
RUN apt-get install -y openssh-server openssh-client
RUN mkdir /var/run/sshd

# 设置root ssh远程登录密码为123456
RUN echo "root:123456" | chpasswd

# 容器需要开放SSH 22端口
EXPOSE 22