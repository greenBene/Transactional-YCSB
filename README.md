<!--
Copyright (c) 2010 Yahoo! Inc., 2012 - 2016 YCSB contributors.
All rights reserved.

Licensed under the Apache License, Version 2.0 (the "License"); you
may not use this file except in compliance with the License. You
may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or
implied. See the License for the specific language governing
permissions and limitations under the License. See accompanying
LICENSE file.
-->

# Transactional YCSB

This project is a fork of the [YCSB](https://github.com/brianfrankcooper/YCSB). 
It adapts the benchmark to run all operations in all workloads within transactions 
and introduces a new workload that allows the benchmarking of transactions with 
any number of read, update, insert, and scan operations.

The project understand itself as a continuation of the [YCSB+T](https://github.com/brianfrankcooper/YCSB/pull/169) 
from 2014. While YCSB+T focuses on the benchmarking of transactional overhead and the detection of consistency anomalies,
this fork enables the benchmarking of transactions with increasing length.  

To read more about the YCSB+T see this paper: 
> A. Dey, A. Fekete, R. Nambiar and U. Röhm, "YCSB+T: Benchmarking web-scale transactional databases," 2014 IEEE 30th International Conference on Data Engineering Workshops, Chicago, IL, USA, 2014, pp. 223-230, doi: 10.1109/ICDEW.2014.6818330. keywords: {Benchmark testing;Distributed databases;Throughput;Google;Scalability;Protocols},


## Supported Bindings
While this fork includes the code of all bindings available in the YCSB at the time of forking, not all bindings 
are updated to support transactions yet. At the moment, the following bindings are updated to support 
transactional workloads:

* [x] foundationdb-binding
* [x] mongodb-binding
* [x] orientdb-binding


## Building from source

YCSB requires the use of Maven 3.

To build the full distribution, with all database bindings:

    mvn clean package

To build a single database binding:

    mvn -pl site.ycsb:mongodb-binding -am clean package
