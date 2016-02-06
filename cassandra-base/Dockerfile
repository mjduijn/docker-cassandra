FROM anapsix/alpine-java:latest

ENV CASSANDRA_HOME /opt/apache-cassandra
ENV CASSANDRA_CONFIG $CASSANDRA_HOME/conf
ENV CASSANDRA_VERSION 3.2.1

# Install Cassandra
RUN wget http://apache.cs.uu.nl/cassandra/$CASSANDRA_VERSION/apache-cassandra-$CASSANDRA_VERSION-bin.tar.gz -O /tmp/cassandra-$CASSANDRA_VERSION.tar.gz \
	&& tar -xzf /tmp/cassandra-$CASSANDRA_VERSION.tar.gz -C /opt \
	&& ln -s /opt/apache-cassandra-$CASSANDRA_VERSION $CASSANDRA_HOME \
	&& rm -rf /tmp/*

ENV PATH "$CASSANDRA_HOME/bin:$PATH"

#Install JNA
ENV JNA_VERSION 4.1.0
RUN mkdir -p $JAVA_HOME/lib \
	&& wget -P /opt/jdk/lib/ https://github.com/twall/jna/raw/$JNA_VERSION/dist/linux-x86-64.jar

COPY scripts /scripts
RUN /scripts/config-cassandra-base.sh

EXPOSE 7199 7000 7001 9160 9042 22 8012 61621

#CMD [""]