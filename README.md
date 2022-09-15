# Big Data Analysis Using Apache Spark

* Introduction
  ------------

In this experiment, we have performed a word count program using spark by following MapReduce paradigm in big data. Apache Spark™ provides a multi-language engine for executing programs on single-node machines or clusters.

* Requirements
  ------------
  
  1. Amazon Web Services 
  2. Apache Spark
  3. Java 

* Installations
  ------------

For implementing the word count program in a single node cluster, we had to make a setup by installation of java and spark in the AWS EC2 instance.

a. EC2 Instance: First, an EC2 instance is created and connected to PuTTY’s SSH client using private key pairs and IP address.
  
  - Instance ID: your id (sparkour-app)
  - IP Address: your ip
  - Security Group: your group (sparktest) 

b. Java/ JDK: To install spark, java runtime of version 8 or above has to be installed.

Figure 1: Java version
![alt text](https://github.com/WaniaKhance/Big-Data-Analysis-Using-Apache-Spark/blob/main/Picture1.png?raw=true)


c. Apache Spark: Then Apache spark has been installed in the EC2 instance. The version can be seen in the following figure. 

Figure 2: Spark version
![alt text](https://github.com/WaniaKhance/Big-Data-Analysis-Using-Apache-Spark/blob/main/Picture2.png?raw=true)


d. Path Environment: The path variable of the JDK and spark installation directories are added in the bashrc file using following command.

   - ubuntu@ip-172-31-8-42:/vi /.bashrc

Figure 3: Path to directories
![alt text](https://github.com/WaniaKhance/Big-Data-Analysis-Using-Apache-Spark/blob/main/Picture3.png?raw=true)


2. Word Count Example

We have implemented word count example using two methods; 1. Text file and 2. Manual Array.

   - Using Text File: First, a text file named as ’wania.txt’ with a sample lines of text is created and saved in the spark installation directory. Following commands are used for the program.
    
     – sc.textFile(): It is used to read the file from the file system.
     – flatMap(): It performs transformation operation which flattens the elements of RDD and returns a new RDD. The words in the text are separated on the basis of spaces and stored in an array.
     – Map(): It is also performing transformation on every element of RDD and converting each word into key-value pair.
     – reduceByKey(): It group by keys and performs aggregation on each key based on the word count of unique words.
     – Final Result: When all the keys are aggregated, we can see all the words with their counts in the result. Saving file in CSV format is optional.

Figure 4: Word Count Program using Text File
![alt text](https://github.com/WaniaKhance/Big-Data-Analysis-Using-Apache-Spark/blob/main/Picture4.png?raw=true)


   - Manual Array: In this method, a user manually adds a text on which all the same steps are performed as explained above. Following lines of code are implemented as shown in figure 5.
   
     – sc.parallelize(): It creates an RDD from a list collection which will applied to further MapReduce paradigm.
    
Figure 5: Word Count Program Through Manual Array
![alt text](https://github.com/WaniaKhance/Big-Data-Analysis-Using-Apache-Spark/blob/main/Picture5.png?raw=true)



