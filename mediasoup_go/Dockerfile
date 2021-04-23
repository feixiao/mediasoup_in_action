FROM registry.cn-hangzhou.aliyuncs.com/frank_dev/mediasoup-worker:3.7.2


WORKDIR /app

# support go 
ENV GOLANG_VERSION 1.16.3
ENV GOLANG_DOWNLOAD_URL https://dl.google.com/go/go${GOLANG_VERSION}.linux-amd64.tar.gz
RUN curl -fsSL "$GOLANG_DOWNLOAD_URL" -o golang.tar.gz \
    && tar -C /usr/local -xzf golang.tar.gz \
    && rm -f golang.tar.gz

ENV GOPROXY=https://goproxy.cn
ENV GOSUMDB="sum.golang.google.cn"
ENV GOPATH=/home/frank/gopath
ENV PATH $GOPATH/bin:/usr/local/go/bin:$PATH
RUN mkdir -p "$GOPATH/src" "$GOPATH/bin" && chmod -R 777 "$GOPATH" &&\
    echo "export GOROOT=/usr/local/go" >> /etc/profile && \
    echo "export GOPATH=/home/frank/gopath" >> /etc/profile  \
    echo "export PATH=/usr/local/go/bin:${PATH}" >> /etc/profile  


RUN git clone https://github.com/jiyeyuran/mediasoup-go-demo.git 
RUN cd mediasoup-go-demo/server && go build 


ENV MEDIASOUP_WORKER_BIN    /ms/mediasoup-3.7.2/worker/out/Release/mediasoup-worker
CMD [ "./server" ]