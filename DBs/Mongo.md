### MongoNotes
```
docker pull mongo
docker run -d -p 27017-27019:27017-27019 --name mongodb mongo
```

//if in detached (-d) you can interact with it:
docker exec -it mongodb bash


you can use robo 3d as GUI


## Configuration
add this to application.conf:
```
# The mongo module
module.mongo=${play.path}/modules/mongo

# mongodb connection details
mongo.host=localhost
mongo.port=27017
mongo.database=peerreview

mongo.username=test
mongo.password=test123
```

## Data Store
Create a data directory on a suitable volume on your host system, e.g. /org/lichfolky/peerreview.

Start your mongo container like this:

$ docker run --name some-mongo -v /org/lichfolky/peerreview:/data/db -d mongo
The -v /org/lichfolky/peerreview:/data/db part of the command mounts the /my/own/datadir directory from the underlying 
host system as /data/db inside the container, where MongoDB by default will write its data files.

This image also defines a volume for /data/configdb for use with --configsvr (see docs.mongodb.com for more details).