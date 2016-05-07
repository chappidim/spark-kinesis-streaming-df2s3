# spark-kinesis-streaming-df2s3

This example is moved version of apache-spark [streaming](https://github.com/apache/spark/tree/master/external/kinesis-asl/src/main/scala/org/apache/spark) examples.

#Setup

* GIT/Download the package.
* Build using maven.
  mvn package -Dmaven.test.skip=true
  
#Usage

Run spark-submit job,

  spark-submit --packages com.amazonaws:amazon-kinesis-client:1.6.1,org.apache.spark:spark-streaming-kinesis-asl_2.11:1.6.1 --class com.mchappidi.spark.examples.streaming.KinesisWordCountASL target/spark-streaming-kinesis-df2s3-1.6.1.jar STREAMNAME APPNAME https://kinesis.ENDPOINT.amazonaws.com s3://BUCKET/PREFIX/
  
Similarly for cluster-mode
 spark-submit --deploy-mode cluster .....
 
#Sample Output
* s3 output 4 files (s3://BUCKET/PREFIX/2016-05-06/22/54/)

    2016-05-06 22:54:05          0 _SUCCESS
    2016-05-06 22:54:05    7120056 part-r-00000-a2edefa4-885f-4588-b57e-bcd374f9cb2a
    2016-05-06 22:54:04    6866527 part-r-00001-a2edefa4-885f-4588-b57e-bcd374f9cb2a
    2016-05-06 22:54:04    7106386 part-r-00002-a2edefa4-885f-4588-b57e-bcd374f9cb2a
    2016-05-06 22:54:05    6934406 part-r-00003-a2edefa4-885f-4588-b57e-bcd374f9cb2a
* JSON output

    {"word":"police","total":5}
    {"word":"Giles","total":1}
    {"word":"UK\",\"url\":null,\"description\":\"Arsenal,","total":1}

