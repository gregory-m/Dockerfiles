#etcd
Etcd on buasybox

##Build
```
docker build -t etcd .
```

##Run
```
docker run -d -p 4001:4001 etcd
```

##Volumes
On host:
```
docker run -d -p 4001:4001 -v /tmp/etcd-data:/data:rw etcd
```

In another contaner:
```
docker run -d -v /data --name etcd-data busybox:latest echo Data-only container for etcd #one time

docker run -d  -p 4001: 4001 --volumes-from etcd-data etcd
```
