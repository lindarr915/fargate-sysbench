FROM ubuntu:latest

RUN apt-get update -y && \
    apt-get install -y sysbench && \
    apt-get clean

CMD ["/usr/bin/sysbench"]
