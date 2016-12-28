# Apache Kafka Vagrant based Ansible Playbook

Simple Vagrant and Ansible playbook to provision a Apache Kafka environment with VirtualBox.

Creates a 2 node cluster for Apache Kafka

Requires [Virtual Apache ZooKeeper cluster](https://github.com/skohlmann/virtual-zookeeper-cluster).

__Note__: This is a proof of concept and test installation only. Do ot use in production.

# Cluster specs

- System: 2x Ubuntu 14.04 server
- Memory: 1024 MB each host
- IP address: 192.168.5.200-201
- Hostnames: `kafka-node-[x]` were `x` have values of 1 or 2
- [Kafka](http://kafka.apache.org/) version: 0.10.1.1
- JVM: Oracle Java-8

# Installation

1. Install [VirtualBox](https://www.virtualbox.org/)
2. Install [Vagrant](https://www.vagrantup.com/)
3. Install [Ansible](https://www.ansible.com/)
4. Clone this repository
5. Enter cloned repository
6. Execute `vagrant provision && vagrant up`

# Test setup

1. Connect to Kafka service with: `vagrant ssh kafka-node-1`
2. Change to Kafka `bin` directory: `cd //opt/kafka_2.10-0.10.1.1/bin
3. List existing topics: `./kafka-topics.sh  --list --zookeeper 192.168.5.100:2181`
4. Create new topic: `./kafka-topics.sh --create --topic firsttopic --zookeeper 192.168.5.100:2181 --partitions 1 --replication-factor 1`<br />Output: `Created topic "firsttopic".`
5. Show created topic: `./kafka-topics.sh  --list --zookeeper 192.168.5.100:2181`<br />Output: `firsttopic`
