# Apache Kafka Vagrant based Ansible Playbook
Simple Vagrant and Ansible playbook to provision a Apache Kafka environment.

Creates a 2 node cluster for Kafka 0.10.1.1 running with Java 8.

Requires [Virtual Apache ZooKeeper cluster](https://github.com/skohlmann/virtual-zookeeper-cluster).

*Note*: This is a proof of concept and test installation only. Do ot use in production.

# Installation

1. Install [Vagrant](https://www.vagrantup.com/)
2. Install [Ansible](https://www.ansible.com/)
3. Clone this repository
4. Execute `vagrant provision && vagrant up`

# Test setup

1. Connect to Kafka service with: `vagrant ssh kafka-node-1`
2. Change to Kafka `bin` directory: `cd //opt/kafka_2.10-0.10.1.1/bin
3. List existing topics: `./kafka-topics.sh  --list --zookeeper 192.168.5.100:2181`
4. Create new topic: `./kafka-topics.sh --create --topic firsttopic --zookeeper 192.168.5.100:2181 --partitions 1 --replication-factor 1`<br />Output: `Created topic "firsttopic".`
5. Show created topic: `./kafka-topics.sh  --list --zookeeper 192.168.5.100:2181`<br />Output: `firsttopic`
