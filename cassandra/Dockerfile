FROM cassandra-base

USER root

# Place single-node startup-config script
COPY scripts/cassandra-singlenode.sh /usr/local/bin/cassandra-singlenode

# Start Cassandra
CMD ["cassandra-singlenode"]