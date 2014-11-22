FROM progrium/busybox
MAINTAINER  Gregory Man <man.gregory@gmail.com>

ENV VERSION 0.4.6
ADD http://github.com/coreos/etcd/releases/download/v${VERSION}/etcd-v${VERSION}-linux-amd64.tar.gz etcd-v${VERSION}-linux-amd64.tar.gz

RUN gzip -d etcd-v${VERSION}-linux-amd64.tar.gz &&\
    tar -x -f etcd-v${VERSION}-linux-amd64.tar && \
    cp etcd-v${VERSION}-linux-amd64/etcd /usr/bin/ &&\
    cp etcd-v${VERSION}-linux-amd64/etcdctl /usr/bin/ &&\
    rm -rf etcd-v${VERSION}-linux-amd64

EXPOSE  4001
EXPOSE  7001
VOLUME  ["/data"]

#Version 4.06 can't work without name if data-dir given :(
CMD ["etcd", "-data-dir=/data", "-name=etcd"]
