FROM centos

RUN yum upgrade -y && \
	yum groupinstall -y 'Development Tools' && \
	yum install -y \
	sudo \
	git \
	wget \
	tmux \
	vim \
	zsh \
	sbt \
	python-pip \
	python-devel && \
	yum clean all && rm -rf /var/cache/yum/*

RUN adduser PlayerOne -s /bin/zsh && \
    echo "PlayerOne ALL=(root) NOPASSWD:ALL" | tee -a /etc/sudoers.d/user && \
    chmod 0440 /etc/sudoers.d/user

RUN cd /home/PlayerOne && \
    sudo -u PlayerOne wget https://github.com/gutsche/docker-containers/raw/master/centos7-container/setup.tgz && \
    sudo -u PlayerOne tar xzf setup.tgz && \
    sudo -u PlayerOne rm setup.tgz

CMD ["su", "-", "PlayerOne"]
