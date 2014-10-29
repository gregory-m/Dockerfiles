#geminabox
Gem in a Box server listening on port 9292 using thin

##Build
```
docker build -t geminabox .
```

##Run
```
docker run -d -p 9292:9292 geminabox
```

##Volumes
On host:
```
docker run -d -p 9292:9292 -v /tmp/geminabox-data:/opt/geminabox/data:rw geminabox-webrick
```

In another contaner:
```
docker run -d -v /opt/geminabox/data --name geminabox-data busybox:latest echo Data-only container for geminabox #one time

docker run -d  -p 9292:9292 --volumes-from geminabox-data geminabox
```
