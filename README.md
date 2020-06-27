# Setting up Infinispan Distributed Cache on AWS
What is Infinispan?
Infinispan is an open source distributed in-memory key/value store developed by Red Hat and is available under Apache License, v2.0.
Checkout the below links for more information about Infinispan.
https://infinispan.org/
https://en.wikipedia.org/wiki/Infinispan
https://www.aosabook.org/en/posa/infinispan.html
Problem
AWS EC2 instances do not completely support UDP Multicast (one-to-many communication over an IP network) this makes it impossible to use Infinispan using its native tcp or udp protocol.

Solution
This tutorial will help you setup Infinispan Distributed Cache on AWS by using the EC2-S3 PING protocol. We will use an S3 bucket as a gossip server that will route the communication among all the members in the cluster.
You can find more information about the S3 ping protocol here:
http://www.jgroups.org/javadoc/org/jgroups/protocols/S3_PING.html
https://github.com/jgroups-extras/native-s3-ping
