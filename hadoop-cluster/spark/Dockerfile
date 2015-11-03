FROM cdh-r

RUN yum install -y unzip

WORKDIR /home/guest
RUN su guest

RUN wget http://d3kbcqa49mib13.cloudfront.net/spark-1.5.1.tgz
RUN tar vxzf spark-1.5.1.tgz
RUN wget http://www.eu.apache.org/dist/maven/maven-3/3.3.3/binaries/apache-maven-3.3.3-bin.zip
RUN unzip apache-maven-3.3.3-bin.zip

ENV HOME /home/guest
ENV M2_HOME $HOME/apache-maven-3.3.3
ENV PATH $HOME/apache-maven-3.3.3/bin:$PATH
ENV MAVEN_OPTS "-Xmx2g -XX:MaxPermSize=512M -XX:ReservedCodeCacheSize=512m"
ENV SPARK_HOME $HOME/spark-1.5.1
ENV PATH .:$HOME/spark-1.5.1/bin:/home/login/spark-1.4.1/sbin:$PATH
ENV HADOOP_CONF_DIR /etc/hadoop/conf

WORKDIR $HOME/spark-1.5.1

RUN mvn -Pyarn -Phadoop-2.6 -Dhadoop.version=2.6.0 -Dyarn.version=2.6.0 -DskipTests -Psparkr  -Phive -Phive-thriftserver clean package

WORKDIR $HOME

EXPOSE 4040
EXPOSE 18080
EXPOSE 5000

