#### Overview

These Dockerfiles aim at creating a CDH (Cloudera Hadoop Distribution) with Impala/Hive/Hue, RStudio, and Spark. Dockerfiles are split in three parts:

* cdh54: To build a CDH container (version 5.4). From Lucamilanesio https://github.com/lucamilanesio/docker-cdh5.4
* cdh-rstudio: Adds R Studio (0.99.484)
* spark: Adds Spark 1.5.1

#### Create containers

In three steps:

```
cd cdh54
docker build -t docker-cdh54 .
cd ../cdh-rstudio
docker build -t cdh-r .
cd ../spark
docker build -t cdh-r-spark .
```

Each container takes about 10 minutes, 10 minutes, 1 hour to be built, respectively.

#### Run cdh-r-spark

```
docker run -it cdh-r-spark bash
````




