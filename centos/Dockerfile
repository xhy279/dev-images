FROM centos:centos7.9.2009
RUN yum -y update && \
	yum -y install net-tools vim zsh gcc epel-release && \
	yum repolist && \
	yum -y install nginx && \
	yum clean all
RUN curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs |  sh -s -- -y
COPY ./.vimrc /root
CMD ["/usr/bin/zsh"]
