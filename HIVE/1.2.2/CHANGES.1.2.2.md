
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
# Apache Hive Changelog

## Release 1.2.2 - Unreleased (as of 2015-09-03)

### INCOMPATIBLE CHANGES:

| JIRA | Summary | Priority | Component | Reporter | Contributor |
|:---- |:---- | :--- |:---- |:---- |:---- |


### NEW FEATURES:

| JIRA | Summary | Priority | Component | Reporter | Contributor |
|:---- |:---- | :--- |:---- |:---- |:---- |


### IMPROVEMENTS:

| JIRA | Summary | Priority | Component | Reporter | Contributor |
|:---- |:---- | :--- |:---- |:---- |:---- |
| [HIVE-11076](https://issues.apache.org/jira/browse/HIVE-11076) | Explicitly set hive.cbo.enable=true for some tests |  Major | . | Pengcheng Xiong | Pengcheng Xiong |
| [HIVE-9583](https://issues.apache.org/jira/browse/HIVE-9583) | Rolling upgrade of Hive MetaStore Server |  Major | HCatalog, Metastore | Thiruvel Thirumoolan | Thiruvel Thirumoolan |


### BUG FIXES:

| JIRA | Summary | Priority | Component | Reporter | Contributor |
|:---- |:---- | :--- |:---- |:---- |:---- |
| [HIVE-11344](https://issues.apache.org/jira/browse/HIVE-11344) | HIVE-9845 makes HCatSplit.write modify the split so that PartInfo objects are unusable after it |  Major | . | Sushanth Sowmyan | Sushanth Sowmyan |
| [HIVE-11224](https://issues.apache.org/jira/browse/HIVE-11224) | AggregateStatsCache triggers java.util.ConcurrentModificationException under some conditions |  Major | . | Pengcheng Xiong | Pengcheng Xiong |
| [HIVE-11172](https://issues.apache.org/jira/browse/HIVE-11172) | Vectorization wrong results for aggregate query with where clause without group by |  Critical | Hive | Yi Zhang | Hari Sankar Sivarama Subramaniyan |
| [HIVE-11171](https://issues.apache.org/jira/browse/HIVE-11171) | Join reordering algorithm might introduce projects between joins |  Major | CBO | Jesus Camacho Rodriguez | Jesus Camacho Rodriguez |
| [HIVE-11151](https://issues.apache.org/jira/browse/HIVE-11151) | Calcite transitive predicate inference rule should not transitively add not null filter on non-nullable input |  Major | CBO, Logical Optimizer | Ashutosh Chauhan | Ashutosh Chauhan |
| [HIVE-11074](https://issues.apache.org/jira/browse/HIVE-11074) | Update tests for HIVE-9302 after removing binaries |  Major | Tests | Jesus Camacho Rodriguez | Jesus Camacho Rodriguez |
| [HIVE-11066](https://issues.apache.org/jira/browse/HIVE-11066) | Ensure tests don't share directories on FS |  Major | Tests | Eugene Koifman | Eugene Koifman |
| [HIVE-11060](https://issues.apache.org/jira/browse/HIVE-11060) | Make test windowing.q robust |  Major | Tests | Jesus Camacho Rodriguez | Jesus Camacho Rodriguez |
| [HIVE-11059](https://issues.apache.org/jira/browse/HIVE-11059) | hcatalog-server-extensions tests scope should depend on hive-exec |  Minor | Tests | Sushanth Sowmyan | Sushanth Sowmyan |
| [HIVE-11050](https://issues.apache.org/jira/browse/HIVE-11050) | testCliDriver\_vector\_outer\_join.\* failures in Unit tests due to unstable data creation queries |  Blocker | Hive | Matt McCline | Matt McCline |
| [HIVE-11028](https://issues.apache.org/jira/browse/HIVE-11028) | Tez: table self join and join with another table fails with IndexOutOfBoundsException |  Major | Query Planning | Jason Dere | Jason Dere |
| [HIVE-10996](https://issues.apache.org/jira/browse/HIVE-10996) | Aggregation / Projection over Multi-Join Inner Query producing incorrect results |  Critical | Query Planning | Gautam Kowshik | Jesus Camacho Rodriguez |


### TESTS:

| JIRA | Summary | Priority | Component | Reporter | Contributor |
|:---- |:---- | :--- |:---- |:---- |:---- |
| [HIVE-11083](https://issues.apache.org/jira/browse/HIVE-11083) | Make test cbo\_windowing robust |  Major | Tests | Ashutosh Chauhan | Ashutosh Chauhan |
| [HIVE-11048](https://issues.apache.org/jira/browse/HIVE-11048) | Make test cbo\_windowing robust |  Major | Tests | Ashutosh Chauhan | Ashutosh Chauhan |


### SUB-TASKS:

| JIRA | Summary | Priority | Component | Reporter | Contributor |
|:---- |:---- | :--- |:---- |:---- |:---- |


### OTHER:

| JIRA | Summary | Priority | Component | Reporter | Contributor |
|:---- |:---- | :--- |:---- |:---- |:---- |

