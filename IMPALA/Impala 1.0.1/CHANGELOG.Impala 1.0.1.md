
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
# Apache Impala Changelog

## Release Impala 1.0.1 - 2013-06-04



### NEW FEATURES:

| JIRA | Summary | Priority | Component | Reporter | Contributor |
|:---- |:---- | :--- |:---- |:---- |:---- |
| [IMPALA-31](https://issues.apache.org/jira/browse/IMPALA-31) | Support "explain \<query\>" |  Major | . | Alan Choi | Alan Choi |


### IMPROVEMENTS:

| JIRA | Summary | Priority | Component | Reporter | Contributor |
|:---- |:---- | :--- |:---- |:---- |:---- |
| [IMPALA-265](https://issues.apache.org/jira/browse/IMPALA-265) | [api] Support GetLog() |  Major | . | Romain Rigaux | Alan Choi |
| [IMPALA-307](https://issues.apache.org/jira/browse/IMPALA-307) | &raw param for debug web UI /varz and others similar to what query profiles have |  Minor | . | Hari Sekhon | Alan Choi |
| [IMPALA-348](https://issues.apache.org/jira/browse/IMPALA-348) | Insert queries don't have averaged fragment nodes |  Major | . | Kyle Vigen | Henry Robinson |
| [IMPALA-353](https://issues.apache.org/jira/browse/IMPALA-353) | Add a timer that tracks the amount of time a query is waiting for further input from the client |  Major | . | Henry Robinson | Henry Robinson |
| [IMPALA-361](https://issues.apache.org/jira/browse/IMPALA-361) | Move encoded query profile logging to a separate file |  Major | . | Henry Robinson | Henry Robinson |


### BUG FIXES:

| JIRA | Summary | Priority | Component | Reporter | Contributor |
|:---- |:---- | :--- |:---- |:---- |:---- |
| [IMPALA-293](https://issues.apache.org/jira/browse/IMPALA-293) | Impala is unable to query RCFile tables which describe fewer columns than the file's header. |  Major | . | Ricky Saltzer | Skye Wanderman-Milne |
| [IMPALA-16](https://issues.apache.org/jira/browse/IMPALA-16) | Impala returns 0 for bad time values in UNIX\_TIMESTAMP, Hive returns NULL |  Minor | . | Henry Robinson | Skye Wanderman-Milne |
| [IMPALA-298](https://issues.apache.org/jira/browse/IMPALA-298) | lzo scanner tries to read past end of file |  Major | . | Skye Wanderman-Milne | Skye Wanderman-Milne |
| [IMPALA-326](https://issues.apache.org/jira/browse/IMPALA-326) | Parquet supported encodings validation is too strict |  Major | . | Nong Li | Nong Li |
| [IMPALA-162](https://issues.apache.org/jira/browse/IMPALA-162) | Inconsistent result from order by limit query |  Major | . | Alan Choi | Nong Li |
| [IMPALA-318](https://issues.apache.org/jira/browse/IMPALA-318) | Profile for 'show tables' missing summary information |  Major | . | Kyle Vigen | Skye Wanderman-Milne |
| [IMPALA-333](https://issues.apache.org/jira/browse/IMPALA-333) | Impala parquet scanner can not read all data files generated by other frameworks |  Blocker | . | Nong Li | Nong Li |
| [IMPALA-344](https://issues.apache.org/jira/browse/IMPALA-344) | StatsMetrics may write unparseable JSON when a value is NaN or inf |  Major | . | Henry Robinson | Henry Robinson |
| [IMPALA-319](https://issues.apache.org/jira/browse/IMPALA-319) | RuntimeProfile.thrift doesn't have event sequence information |  Major | . | Kyle Vigen | Henry Robinson |
| [IMPALA-349](https://issues.apache.org/jira/browse/IMPALA-349) | Query state for successful create table is EXCEPTION |  Major | . | Kyle Vigen | Lenni Kuff |
| [IMPALA-351](https://issues.apache.org/jira/browse/IMPALA-351) | Impala does not correctly substitute \_HOST with hostname in --principal |  Major | . | Henry Robinson | Henry Robinson |
| [IMPALA-357](https://issues.apache.org/jira/browse/IMPALA-357) | insert into Parquet exceed mem-limit |  Major | . | Alan Choi | Nong Li |
| [IMPALA-358](https://issues.apache.org/jira/browse/IMPALA-358) | Double check release of JNI-allocated byte-strings |  Major | . | Henry Robinson | Alan Choi |
| [IMPALA-300](https://issues.apache.org/jira/browse/IMPALA-300) | Hbase region changes are not handled correctly |  Major | . | Skye Wanderman-Milne | Alan Choi |
| [IMPALA-362](https://issues.apache.org/jira/browse/IMPALA-362) | impalad hangs when read sequence file without contents |  Major | . | Zesheng Wu | Skye Wanderman-Milne |
| [IMPALA-378](https://issues.apache.org/jira/browse/IMPALA-378) | 'use' queries have incomplete profiles |  Major | . | Kyle Vigen | Henry Robinson |
| [IMPALA-365](https://issues.apache.org/jira/browse/IMPALA-365) | malformed query ends up with a partially populated profile |  Minor | . | Chris Leroy | Henry Robinson |


### OTHER:

| JIRA | Summary | Priority | Component | Reporter | Contributor |
|:---- |:---- | :--- |:---- |:---- |:---- |
| [IMPALA-63](https://issues.apache.org/jira/browse/IMPALA-63) | Add new Impala metric that exposes the total number of tables and databases Impala "knows about" |  Major | . | Lenni Kuff | Henry Robinson |
| [IMPALA-210](https://issues.apache.org/jira/browse/IMPALA-210) | Impala /backends should to links to the debug page for those BEs |  Minor | . | Nong Li | Henry Robinson |

