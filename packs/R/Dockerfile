FROM r-base:latest
COPY * .
ENV PORT 8080
EXPOSE 8080
RUN curl -L "https://github.com/jenkins-x/jx/releases/download/$(curl --silent "https://github.com/jenkins-x/jx/releases/latest" | sed 's#.*tag/\(.*\)\".*#\1#')/jx-linux-amd64.tar.gz" | tar xzv "jx" &&\
    mv jx /usr/local/bin &&\
    rm -fr jx &&\
    jx version
USER docker
COPY ./* /home/docker
WORKDIR /home/docker
