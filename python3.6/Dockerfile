FROM python:3.6.15-alpine as base

RUN mkdir /svc
ADD . /svc
WORKDIR /svc
ENV CRYPTOGRAPHY_DONT_BUILD_RUST=1
# RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.aliyun.com/g' /etc/apk/repositories \
#	&& apk add libffi-dev mariadb-dev jpeg-dev xz-dev bzip2-dev build-base  

# RUN pip wheel -i https://pypi.douban.com/simple Cython==3.0a8 cryptography==3.4.7 --wheel-dir=/svc/wheels \
#	&& pip wheel -i https://pypi.douban.com/simple gevent==21.1.2 --no-build-isolation --wheel-dir=/svc/wheels \
#	&& pip wheel -i https://pypi.douban.com/simple pandas==1.1.5 --wheel-dir=/svc/wheels \
#	&& pip wheel -i https://pypi.douban.com/simple -r requirements.txt --wheel-dir=/svc/wheels
#   && cp -r /usr/lib /svc/lib


FROM python:3.6.15-alpine

COPY --from=base /svc /svc
WORKDIR /svc

RUN pip install --no-index --find-links=/svc/wheels -r requirements.txt \
	&& cp -r /svc/top /usr/local/lib/python3.6/site-packages/top \
	&& cp /svc/Shanghai /etc/localtime \
	&& cp /svc/lib/* /usr/lib/ && ln -s /usr/lib/libjpeg.so.8.2.2 /usr/lib/libjpeg.so.8 \
	&& ln -s /usr/lib/libstdc\+\+.so.6.0.28 /usr/lib/libstdc\+\+.so.6 \ 
	&& echo "Asia/Shanghai" > /etc/timezone \
	&& rm -rf /svc/*

