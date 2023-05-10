FROM python:3.6.15-alpine

ENV CRYPTOGRAPHY_DONT_BUILD_RUST=1
COPY top /usr/local/lib/python3.6/site-packages/top
COPY requirements.txt ./requirements.txt
COPY Shanghai /etc/localtime
# COPY rustup-init /tmp/rustup-init

#RUN apk add --no-cache gcc g++ make python3-dev libffi-dev mariadb-dev jpeg-dev xz-dev bzip2-dev libevent-dev bash
RUN apk add --no-cache libffi-dev mariadb-dev jpeg-dev xz-dev bzip2-dev build-base bash \
	&& pip install --no-cache -i https://pypi.douban.com/simple Cython==3.0a8 cryptography==3.4.7 \
	&& pip install --no-cache -i https://pypi.douban.com/simple gevent==21.1.2 --no-build-isolation \ 
	&& pip install --no-cache -i https://pypi.douban.com/simple -r ./requirements.txt \
	&& echo 'net.core.somaxconn = 2048' >> /etc/sysctl.conf && sysctl -p \
	&& echo "Asia/Shanghai" > /etc/timezone



# RUN /tmp/rustup-init -y 
# RUN rustup self uninstall -y
