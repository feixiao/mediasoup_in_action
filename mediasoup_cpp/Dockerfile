FROM feixiao/cpp_base:1.2

WORKDIR /ms


ADD ./mediasoup-3.7.2.tar.gz .

RUN apt update -y && apt install -y python3
RUN cd mediasoup-3.7.2/worker && make -j 4