

   :tv:	          Youtube Analysis      :film_projector:
   

********For problem statement 1.*******

We analyze the data to identify the top 5 categories in which the most number of videos are uploaded. The dataset is gathered using the YouTube API and stored in Hadoop Distributed File System(HDFS). MapReduce algorithm is applied to process the dataset and identify the video categories.



1. Open terminal :desktop_computer:

2. hadoop fs -mkdir /youtube

3. hadoop fs -put /home/mangal/Desktop/youtubedata.txt /youtube

4. Open bashrc file by gedit ~/.bashrc and type
	  ///// don't add this path if it is already exist
	export HADOOP_CLASSPATH=$JAVA_HOME/lib/tools.jar

5. Then source ~/.bashrc

6. cd Desktop :dvd:

7. Now compile youtube1.java file suppose that file is on Desktop

	hadoop com.sun.tools.javac.Main youtube1.java

8. To combine all class files 
	
	jar cf wc.jar youtube1*.class

9. To execute
	
	hadoop jar wc.jar youtube1 /youtube/youtubedata.txt /top5rating

10. hadoop fs -ls /			//// to check output folder is there or not

11. hadoop fs -cat /top5rating/part-r-00000

************For problem statement 2****************

1. Open terminal

2. hadoop fs -mkdir /youtube

3. hadoop fs -put /home/mangal/Desktop/youtubedata.txt /youtube

4. Open bashrc file by gedit ~/.bashrc and type
	  ///// don't add this path if it is already exist
	export HADOOP_CLASSPATH=$JAVA_HOME/lib/tools.jar

5. Then source ~/.bashrc

6. cd Desktop

7. Now compile youtube2.java file suppose that file is on Desktop

	hadoop com.sun.tools.javac.Main youtube2.java

8. To combine all class files 
	
	jar cf wc.jar youtube2*.class

9. To execute :minidisc:
	
	hadoop jar wc.jar youtube2 /youtube/youtubedata.txt /videorating

10. hadoop fs -ls /			//// to check output folder is there or not

11. hadoop fs -cat /videorating/part-r-00000


Hadoop
Hadoop is a distributed computing Framework developed and maintained by The Apache Software Foundation written in Java. Hadoop consists of HDFS and MapReduce and is genrally deployed in a group of machines called cluster. Initially, GFS and MapReduce were built to empower Google Search. HDFS stands for Hadoop Distributed File System and is used to store data across multiple disks.MapReduce is a way to parallelize Data processing tasks.

MapReduce Algorithm
MapReduce Algorithm consists of Map() procedure that performs filtering and sorting of input data and Reduce() performs summary\aggregate function per (key, value) pair.

This project implements Hadoop MapReduce algorithm on the YouTube data and display the result on a web server.

