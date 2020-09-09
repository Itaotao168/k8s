#
# MAINTAINER        Carson,C.J.Zeong <zcy@nicescale.com>
# DOCKER-VERSION    1.6.2
#
# Dockerizing CentOS7: Dockerfile for building CentOS images
#
FROM centos:7.6.1810
MAINTAINER tao.mei <4836266@qq.com>

ENV TZ "Asia/Shanghai"
ENV TERM xterm
RUN yum install kde-l10n-Chinese -y 
RUN yum install glibc-common -y
RUN localedef -c -f UTF-8 -i zh_CN zh_CN.utf8
ENV LC_ALL zh_CN.UTF-8

RUN yum -y install fontconfig ttmkfdir
ADD simsun.ttc /usr/share/fonts
RUN chmod -R 755 /usr/share/fonts && ttmkfdir -e /usr/share/X11/fonts/encodings/encodings.dir 
ADD fonts.conf /etc/fonts/fonts.conf
ADD aliyun-mirror.repo /etc/yum.repos.d/CentOS-Base.repo
ADD aliyun-epel.repo /etc/yum.repos.d/epel.repo

RUN  yum install -y java-1.8.0-openjdk maven curl git libtool-ltdl-devel && \
     yum clean all && \
     rm -rf /var/cache/yum/* && \
     mkdir -p /usr/share/jenkins

COPY  agent.jar  /usr/share/jenkins/agent.jar
COPY  jenkins-slave  /usr/bin/jenkins-slave
COPY  settings.xml  /etc/maven/settings.xml
RUN   chmod +x /usr/bin/jenkins-slave
COPY  helm kubectl  /usr/bin/

ENTRYPOINT ["jenkins-slave"]
