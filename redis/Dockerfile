FROM centos:base

RUN yum install -y ruby ruby-devel rubygems rpm-build

RUN gem install redis

ENV REDIS_VERSION="3.2.9"

RUN  wget http://download.redis.io/releases/redis-${REDIS_VERSION}.tar.gz -O /opt/redis-${REDIS_VERSION}.tar.gz

RUN tar vxf /opt/redis-${REDIS_VERSION}.tar.gz -C /opt

RUN ln -s /opt/redis-${REDIS_VERSION} /opt/redis

RUN cd /opt/redis && make distclean && make install

RUN echo 'vm.overcommit_memory = 1' >> /etc/sysctl.conf


