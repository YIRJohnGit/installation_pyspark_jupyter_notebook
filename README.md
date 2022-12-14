# Spark Installation with Python + Jupyter Notebook #

## Prerequitist and Installation (Optional) ##
___Move on to Step 3, If you are not using on top of Hadoop___
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
_Optional if Needed can be use with latest version, but read the documentation for Latest Updates_
```
sudo apt-get install -y default-jre
```

### Step-3 - Download hive from the below link ###
```
cd ~/Downloads
wget --continue https://dlcdn.apache.org/spark/spark-3.2.2/spark-3.2.2-bin-hadoop3.2.tgz
tar -xzvf spark-3.2.2-bin-hadoop3.2.tgz
mv spark-3.2.2-bin-hadoop3.2 ~/spark
```

### Step-4 - Install PIP and Jupyter ###
```
whereis python3
python3 --version
python3
```
_To Exit from the python shell type quit() >>>_
```
quit()
```
**_Install pip3 and Jupyter for Python_**
```
sudo apt install -y python3-pip
```
```
pip3 install jupyter
```

### Step-5 - Install of Scala and Python for Java ###
```
sudo apt-get install -y scala
scala -version
pip3 install py4j
```

### Step-6 - Add Environment Variables ###
```
sudo nano ~/.bashrc
```

**_Add the below Change to the ~/.bashrc File and Save_**
```
# Adding the SpySpark Settings
export SPARK_HOME=/home/hadoop/spark
export PATH=$PATH:$SPARK_HOME
export PYTHONPATH=$SPARK_HOME/python:$PYTHONPATH
export PYSPARK_DRIVER_PYTHON="jupyter"
export PYSPARK_DRIVER_PYTHON_OPTS="notebook"
export PYSPARK_PYTHON=python3
```
_Result_


**_Initiate the default changes_**
```
source ~/.bashrc
```
**_Verify Spark Shell_ tpye :quit to exit**
```
cd $SPARK_HOME/bin
./spark-shell
:quit
```
_Result_
![image](https://user-images.githubusercontent.com/111234771/195506716-24442271-c58f-4de1-a427-61e7b916ca21.png)

**_Verify Spark Shell_ sample Code in Scala> prompt**

```
	val num=Array(1,2,3,56,78)
	val data = sc.parallelize(num)
	data.foreach(println)
```
_Result_
![image](https://user-images.githubusercontent.com/111234771/195506221-5246cfbb-79e3-49f0-b3c6-61beeee51503.png)

```
jupyter notebook
```
_Result_
![image](https://user-images.githubusercontent.com/111234771/195502410-c2a0ca7d-005d-46ab-94a8-1e1fc1a966e7.png) 

___Run The Sample File from Git URL___
```
git pull https://github.com/YIRJohnGit/sample_pyspark.git
```


## Installation of Additional Libraries ##
```
pip3 install sklearn
pip3 install Keras
pip3 install tensorflow
```
_Result_
![image](https://user-images.githubusercontent.com/111234771/195503927-901eaa70-dd0b-44f5-a224-59e7a4ef3962.png)

___Start PySpark Jupyter Notebook___
```
~/spark/bin/pyspark
```
