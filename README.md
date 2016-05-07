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

