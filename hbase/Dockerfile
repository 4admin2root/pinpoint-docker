FROM java:8
MAINTAINER JASON LUI
EXPOSE 16010 2181
WORKDIR /opt/
RUN mkdir data
RUN wget http://archive.apache.org/dist/hbase/hbase-1.0.3/hbase-1.0.3-bin.tar.gz && tar -xvf hbase-1.0.3-bin.tar.gz && rm  hbase-1.0.3-bin.tar.gz
COPY hbase-site.xml ./hbase-1.0.3/conf/
COPY init-hbase.txt ./hbase-1.0.3/conf/
COPY  hbase-front.sh ./hbase-1.0.3/bin/
COPY  start-front.sh ./hbase-1.0.3/bin/
RUN ./hbase-1.0.3/bin/start-hbase.sh && sleep 10 && ./hbase-1.0.3/bin/hbase shell ./hbase-1.0.3/conf/init-hbase.txt
CMD bash -x ./hbase-1.0.3/bin/start-front.sh
