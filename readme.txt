mvn eclipse:eclipse -DskipTests 
mvn package -DskipTests -Pdist,native -Dtar

ganglia
������
vncserver -geometry 1280x800 -alwaysshared

hadoop-src-v1����Դ�����ɹ�
hadoop-src-v2����luna������������룬���ҽ�luna-scheduler.xml�ļ����뵽conf�ļ��У����ұ���ɹ���
hadoop-src-v3����luna-scheduler.xml�޸���ȷ�����Դ�룬�ٴα���ɹ��� ע��yarn.scheduler.luna
hadoop-src-v4��������������luna�������ˡ�

storm on yarn �������з�ʽ��storm jar storm-on-yarn/storm-yarn-master/lib/storm-starter-0.0.1-SNAPSHOT.jar storm.starter.WordCountTopology -c nimbus.host=192.168.0.35

spark ���з�ʽ��./bin/spark-shell --master yarn --deploy-mode client
		val file=sc.textFile("hdfs://192.168.0.31:9000/data/partsupp.tbl")
		val count=file.flatMap(line => line.split(" ")).map(word => (word,1)).reduceByKey(_+_)
		count.collect()
	

./bin/spark-submit --class org.apache.spark.examples.SparkPi --master yarn --deploy-mode cluster ~/spark-1.4.0-bin-hadoop2.6/lib/spark-examples-1.4.0-hadoop2.6.0.jar


