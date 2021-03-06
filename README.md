Role Name
=========

Install Zookeeper on Ubuntu Precice with Cloudera zookeepr-server package

[![Build Status](https://travis-ci.org/anorsich/ansible-zookeeper.svg)](https://travis-ci.org/anorsich/ansible-zookeeper)

Requirements
------------

Role Variables
--------------

Defaults: 

```
zookeeper_conf_dir: "/etc/zookeeper/conf"
zookeeper_data_dir: "/var/lib/zookeeper"

# Allow larger than default maximum client connections.
zookeeper_maxClientCnxns: 200

# The number of milliseconds of each tick
zookeeper_tickTime: 2000

# The number of ticks that the initial
# synchronization phase can take
zookeeper_initLimit: 100

# The number of ticks that can pass between
# sending a request and getting an acknowledgement
zookeeper_syncLimit: 5

# the port at which the clients will connect
zookeeper_clientPort: 2181

# the id which is used to initialize zookeeper server
zookeeper_id: 0

zookeeper_servers:
  - { zookeeper_id: "0", ip: "127.0.0.1", ports: "2888:3888" }
```

Dependencies
------------

Depends on smola.java


Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:
	
	- hosts: all
	  pre_tasks:
	    - name: Update APT cache
	      apt: update_cache=yes
	  roles:
	    - { role: anorsich.zookeeper }

To play with role check out example running in vagrant at /tests/vagrant folder	    

License
-------

BSD