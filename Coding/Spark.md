per lanciare spark start-master.sh

lancia processo che listen on TCP 8080
UI: localhost:8080
spark url: spark://agilelab-notebook.lan:7077

// per lanciare un worker
start-slave.sh spark://agilelab-notebook.lan:7077

// per lanciare una spark shell:
spark-shell
pyspark per usare python


//per chiudere i processi:
SPARK_HOME/sbin/stop-slave.sh
SPARK_HOME/sbin/stop-master.sh

//per usare in scala
in build.sbt
libraryDependencies += "org.apache.spark" %% "spark-sql" % "2.4.5"



//???
 sbt -mem 2048 run per spak
 spark.read.parquet('173.30percorso)


sbt package?
