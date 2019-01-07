# Terraria Server V1.3.5.3
![Terraria Logo](https://d1u5p3l4wpay3k.cloudfront.net/terraria_gamepedia/c/c4/Terraria.png "Terraria Logo")

## Vanilla Dedicated Linux Server
This docker container is based on the latest centos linux und uses the official dedicated server package from [Terraria.org](http://terraria.org/).

## Volumes
* the path to store the terraria worlds
```
-v "/hostpath/world":"/world":rw
``` 
* using your own server configuration file
```
-v "/hostpath/server.config":"/opt/terraria/Dedicated Server/Linux/server.config":rw
``` 
* get the server log file (this is console ouput)
```
-v "/hostpath/log/terraria/":"/var/log/terraria":rw
``` 

## Start the server
```
docker run -dit --name="terraria-server" -p 7777:7777 -v "/srv/terraria/worlds/":"/world":rw -v "/var/log/terraria/":"/var/log/terraria":rw mangirdas/terraria-server
```

## Build
```
docker build -t mangirdas/terraria-server .
```

## Attach to server console
```
docker attach terraria-server
```

## Detach from server console
```
crtl+p crtl+q
```
