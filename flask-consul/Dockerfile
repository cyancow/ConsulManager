FROM python:3-alpine
ADD . /flask
WORKDIR /flask

RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.aliyun.com/g' /etc/apk/repositories \
&& apk add --no-cache gcc libc-dev libffi-dev \
&& rm -rf /var/cache/apk/* \
&& pip3 install --upgrade pip -i https://mirrors.aliyun.com/pypi/simple \
&& pip3 install -r requirements.txt -i https://mirrors.aliyun.com/pypi/simple
EXPOSE 2026
CMD ["python3","./manager.py"]
