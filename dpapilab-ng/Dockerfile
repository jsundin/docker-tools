FROM python:alpine3.15
WORKDIR /app
COPY . /app
RUN apk add --no-cache build-base && \
    ln -s /usr/local/bin/python3 /usr/bin/python3 && \
    /usr/local/bin/python -m pip install --upgrade pip && \
    /usr/local/bin/python -m pip install --no-cache-dir -r requirements.txt && \
    chmod +x *.py

ENV PATH /usr/local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/app

ENTRYPOINT [ "sh" ]
