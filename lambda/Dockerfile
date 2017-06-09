FROM amazonlinux
MAINTAINER ecleya <ecleya@gmail.com>

RUN yum -y update && \ 
    yum -y upgrade && \
    yum -y groupinstall "Development Tools" && \
    yum -y install git curl openssl openssl-devel zlib zlib-devel readline readline-devel bzip2 bzip2-devel sqlite sqlite-devel && \
    yum clean all

ENV LANG=en_US.utf8
ENV LC_ALL=en_US.utf8
ENV LANGUAGE=en_US.utf8

RUN git clone git://github.com/yyuu/pyenv.git /tmp/pyenv && \
    cd /tmp/pyenv/plugins/python-build && \
    ./install.sh

RUN python-build 3.6.0 /usr/local/share/python-3.6.0

RUN \
  bash -c "ln -s /usr/local/share/python-3.6.0/bin/{2to3,easy_install,idle,idle3.6,pip3,pydoc,pydoc3.6,python-config,python3-config,python3.6-config,python3.6m-config,pyvenv-3.6,2to3-3.6,easy_install-3.6,idle3,pip,pip3.6,pydoc3,python,python3,python3.6,python3.6m,pyvenv} /usr/local/bin"
