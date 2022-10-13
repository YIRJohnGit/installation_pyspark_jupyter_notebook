https://youtu.be/N8-3kCscjrU
Step by Step Spark Installation with Ubuntu + Python + Jupyter Notebook - From Scratch
====================================
# Spark Installation with Python + Jupyter Notebook #

## Prerequitist and Installation (Optional, Since Run Hadoop) ##
Move on to Step 3, If you are not using on top of Hadoop
current Logged User Name: **_hadoop_**
host: **_localhost_**
```
sudo hostnamectl set-hostname localhost
exec bash
```
_Result_
![image](https://user-images.githubusercontent.com/111234771/195283872-ad5b1a98-5f9d-4356-934a-b6ec31935701.png)

### Step-1 - Initial Setup and System Updates ###
```
sudo apt update
```
```
java -version
readlink -f $(which java) # Verify Java Location

sudo apt remove openjdk-11*
sudo apt remove icedtea*
```

### Step-2 - Java Installation ###
```
sudo apt install -y openjdk-8-jdk openjdk-8-jre
```

### Step-3 - Download hive from the below link ###
```
cd ~/Downloads
wget --continue https://dlcdn.apache.org/spark/spark-3.2.2/spark-3.2.2-bin-hadoop3.2.tgz
tar -zxvr spark-3.2.2-bin-hadoop3.2.tgz
mv spark-3.2.2-bin-hadoop3.2.tgz ~/spark
```

### Step-4 - Install PIP and Jupyter ###
```
whereis python3
python3 --version

python3
```

```
sudo apt install -y python3-pip
pip3 install jupyter
```
====================================

sudo nano ~./bashrc



$ export PATH=$PATH:/.local/bin
$ jupyter notebook

=======
$ sudo apt-get update
$ sudo apt-get install default-jre
$ java -version

$ sudo apt-get install -y scala
$ scala -version
$ pip3 install py4j



$ export SPARK_HOME=/home/hadoop/spark
$ export PATH=$PATH:$SPARK_HOME
$ export PYTHONPATH=$SPARK_HOME/python:$PYTHONPATH
$ export PYSPARK_DRIVER_PYTHON="jupyter"
$ export PYSPARK_DRIVER_PYTHON_OPTS="notebook"
$ export PYSPARK_PYTHON=python3


$ jupyter notebook


#Create a New 
	import pyspark
	from pyspark import SparkSession
	spark = SparkSession.builder.appName('TestingSpark').getOrCreate()
	print(spark)




cd /usr/local/spark
ls -al
cd bin
ls -al

$ spark_shell
# collect the url to check
scala> quit

$ pyspark
>>>

