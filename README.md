
TO check Flumes version:The command is : flume-ng version

the flumes version is :Flume 1.9.0
Hadoop version is :3.3.1
python version is(python3 --version) :3.8.10

To write python code for getting live stock data using the link provided(python3)

Generate API(Application programming interface) key from following link: https://www.alphavantage.co/

Get the required url and python code for the stock data from following link: https://www.alphavantage.co/documentation/#

Create a .env file in VS Code and declare your API key in that. Create a stock_data_api_hdfs.py  file and write the python code.

Create a configuration file flume2hadoop.conf  in directory  apache-flume-1.9.0-bin/conf using :nano flume2hadoop.conf

Inside conf file give the path location of python file using python3 as and give the hadoop directory as:

agent1.sources.tail.command = python3 /home/lenovo/Desktop/Python_work/hadoop/FLUMES/stock_data_api_hdfs.py

agent1.sinks.sink-1.hdfs.path = hdfs://localhost:9000/flume_stock_data1

Run the following command to send the python source to hdfs from apache flume directory:

~/Downloads/apache-flume-1.9.0-bin$ bin/flume-ng agent –conf ./conf/ -f conf/flume2hadoop.conf -n agent1 -Dflume.root.logger=DEBUG

Open localhost:9870 to see the data
