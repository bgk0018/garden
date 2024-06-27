---
{"dg-publish":true,"permalink":"/projects/dallas-confluent-practice/notes/zookeeper-setup-202406021533/","tags":["📖","♣️/kafka"],"created":"2024-06-03T14:22:23.592+01:00","updated":"2024-06-13T23:49:26.357+01:00"}
---

kafka # Zookeeper Setup

# Cloud Provider and Target Architecture

![Apache Kafka Series - Learn Apache Kafka for Beginners v3 - 202302211109-20240506211203832.webp](/img/user/assets/Apache%20Kafka%20Series%20-%20Learn%20Apache%20Kafka%20for%20Beginners%20v3%20-%20202302211109-20240506211203832.webp)

Zookeeper and Kafka must know their hostname and/or IP

# What is Zookeeper?

- Zookeeper provides multiple features for distributed applications
	- Distributed configuration management
	- Self election / consensus building
	- Coordination and locks
	- Key value store
- Zookeeper is used in many distributed systems Hadoop eg
- It's very stable

Zookeeper can have basically a directory like system for organizing nodes  
	- It's internal data structure is a tree  
	- Each node is called a zNode  
	- Each zNode has a path  
	- zNodes can be persistent or ephemeral  
		- Ephemeral goes away if your app disconnects  
		- Persistent does not  
	- zNodes can store data  
	- Each zNode can be WATCHed for changes

# Zookeeper Role in Kafka Cluster

- Broker registration with heartbeats mechanism to keep the list current
- Maintaining a list of topics alongside
	- Their configurations (partitions, replication factor, additional configurations)
	- The list of ISRs for partitions
- Performing leader elections in case some brokers go down
- Storing the Kafka cluster id
- Storing ACLs if security is enabled
	- Topics consumer groups users
- Quotas configuration if enabled

# Zookeeper Quorum Sizing

- Zookeeper needs to have a strict majority of servers up to form a strict majority when votes happen
- Therefore zookeeper quorums have 2N+1 servers
- Typically 1 for dev, 3 for production, 5 is very large production (Netflix)

# Zookeeper Configuration

- `dataDir=/data/zookeeper` Directory where data is stored
- `clientPort=2181` the port at which the clients connect
- `maxClientCnxns=0` Per IP limit on the number of connections
- `tickTime=2000` Milliseconds used to do heartbeats and the minimum session timeout will be twice the tickTime
- `initLimit=10` the number of ticks that the initial synchronization phase can take
- `syncLimit=5` The number of ticks that can pass between sending a request and getting an acknowledgement
- `server.1=zookeeper-1:2888:3888` zoo server hostnames

# Hands On Zookeeper AWS Setup

- Security Group, allow ports on:
	- 22 (SSH)
	- 2181
	- 2888
	- 3888
	- 2181

For Zookeeper

# Single Zookeeper Machine Setup

You want to:
- Disable RAM Swap
	- `echo 'vm.swappiness=1 | sudo tee --append /etc/sysctl.conf`
- Add hosts mapping from hostname to public ips to /etc/hosts
	- `echo "172.31.9.1 kafka1 (etc) | sudo tee --append /etc/hosts`


# Zookeeper Quorum Setup

- It's important that all instances of zookeeper have the exact same configurations

# Zookeeper Four Letter Words

- `conf` configuration
- `cons` connections to the server
- `dump` list the outstanding sessions (only works on leader)
- `envi` details about the environment (java version)
- `ruok` is a health check
- `srvr` full details of the server
- `stat` lisat brief details for the server and connected clients
- `wchs` lists brief information on watches for the server
- `wchc` Lists detailed information on watches for the server by session

# Factors impacting Zookeeper Performance

- Latency, low as possible
- Fask disk is good
- No RAM Swap
- Separate disk for snapshots and logs
- High performance network (put your zookeeper servers close to each other, at least same region)
- Isolate zookeeper instances from other processes (3 zookeeper quorum + 3 kafka brokers = 6 servers)

# References


# Flashcards