FROM python:3.6.15-alpine

#RUN apk add --no-cache gcc g++ make python3-dev libffi-dev mariadb-dev jpeg-dev xz-dev bzip2-dev libevent-dev bash
RUN apk add --no-cache libffi-dev mariadb-dev jpeg-dev xz-dev bzip2-dev build-base bash
COPY top /usr/local/lib/python3.6/site-packages/top
COPY requirements.txt ./requirements.txt
# COPY rustup-init /tmp/rustup-init
# RUN /tmp/rustup-init -y 
ENV CRYPTOGRAPHY_DONT_BUILD_RUST=1
RUN pip install --no-cache -i https://pypi.douban.com/simple Cython==3.0a8 cryptography==3.4.7
RUN pip install --no-cache -i https://pypi.douban.com/simple gevent==21.1.2 --no-build-isolation
RUN pip install --no-cache -i https://pypi.douban.com/simple -r ./requirements.txt
# RUN rustup self uninstall -y
