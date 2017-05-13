> **rawdata = range(0, 100)** 

> Use python range to generate 100 numbers

> **data = sc.parallelize(rawdata)**

> Convert rawdata into spark RDD

> **count = data.count()**

> Spark will count the number of records
