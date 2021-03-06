
<!---
# Licensed to the Apache Software Foundation (ASF) under one
# or more contributor license agreements.  See the NOTICE file
# distributed with this work for additional information
# regarding copyright ownership.  The ASF licenses this file
# to you under the Apache License, Version 2.0 (the
# "License"); you may not use this file except in compliance
# with the License.  You may obtain a copy of the License at
#
#     http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
-->
# Apache Flink Changelog

## Release 1.5.4 - Unreleased (as of 2018-09-12)



### IMPROVEMENTS:

| JIRA | Summary | Priority | Component | Reporter | Contributor |
|:---- |:---- | :--- |:---- |:---- |:---- |
| [FLINK-10082](https://issues.apache.org/jira/browse/FLINK-10082) | Initialize StringBuilder in Slf4jReporter with estimated size |  Major | Metrics | Chesnay Schepler | Chesnay Schepler |
| [FLINK-10137](https://issues.apache.org/jira/browse/FLINK-10137) | YARN: Log completed Containers |  Major | Distributed Coordination, ResourceManager, YARN | Gary Yao | Gary Yao |
| [FLINK-10131](https://issues.apache.org/jira/browse/FLINK-10131) | Improve logging around ResultSubpartition |  Major | Logging, Network | Nico Kruber | Nico Kruber |
| [FLINK-10185](https://issues.apache.org/jira/browse/FLINK-10185) | Make ZooKeeperStateHandleStore#releaseAndTryRemove synchronous |  Major | Distributed Coordination | Till Rohrmann | Till Rohrmann |


### BUG FIXES:

| JIRA | Summary | Priority | Component | Reporter | Contributor |
|:---- |:---- | :--- |:---- |:---- |:---- |
| [FLINK-10101](https://issues.apache.org/jira/browse/FLINK-10101) | Mesos web ui url is missing. |  Major | Mesos | Renjie Liu | Renjie Liu |
| [FLINK-10116](https://issues.apache.org/jira/browse/FLINK-10116) | createComparator fails on case class with Unit type fields prior to the join-key |  Major | DataSet API | Will | Fabian Hueske |
| [FLINK-10172](https://issues.apache.org/jira/browse/FLINK-10172) | Inconsistentcy in ExpressionParser and ExpressionDsl for order by asc/desc |  Major | Table API & SQL | Rong Rong | Rong Rong |
| [FLINK-10204](https://issues.apache.org/jira/browse/FLINK-10204) | StreamElementSerializer#copy broken for LatencyMarkers |  Major | Metrics, Streaming | Ben La Monica | Ben La Monica |
| [FLINK-10142](https://issues.apache.org/jira/browse/FLINK-10142) | Reduce synchronization overhead for credit notifications |  Major | Network | Nico Kruber | Nico Kruber |
| [FLINK-10141](https://issues.apache.org/jira/browse/FLINK-10141) | Reduce lock contention introduced with 1.5 |  Major | Network | Nico Kruber | Nico Kruber |
| [FLINK-10115](https://issues.apache.org/jira/browse/FLINK-10115) | Content-length limit is also applied to FileUploads |  Major | REST, Webfrontend | Yazdan Shirvany | Chesnay Schepler |
| [FLINK-10150](https://issues.apache.org/jira/browse/FLINK-10150) | Chained batch operators interfere with each other other |  Blocker | Metrics, Webfrontend | Helmut Zechmann | Chesnay Schepler |
| [FLINK-10261](https://issues.apache.org/jira/browse/FLINK-10261) | INSERT INTO does not work with ORDER BY clause |  Major | Table API & SQL | Timo Walther | xueyu |
| [FLINK-10193](https://issues.apache.org/jira/browse/FLINK-10193) | Default RPC timeout is used when triggering savepoint via JobMasterGateway |  Critical | Distributed Coordination | Gary Yao | Gary Yao |
| [FLINK-10293](https://issues.apache.org/jira/browse/FLINK-10293) | RemoteStreamEnvironment does not forward port to RestClusterClient |  Major | Client, Streaming | Chesnay Schepler | Chesnay Schepler |
| [FLINK-10267](https://issues.apache.org/jira/browse/FLINK-10267) | [State] Fix arbitrary iterator access on RocksDBMapIterator |  Major | State Backends, Checkpointing | Yun Tang | Yun Tang |
| [FLINK-10011](https://issues.apache.org/jira/browse/FLINK-10011) | Old job resurrected during HA failover |  Blocker | JobManager | Elias Levy | Till Rohrmann |


