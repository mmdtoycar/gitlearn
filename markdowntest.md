# Get Spark CLI

As I have installed Spark 2.1.0 before, so I illustrate my setup process rather than provided in homework
The tutorial I followed is [here](http://codingxiaxw.cn/2016/12/07/60-mac-spark/)

### Preparation

1.Install Java, version 1.7.0_80  
2.Install Hadoop, I follow the instruction [here](http://codingxiaxw.cn/2016/12/06/59-mac-hadoop/), version 2.7.3  
3.Install Scala  
*Notice*: The newest scala of version 2.12.1 is not compatible with Java 1.7, so I used scala of version 2.11.8 instead

### Install Spark

> Download spark-2.1.0-bin-hadoop2.7    
  http://spark.apache.org/downloads.html  
> tar xvf spark-2.2.0-bin-hadoop2.7  
> mv spark-2.0.0-bin-hadoop2.7 spark  
> rm spark-2.0.0-bin-hadoop2.7.tgz  
> Enter the configuration folder of spark `cd /usr/local/spark/conf` then `cp spark-env.sh.template spark-env.sh` and edit it  

    ```Bash
    export SCALA_HOME=/usr/local/scala
    export SPARK_MASTER_IP=localhost
    export SPARK_WORKER_MEMORY=4g
    ```

### Test

+ 'spark-shell' & 'pyspark'

	```Bash
	~/Documents/cs502-1702/mingdimao(master*) » pyspark                                             mingdimao@LeoMacBookPro
	Python 2.7.13 (default, Dec 18 2016, 07:03:39) 
	[GCC 4.2.1 Compatible Apple LLVM 8.0.0 (clang-800.0.42.1)] on darwin
	Type "help", "copyright", "credits" or "license" for more information.
	Using Spark's default log4j profile: org/apache/spark/log4j-defaults.properties
	Setting default log level to "WARN".
	To adjust logging level use sc.setLogLevel(newLevel). For SparkR, use setLogLevel(newLevel).
	17/05/13 13:57:40 WARN SparkContext: Support for Java 7 is deprecated as of Spark 2.0.0
	17/05/13 13:57:41 WARN NativeCodeLoader: Unable to load native-hadoop library for your platform... using builtin-java classes where applicable
	17/05/13 13:57:47 WARN ObjectStore: Version information not found in metastore. hive.metastore.schema.verification is not enabled so recording the schema version 1.2.0
	17/05/13 13:57:47 WARN ObjectStore: Failed to get database default, returning NoSuchObjectException
	17/05/13 13:57:48 WARN ObjectStore: Failed to get database global_temp, returning NoSuchObjectException
	Welcome to
	      ____              __
	     / __/__  ___ _____/ /__
	    _\ \/ _ \/ _ `/ __/  '_/
	   /__ / .__/\_,_/_/ /_/\_\   version 2.1.0
	      /_/

	Using Python version 2.7.13 (default, Dec 18 2016 07:03:39)
	SparkSession available as 'spark'.
	>>> 
	```

# Operation and Transformation

> **rawdata = range(0, 100)**  
> Use python range to generate 100 numbers  
> **data = sc.parallelize(rawdata)**  
> Convert rawdata into spark RDD  
> **count = data.count()**  
> Spark will count the number of records  

```
>>> rawdata = range(0,100)
>>> rawdata
[0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98, 99]
>>> data = sc.parallelize(rawdata)
>>> data
ParallelCollectionRDD[0] at parallelize at PythonRDD.scala:475
>>> count = data.count()
>>> count                                                                       
100
```

# Spark Wordcount in 3 Lines

