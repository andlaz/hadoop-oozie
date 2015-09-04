## Oozie for Hadoop 2.x

This is an image that applies some changes to the uber profile of oozie/webapp and builds an Oozie distro with the hadoop-2 profile
and Hadoop 2.7.0 libraries.

## Usage

#### Install Oozie sharelib to HDFS

    docker run -ti --rm \ 
    andlaz/hadoop-oozie su oozie -c 'oozie-setup.sh sharelib create -fs hdfs://namenode:8020'

#### Start Ooozie

    docker run -d --name oozie -p 0.0.0.0:11000 -p 0.0.0.0:11001:11001 \
    andlaz/hadoop-oozie su oozie -c 'oozied.sh run'