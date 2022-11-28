# Distributed Processing with Apache Spark & Nvidia Rapids
## Deep Learning - CPGEI - November 29, 2022
### Prof. M.Sc. Clayton Kossoski

<hr style="border:1px solid gray">
<hr style="border:1px">

## Basic step by step installation on ubuntu 20.04
<hr style="border:1px">

### Nvidia Cuda 11.2
```
https://developer.nvidia.com/cuda-11.2.0-download-archive?target_os=Linux
https://developer.nvidia.com/rdp/cudnn-archive#a-collapse831-102
```
### Java 8
```
sudo apt install openjdk-8-jdk
export JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64/
export PATH=/usr/lib/x86_64-linux-gnu:$PATH
export LD_LIBRARY_PATH=/usr/lib/x86_64-linux-gnu:$LD_LIBRARY_PATH
export _JAVA_OPTIONS=-Xmx4096m
```
### Docker
```
https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-20-04
```
### Nvidia Container Toolkit
```
https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/install-guide.html#docker
```
### Apache Spark
```
wget https://dlcdn.apache.org/spark/spark-3.2.2/spark-3.2.2-bin-hadoop3.2.tgz
export SPARK_HOME=/path-to/spark-3.2.2-bin-hadoop3.2
export PATH=$PATH:$SPARK_HOME/bin:$SPARK_HOME/sbin
export PYSPARK_PYTHON=/usr/bin/python3
```
### Nvidia RAPIDS
```
docker pull nvcr.io/nvidia/rapidsai/rapidsai-core:22.10-cuda11.2-runtime-ubuntu20.04-py3.8
docker run --gpus all --rm -it --shm-size=1g --ulimit memlock=-1 -p 8888:8888 -p 8787:8787 -p 8786:8786 nvcr.io/nvidia/rapidsai/rapidsai-core:22.10-cuda11.2-runtime-ubuntu20.04-py3.8
```