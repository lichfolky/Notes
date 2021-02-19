# Docker basics

run bash in a docker running image

```
docker exec -it {containerid} bin/bash
```

copy a file in a running image:
```
docker cp  {containerid}:SRC__PATH DEST_PATH
docker cp  SRC__PATH {containerid}:DEST_PATH
```

clean unused images:
```
docker image prune -a
```

clean stopped containers:
```
docker container prune
```


## WSL2


wsl --set-default-version 2

wsl --set-default-version 1


install ubuntu
https://ubuntu.com/wsl


lista distribuzioni installate
```
wslconfig /L

wsl --list --verbose
```


terminate a wsl distro:
wsl -t Ubuntu


Set ubuntu as default
```
wslconfig /setdefault Ubuntu-20.04
```
run ubuntu:
```
wsl
```


Install a new powershell
https://github.com/PowerShell/PowerShell

launch with pwsh
