
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
# Hadoop Changelog

## Release 2.1.1-beta - 2013-09-16

### INCOMPATIBLE CHANGES:

| JIRA | Summary | Priority | Component | Reporter | Contributor |
|:---- |:---- | :--- |:---- |:---- |:---- |


### NEW FEATURES:

| JIRA | Summary | Priority | Component | Reporter | Contributor |
|:---- |:---- | :--- |:---- |:---- |:---- |


### IMPROVEMENTS:

| JIRA | Summary | Priority | Component | Reporter | Contributor |
|:---- |:---- | :--- |:---- |:---- |:---- |
| [MAPREDUCE-5478](https://issues.apache.org/jira/browse/MAPREDUCE-5478) | TeraInputFormat unnecessarily defines its own FileSplit subclass |  Minor | examples | Sandy Ryza | Sandy Ryza |
| [MAPREDUCE-5379](https://issues.apache.org/jira/browse/MAPREDUCE-5379) | Include token tracking ids in jobconf |  Major | job submission, security | Sandy Ryza | Karthik Kambatla |
| [MAPREDUCE-5367](https://issues.apache.org/jira/browse/MAPREDUCE-5367) | Local jobs all use same local working directory |  Major | . | Sandy Ryza | Sandy Ryza |
| [MAPREDUCE-1981](https://issues.apache.org/jira/browse/MAPREDUCE-1981) | Improve getSplits performance by using listLocatedStatus |  Major | job submission | Hairong Kuang | Hairong Kuang |


### BUG FIXES:

| JIRA | Summary | Priority | Component | Reporter | Contributor |
|:---- |:---- | :--- |:---- |:---- |:---- |
| [MAPREDUCE-5497](https://issues.apache.org/jira/browse/MAPREDUCE-5497) | '5s sleep'  in MRAppMaster.shutDownJob is only needed before stopping ClientService |  Major | . | Jian He | Jian He |
| [MAPREDUCE-5493](https://issues.apache.org/jira/browse/MAPREDUCE-5493) | In-memory map outputs can be leaked after shuffle completes |  Blocker | mrv2 | Jason Lowe | Jason Lowe |
| [MAPREDUCE-5483](https://issues.apache.org/jira/browse/MAPREDUCE-5483) | revert MAPREDUCE-5357 |  Major | distcp | Alejandro Abdelnur | Robert Kanter |
| [MAPREDUCE-5475](https://issues.apache.org/jira/browse/MAPREDUCE-5475) | MRClientService does not verify ACLs properly |  Blocker | mr-am, mrv2 | Jason Lowe | Jason Lowe |
| [MAPREDUCE-5470](https://issues.apache.org/jira/browse/MAPREDUCE-5470) | LocalJobRunner does not work on Windows. |  Major | . | Chris Nauroth | Sandy Ryza |
| [MAPREDUCE-5468](https://issues.apache.org/jira/browse/MAPREDUCE-5468) | AM recovery does not work for map only jobs |  Blocker | . | Yesha Vora | Vinod Kumar Vavilapalli |
| [MAPREDUCE-5454](https://issues.apache.org/jira/browse/MAPREDUCE-5454) | TestDFSIO fails intermittently on JDK7 |  Major | test | Karthik Kambatla | Karthik Kambatla |
| [MAPREDUCE-5446](https://issues.apache.org/jira/browse/MAPREDUCE-5446) | TestJobHistoryEvents and TestJobHistoryParsing have race conditions |  Major | mrv2, test | Jason Lowe | Jason Lowe |
| [MAPREDUCE-5440](https://issues.apache.org/jira/browse/MAPREDUCE-5440) | TestCopyCommitter Fails on JDK7 |  Major | mrv2 | Robert Parker | Robert Parker |
| [MAPREDUCE-5428](https://issues.apache.org/jira/browse/MAPREDUCE-5428) | HistoryFileManager doesn't stop threads when service is stopped |  Major | jobhistoryserver, mrv2 | Jason Lowe | Karthik Kambatla |
| [MAPREDUCE-5425](https://issues.apache.org/jira/browse/MAPREDUCE-5425) | Junit in TestJobHistoryServer failing in jdk 7 |  Major | jobhistoryserver | Ashwin Shankar | Robert Parker |
| [MAPREDUCE-5414](https://issues.apache.org/jira/browse/MAPREDUCE-5414) | TestTaskAttempt fails jdk7 with NullPointerException |  Major | test | Nemon Lou | Nemon Lou |
| [MAPREDUCE-5385](https://issues.apache.org/jira/browse/MAPREDUCE-5385) | JobContext cache files api are broken |  Blocker | . | Omkar Vinit Joshi | Omkar Vinit Joshi |
| [MAPREDUCE-5358](https://issues.apache.org/jira/browse/MAPREDUCE-5358) | MRAppMaster throws invalid transitions for JobImpl |  Major | mr-am | Devaraj K | Devaraj K |
| [MAPREDUCE-5317](https://issues.apache.org/jira/browse/MAPREDUCE-5317) | Stale files left behind for failed jobs |  Major | mrv2 | Ravi Prakash | Ravi Prakash |
| [MAPREDUCE-5251](https://issues.apache.org/jira/browse/MAPREDUCE-5251) | Reducer should not implicate map attempt if it has insufficient space to fetch map output |  Major | mrv2 | Jason Lowe | Ashwin Shankar |
| [MAPREDUCE-5164](https://issues.apache.org/jira/browse/MAPREDUCE-5164) | command  "mapred job" and "mapred queue" omit HADOOP\_CLIENT\_OPTS |  Major | . | Nemon Lou | Nemon Lou |
| [MAPREDUCE-5020](https://issues.apache.org/jira/browse/MAPREDUCE-5020) | Compile failure with JDK8 |  Major | client | Trevor Robinson | Trevor Robinson |
| [MAPREDUCE-5001](https://issues.apache.org/jira/browse/MAPREDUCE-5001) | LocalJobRunner has race condition resulting in job failures |  Major | . | Brock Noland | Sandy Ryza |
| [MAPREDUCE-3193](https://issues.apache.org/jira/browse/MAPREDUCE-3193) | FileInputFormat doesn't read files recursively in the input path dir |  Major | mrv1, mrv2 | Ramgopal N | Devaraj K |


### TESTS:

| JIRA | Summary | Priority | Component | Reporter | Contributor |
|:---- |:---- | :--- |:---- |:---- |:---- |


### SUB-TASKS:

| JIRA | Summary | Priority | Component | Reporter | Contributor |
|:---- |:---- | :--- |:---- |:---- |:---- |
| [MAPREDUCE-5476](https://issues.apache.org/jira/browse/MAPREDUCE-5476) | Job can fail when RM restarts after staging dir is cleaned but before MR successfully unregister with RM |  Blocker | . | Jian He | Jian He |
| [MAPREDUCE-5466](https://issues.apache.org/jira/browse/MAPREDUCE-5466) | Historyserver does not refresh the result of restarted jobs after RM restart |  Blocker | . | Yesha Vora | Jian He |
| [MAPREDUCE-5462](https://issues.apache.org/jira/browse/MAPREDUCE-5462) | In map-side sort, swap entire meta entries instead of indexes for better cache performance |  Major | performance, task | Sandy Ryza | Sandy Ryza |
| [MAPREDUCE-5441](https://issues.apache.org/jira/browse/MAPREDUCE-5441) | JobClient exit whenever RM issue Reboot command to 1st attempt App Master. |  Major | applicationmaster, client | Rohith | Jian He |


### OTHER:

| JIRA | Summary | Priority | Component | Reporter | Contributor |
|:---- |:---- | :--- |:---- |:---- |:---- |

