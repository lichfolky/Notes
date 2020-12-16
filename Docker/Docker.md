docker


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
