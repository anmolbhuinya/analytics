# analytics

Documentation, Tutorial: https://spark.apache.org/documentation.html




Deployment

1) Download sbt and unzip and untar it :http://www.scala-sbt.org/download.html
2) I have downloaded Spark Prebuild package for Hadoop 2, unzipped and untarred it: http://www.apache.org/dyn/closer.cgi/spark/spark-1.0.2/spark-1.0.2-bin-hadoop2.tgz
3) I've created standalone application SimpleApp.scala as described in: http://spark.apache.org/docs/latest/quick-start.html#standalone-applications with proper simple.sbt file (just copied from the description) and proper directory layout
4) Make sure you have sbt in you PATH. Go to directory with your application and build your package using sbt package
5) Start Spark Server using SPARK_HOME_DIR/sbin/spark_master.sh
6) Go to localhost:8080 and make sure your server is running. Copy link from URL (from server description, not localhost. It shoul be something with port 7077 or similiar)
7) Start Workers using SPARK_HOME_DIR/bin/spark-class org.apache.spark.deploy.worker.Worker spark://IP:PORT where IP:PORT is the URL copied in 6
8) Deploy you application to the server: SPARK_HOME_DIR/bin/spark-submit --class "SimpleApp" --master URL target/scala-2.10/simple-project_2.10-1.0.jar
