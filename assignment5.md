# Get Spark CLI

As I have installed Spark 2.1.0 before, so I illustrate my setup process rather than provided in homework
The tutorial I followed is [here](http://codingxiaxw.cn/2016/12/07/60-mac-spark/)

### Preparation

1. Install Java, version 1.7.0_80
2. Install Hadoop, I follow the instruction [here](http://codingxiaxw.cn/2016/12/06/59-mac-hadoop/), version 2.7.3
3. Install Scala  
	   *Notice*: The newest scala of version 2.12.1 is not compatible with Java 1.7, so I used scala of version 2.11.8 instead

### Install Spark
+ Download spark-2.1.0-bin-hadoop2.7  
  http://spark.apache.org/downloads.html
+ tar xvf spark-2.2.0-bin-hadoop2.7
+ mv spark-2.0.0-bin-hadoop2.7 spark 
+ rm spark-2.0.0-bin-hadoop2.7.tgz
+ Enter the configuration folder of spark `cd /usr/local/spark/conf` then `cp spark-env.sh.template spark-env.sh` and edit it  

    ```Bash
    export SCALA_HOME=/usr/local/scala
    export SPARK_MASTER_IP=localhost
    export SPARK_WORKER_MEMORY=4g
    ```
