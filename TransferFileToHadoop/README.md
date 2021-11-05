TO check Flumes version:The command is : flume-ng version

the flumes version is :Flume 1.9.0 Hadoop version is :3.3.1

TO MOVE FILE FROM LOCAL SYSTEM TO HADOOP :
Go to the input1.txt file location and copy the path

1)Start the hadoop services : from home 

$start-all.sh
$jps 

2)Go to the flume directory inside conf directory create a flume file using touch command as :
~/Downloads/apache-flume-1.9.0-bin$ cd conf/
~/Downloads/apache-flume-1.9.0-bin/conf$ touch flume.conf
~/Downloads/apache-flume-1.9.0-bin/conf$ nano flume.conf

3)Give the following inside the flume.conf file as below :
  give the hadoop local host and also the input1.txt file location(paste the copied location)

agent1.sources.tail.command = cat /home/lenovo/Downloads/input1.txt
agent1.sinks.sink-1.hdfs.path = hdfs://localhost:9000/flume01

4)Now go to the apache flume directory give the command as below :

~/Downloads/apache-flume-1.9.0-bin$ bin/flume-ng agent –conf ./conf/ -f conf/flume.conf -n agent1 -Dflume.root.logger=DEBUG

5)check the hadoop file system(localhost:9870)
    you can see the contents of input1.txt file in the /flume01 directory with flumedata file

Thus file transferred from local to hadoop  
