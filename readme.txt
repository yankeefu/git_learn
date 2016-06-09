mvn eclipse:eclipse -DskipTests 
mvn package -DskipTests -Pdist,native -Dtar

ganglia
萨丽亚
vncserver -geometry 1280x800 -alwaysshared

hadoop-src-v1：将源码编译成功
hadoop-src-v2：将luna调度器代码加入，并且将luna-scheduler.xml文件加入到conf文件中，并且编译成功。
hadoop-src-v3：将luna-scheduler.xml修改正确后加入源码，再次编译成功。 注：yarn.scheduler.luna
hadoop-src-v4：可以正常运行luna调度器了。

storm on yarn 程序运行方式：storm jar storm-on-yarn/storm-yarn-master/lib/storm-starter-0.0.1-SNAPSHOT.jar storm.starter.WordCountTopology -c nimbus.host=192.168.0.35

spark 运行方式：./bin/spark-shell --master yarn --deploy-mode client
		val file=sc.textFile("hdfs://192.168.0.31:9000/data/partsupp.tbl")
		val count=file.flatMap(line => line.split(" ")).map(word => (word,1)).reduceByKey(_+_)
		count.collect()
	

./bin/spark-submit --class org.apache.spark.examples.SparkPi --master yarn --deploy-mode cluster ~/spark-1.4.0-bin-hadoop2.6/lib/spark-examples-1.4.0-hadoop2.6.0.jar


