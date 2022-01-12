FROM debian:buster


RUN apt-get update && apt-get install -y ca-certificates

ADD sources.list /etc/apt/sources.list
RUN apt-get update && \
    DEBIAN_FRONTEND=noninteractive apt-get install -y locales && \
    sed -i -e 's/# en_US.UTF-8 UTF-8/en_US.UTF-8 UTF-8/' /etc/locale.gen && \
    dpkg-reconfigure --frontend=noninteractive locales && \
    update-locale LANG=en_US.UTF-8

RUN apt-get install -y wget git && \
    HTTPS_PROXY=http://127.0.0.1:1087 wget -O golang.tgz https://dl.google.com/go/go1.16.4.linux-amd64.tar.gz && \
    tar xzvf golang.tgz && \
    mv go /usr/local && \
    rm golang.tgz && \
    HTTPS_PROXY=http://127.0.0.1:1087 wget -O hugo.deb https://github.com/gohugoio/hugo/releases/download/v0.91.2/hugo_extended_0.91.2_Linux-64bit.deb && \
    dpkg -i hugo.deb && \
    rm hugo.deb

ENV TZ="America/Los_Angeles"
ENV GOROOT="/usr/local/go"
ENV PATH="/usr/local/go/bin:${PATH}"

WORKDIR /app

CMD ["hugo", "server", "-b", "http://0.0.0.0", "--minify", "--gc"]
