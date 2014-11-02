#tor-control
Tor daemon with control protocol enabled

##Build
```
docker build -t tor-control .
```

##Generate new password:
```
docker run --rm tor-control tor --hash-password you_password
```

##Run
Interactive:
```
docker run  -it -p 9051:9051 --env TOR_CONTROL_PASSWD=you_hashed_password tor-control
```
Background:
```
docker run -d -p 9051:9051 --env TOR_CONTROL_PASSWD=you_hashed_password tor-control
```


##Volumes
On host:
```
docker run -d -p 9051:9051 -v /tmp/tor-hidden-services:/opt/tor/hidden_services:rw tor-control
```

In another contaner:
```
docker run -d -v /opt/tor/hidden_services --name tor-data busybox:latest echo Data-only container for TOR

docker run -d  -p 9051:9051 --volumes-from tor-data  --env TOR_CONTROL_PASSWD=you_hashed_password tor-control
```
