
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
# Apache HBase Changelog

## Release 1.4.11 - 2019-10-24



### NEW FEATURES:

| JIRA | Summary | Priority | Component | Reporter | Contributor |
|:---- |:---- | :--- |:---- |:---- |:---- |
| [HBASE-15666](https://issues.apache.org/jira/browse/HBASE-15666) | shaded dependencies for hbase-testing-util |  Critical | test | Sean Busbey | Balazs Meszaros |


### IMPROVEMENTS:

| JIRA | Summary | Priority | Component | Reporter | Contributor |
|:---- |:---- | :--- |:---- |:---- |:---- |
| [HBASE-22593](https://issues.apache.org/jira/browse/HBASE-22593) | Add local Jenv file to gitignore |  Trivial | . | Jan Hentschel | Jan Hentschel |
| [HBASE-22344](https://issues.apache.org/jira/browse/HBASE-22344) | Document deprecated public APIs |  Major | API, community, documentation | Jan Hentschel | Jan Hentschel |
| [HBASE-22596](https://issues.apache.org/jira/browse/HBASE-22596) | [Chore] Separate the execution period between CompactionChecker and PeriodicMemStoreFlusher |  Minor | Compaction | Reid Chan | Reid Chan |
| [HBASE-22616](https://issues.apache.org/jira/browse/HBASE-22616) | responseTooXXX logging for Multi should characterize the component ops |  Minor | . | Andrew Kyle Purtell | Andrew Kyle Purtell |
| [HBASE-22604](https://issues.apache.org/jira/browse/HBASE-22604) | fix the link in the docs to "Understanding HBase and BigTable" by Jim R. Wilson |  Trivial | documentation | David Mollitor | Murtaza Hassan |
| [HBASE-22669](https://issues.apache.org/jira/browse/HBASE-22669) | Add unit tests for org.apache.hadoop.hbase.util.Strings |  Major | java | Eric Hettiaratchi | Eric Hettiaratchi |
| [HBASE-22689](https://issues.apache.org/jira/browse/HBASE-22689) | Line break for fix version in documentation |  Trivial | documentation | Jan Hentschel | Jan Hentschel |
| [HBASE-22610](https://issues.apache.org/jira/browse/HBASE-22610) | [BucketCache] Rename "hbase.offheapcache.minblocksize" |  Trivial | . | Reid Chan | Murtaza Hassan |
| [HBASE-22692](https://issues.apache.org/jira/browse/HBASE-22692) | Rubocop definition is not used in the /bin directory |  Minor | . | Jan Hentschel | Jan Hentschel |
| [HBASE-22702](https://issues.apache.org/jira/browse/HBASE-22702) | [Log] 'Group not found for table' is chatty |  Trivial | . | Reid Chan | Murtaza Hassan |
| [HBASE-22363](https://issues.apache.org/jira/browse/HBASE-22363) | Remove hardcoded number of read cache block buckets |  Trivial | BlockCache, BucketCache | Biju Nair | Biju Nair |
| [HBASE-22762](https://issues.apache.org/jira/browse/HBASE-22762) | Print the delta between phases in the split/merge/compact/flush transaction journals |  Minor | logging | Andrew Kyle Purtell | Andrew Kyle Purtell |
| [HBASE-22786](https://issues.apache.org/jira/browse/HBASE-22786) | Fix Checkstyle issues in tests of hbase-client |  Minor | Client | Jan Hentschel | Jan Hentschel |
| [HBASE-22785](https://issues.apache.org/jira/browse/HBASE-22785) | Reduce number of Checkstyle issues in client exceptions |  Minor | Client | Jan Hentschel | Jan Hentschel |
| [HBASE-22828](https://issues.apache.org/jira/browse/HBASE-22828) | Log a region close journal |  Minor | . | Andrew Kyle Purtell | Andrew Kyle Purtell |
| [HBASE-22844](https://issues.apache.org/jira/browse/HBASE-22844) | Fix Checkstyle issues in client snapshot exceptions |  Minor | Client | Jan Hentschel | Jan Hentschel |
| [HBASE-22810](https://issues.apache.org/jira/browse/HBASE-22810) | Initialize an separate ThreadPoolExecutor for taking/restoring snapshot |  Major | . | Zheng Hu | Zheng Hu |
| [HBASE-22464](https://issues.apache.org/jira/browse/HBASE-22464) | Improvements to hbase-vote script |  Trivial | scripts | Artem Ervits | Artem Ervits |
| [HBASE-22880](https://issues.apache.org/jira/browse/HBASE-22880) | [Backport] HBASE-22871 to branch-1 |  Major | . | Reid Chan | Baiqiang Zhao |
| [HBASE-22872](https://issues.apache.org/jira/browse/HBASE-22872) | Don't create normalization plan unnecesarily when split and merge both are disabled |  Minor | . | Aman Poonia | Aman Poonia |
| [HBASE-22724](https://issues.apache.org/jira/browse/HBASE-22724) | Add a emoji on the vote table for pre commit result on github |  Major | build, test | Duo Zhang | Duo Zhang |
| [HBASE-22912](https://issues.apache.org/jira/browse/HBASE-22912) | [Backport] HBASE-22867 to branch-1 to avoid ForkJoinPool to spawn thousands of threads |  Major | . | Reid Chan | Zheng Hu |
| [HBASE-22804](https://issues.apache.org/jira/browse/HBASE-22804) | Provide an API to get list of successful regions and total expected regions in Canary |  Minor | canary | Caroline | Caroline |
| [HBASE-22890](https://issues.apache.org/jira/browse/HBASE-22890) | Verify the files when RegionServer is starting and BucketCache is in file mode |  Major | BucketCache | Baiqiang Zhao | Baiqiang Zhao |
| [HBASE-23058](https://issues.apache.org/jira/browse/HBASE-23058) | Should be "Column Family Name" in table.jsp |  Minor | . | Qiongwu | Qiongwu |
| [HBASE-22975](https://issues.apache.org/jira/browse/HBASE-22975) | Add read and write QPS metrics at server level and table level |  Minor | metrics | Baiqiang Zhao | Baiqiang Zhao |
| [HBASE-22930](https://issues.apache.org/jira/browse/HBASE-22930) | Set unique name to longCompactions/shortCompactions threads |  Minor | . | Pankaj Kumar | Pankaj Kumar |
| [HBASE-22874](https://issues.apache.org/jira/browse/HBASE-22874) | Define a public interface for Canary and move existing implementation to LimitedPrivate |  Critical | canary | Duo Zhang | Rushabh Shah |
| [HBASE-23116](https://issues.apache.org/jira/browse/HBASE-23116) | LoadBalancer should log table name when balancing per table |  Minor | . | Andrew Kyle Purtell | Bharath Vissapragada |
| [HBASE-23114](https://issues.apache.org/jira/browse/HBASE-23114) | Use archiveArtifacts in Jenkinsfiles |  Trivial | . | Peter Somogyi | Peter Somogyi |
| [HBASE-23174](https://issues.apache.org/jira/browse/HBASE-23174) | Upgrade jackson and jackson-databind to 2.9.10 (branch-1) |  Blocker | dependencies, REST, security | Andrew Kyle Purtell | Andrew Kyle Purtell |
| [HBASE-21996](https://issues.apache.org/jira/browse/HBASE-21996) | Set locale for javadoc |  Major | documentation | Peter Somogyi | Peter Somogyi |


### BUG FIXES:

| JIRA | Summary | Priority | Component | Reporter | Contributor |
|:---- |:---- | :--- |:---- |:---- |:---- |
| [HBASE-22520](https://issues.apache.org/jira/browse/HBASE-22520) | Avoid possible NPE in HalfStoreFileReader seekBefore() |  Major | . | Viraj Jasani | Viraj Jasani |
| [HBASE-22563](https://issues.apache.org/jira/browse/HBASE-22563) | Reduce retained jobs for Jenkins pipelines |  Major | . | Josh Elser | Josh Elser |
| [HBASE-22559](https://issues.apache.org/jira/browse/HBASE-22559) | [RPC] set guard against CALL\_QUEUE\_HANDLER\_FACTOR\_CONF\_KEY |  Minor | rpc | Reid Chan | Reid Chan |
| [HBASE-22562](https://issues.apache.org/jira/browse/HBASE-22562) | PressureAwareThroughputController#skipControl never invoked |  Trivial | Operability | Josh Elser | Josh Elser |
| [HBASE-22426](https://issues.apache.org/jira/browse/HBASE-22426) | Disable region split/merge switch doen't work when 'hbase.assignment.usezk' is set true |  Major | Region Assignment | Pankaj Kumar | Pankaj Kumar |
| [HBASE-22605](https://issues.apache.org/jira/browse/HBASE-22605) | Ref guide includes dev guidance only applicable to EOM versions |  Trivial | documentation | Sean Busbey | Mingliang Liu |
| [HBASE-22538](https://issues.apache.org/jira/browse/HBASE-22538) | Prevent graceful\_stop.sh from shutting down RS too early before finishing unloading regions |  Minor | shell | Jeongdae Kim | Jeongdae Kim |
| [HBASE-22492](https://issues.apache.org/jira/browse/HBASE-22492) | HBase server doesn't preserve SASL sequence number on the network |  Major | regionserver | Sébastien BARNOUD | Sébastien BARNOUD |
| [HBASE-22629](https://issues.apache.org/jira/browse/HBASE-22629) | Remove TestReplicationDroppedTables from branch-1 |  Minor | . | Andrew Kyle Purtell | Andrew Kyle Purtell |
| [HBASE-22637](https://issues.apache.org/jira/browse/HBASE-22637) | fix flaky TestMetaTableMetrics test |  Major | metrics, test | Mate Szalay-Beko | Mate Szalay-Beko |
| [HBASE-22654](https://issues.apache.org/jira/browse/HBASE-22654) | apache-rat complains on branch-1 |  Minor | build | Peter Somogyi | Peter Somogyi |
| [HBASE-22656](https://issues.apache.org/jira/browse/HBASE-22656) | [Metrics]  Tabe metrics 'BatchPut' and 'BatchDelete' are never updated |  Minor | metrics | Reid Chan | Reid Chan |
| [HBASE-22686](https://issues.apache.org/jira/browse/HBASE-22686) | ZkSplitLogWorkerCoordination doesn't allow a regionserver to pick up all of the split work it is capable of |  Major | . | Andrew Kyle Purtell | Andrew Kyle Purtell |
| [HBASE-22571](https://issues.apache.org/jira/browse/HBASE-22571) | Javadoc Warnings related to @return tag |  Trivial | documentation | Murtaza Hassan | Murtaza Hassan |
| [HBASE-22586](https://issues.apache.org/jira/browse/HBASE-22586) | Javadoc Warnings related to @param tag |  Trivial | documentation | Murtaza Hassan | Murtaza Hassan |
| [HBASE-22720](https://issues.apache.org/jira/browse/HBASE-22720) | Incorrect link for hbase.unittests |  Trivial | documentation | Peter Somogyi | Peter Somogyi |
| [HBASE-22603](https://issues.apache.org/jira/browse/HBASE-22603) | Javadoc Warnings related to @link tag |  Trivial | documentation | Murtaza Hassan | Murtaza Hassan |
| [HBASE-22730](https://issues.apache.org/jira/browse/HBASE-22730) | XML Parsing error on branch-1 |  Minor | . | Peter Somogyi | Peter Somogyi |
| [HBASE-22715](https://issues.apache.org/jira/browse/HBASE-22715) | All scan requests should be handled by scan handler threads in RWQueueRpcExecutor |  Minor | . | Jeongdae Kim | Jeongdae Kim |
| [HBASE-22658](https://issues.apache.org/jira/browse/HBASE-22658) | region\_mover.rb  should choose same rsgroup servers as target servers |  Major | rsgroup, shell | liang.feng |  |
| [HBASE-22145](https://issues.apache.org/jira/browse/HBASE-22145) | windows hbase-env causes hbase cli/etc to ignore HBASE\_OPTS |  Major | . | Sergey Shelukhin | Sergey Shelukhin |
| [HBASE-22773](https://issues.apache.org/jira/browse/HBASE-22773) | when set blockSize option in Performance Evaluation tool, error occurs:ERROR: Unrecognized option/command: --blockSize=131072 |  Minor | mapreduce | dingwei2019 | dingwei2019 |
| [HBASE-22801](https://issues.apache.org/jira/browse/HBASE-22801) | Maven build issue on Github PRs |  Major | build | Peter Somogyi | Peter Somogyi |
| [HBASE-22838](https://issues.apache.org/jira/browse/HBASE-22838) | assembly:single failure: user id or group id 'xxxxx' is too big |  Major | build | Viraj Jasani | Viraj Jasani |
| [HBASE-22774](https://issues.apache.org/jira/browse/HBASE-22774) | [WAL] RegionGroupingStrategy loses its function after split |  Major | Performance, wal | Reid Chan | Reid Chan |
| [HBASE-22856](https://issues.apache.org/jira/browse/HBASE-22856) | HBASE-Find-Flaky-Tests fails with pip error |  Major | build, test | Duo Zhang | Duo Zhang |
| [HBASE-22861](https://issues.apache.org/jira/browse/HBASE-22861) | [WAL] Merged region should get its WAL according to WALProvider. |  Major | wal | Reid Chan | Reid Chan |
| [HBASE-22601](https://issues.apache.org/jira/browse/HBASE-22601) | Misconfigured addition of peers leads to cluster shutdown. |  Major | . | Rushabh Shah | Rushabh Shah |
| [HBASE-22866](https://issues.apache.org/jira/browse/HBASE-22866) | Multiple slf4j-log4j provider versions included in binary package (branch-1) |  Minor | . | Andrew Kyle Purtell | Viraj Jasani |
| [HBASE-22935](https://issues.apache.org/jira/browse/HBASE-22935) | TaskMonitor warns MonitoredRPCHandler task may be stuck when it recently started |  Minor | logging | David Manning | David Manning |
| [HBASE-22937](https://issues.apache.org/jira/browse/HBASE-22937) | The RawBytesComparator in branch-1 have wrong comparison order |  Major | . | Zheng Hu | Zheng Hu |
| [HBASE-22981](https://issues.apache.org/jira/browse/HBASE-22981) | Remove unused flags for Yetus |  Critical | build | Peter Somogyi | Peter Somogyi |
| [HBASE-22900](https://issues.apache.org/jira/browse/HBASE-22900) | No longer include multiple httpcore and httpclient versions in binary package |  Minor | build, dependencies | Andrew Kyle Purtell | Rabi Kumar K C |
| [HBASE-23007](https://issues.apache.org/jira/browse/HBASE-23007) | UnsatisfiedLinkError when using hbase-shaded packages under linux |  Critical | shading | Balazs Meszaros | Balazs Meszaros |
| [HBASE-23019](https://issues.apache.org/jira/browse/HBASE-23019) | Handle --skip-errorprone on branch-1 |  Major | build | Peter Somogyi | Peter Somogyi |
| [HBASE-22955](https://issues.apache.org/jira/browse/HBASE-22955) | Branches-1 precommit and nightly yetus jobs are using jdk8 for jdk7 jobs |  Major | . | Sean Busbey | Sean Busbey |
| [HBASE-22649](https://issues.apache.org/jira/browse/HBASE-22649) | Encode StoreFile path URLs in the UI to handle scenarios where CF contains special characters (like # etc.) |  Major | UI | Ashok shetty | Y. SREENIVASULU REDDY |
| [HBASE-23015](https://issues.apache.org/jira/browse/HBASE-23015) | Replace Jackson with relocated gson everywhere but hbase-rest |  Blocker | Client, shading | Sean Busbey | Viraj Jasani |
| [HBASE-22653](https://issues.apache.org/jira/browse/HBASE-22653) | Do not run errorProne on JDK7 |  Major | build | Peter Somogyi | Peter Somogyi |
| [HBASE-23086](https://issues.apache.org/jira/browse/HBASE-23086) | TestShell failing on branch-1 and branch-1.4 |  Blocker | shell | Sean Busbey | Viraj Jasani |
| [HBASE-22735](https://issues.apache.org/jira/browse/HBASE-22735) | list\_regions may throw an error if a region is RIT |  Minor | shell | Andrew Kyle Purtell | Viraj Jasani |
| [HBASE-23094](https://issues.apache.org/jira/browse/HBASE-23094) | Wrong log message in simpleRegionNormaliser while checking if merge is enabled. |  Minor | . | Sanjeet Nishad | Sanjeet Nishad |
| [HBASE-23139](https://issues.apache.org/jira/browse/HBASE-23139) | MapReduce jobs lauched from convenience distribution are nonfunctional |  Blocker | mapreduce | Andrew Kyle Purtell | Andrew Kyle Purtell |
| [HBASE-23056](https://issues.apache.org/jira/browse/HBASE-23056) | Block count is 0 when BucketCache using persistent IOEngine and retrieve from file |  Minor | BucketCache | Baiqiang Zhao | Baiqiang Zhao |
| [HBASE-22784](https://issues.apache.org/jira/browse/HBASE-22784) | OldWALs not cleared in a replication slave cluster (cyclic replication bw 2 clusters) |  Blocker | regionserver, Replication | Solvannan R M | Wellington Chevreuil |
| [HBASE-23128](https://issues.apache.org/jira/browse/HBASE-23128) | Restore Region interface compatibility |  Blocker | . | Andrew Kyle Purtell | Andrew Kyle Purtell |
| [HBASE-19663](https://issues.apache.org/jira/browse/HBASE-19663) | javadoc creation needs jsr305 |  Major | documentation, website | Michael Stack | Sean Busbey |
| [HBASE-23153](https://issues.apache.org/jira/browse/HBASE-23153) | PrimaryRegionCountSkewCostFunction SLB function should implement CostFunction#isNeeded |  Major | . | Andrew Kyle Purtell | Andrew Kyle Purtell |


### TESTS:

| JIRA | Summary | Priority | Component | Reporter | Contributor |
|:---- |:---- | :--- |:---- |:---- |:---- |
| [HBASE-22615](https://issues.apache.org/jira/browse/HBASE-22615) | Make TestChoreService more robust to timing |  Minor | test | Sean Busbey | Sean Busbey |
| [HBASE-22725](https://issues.apache.org/jira/browse/HBASE-22725) | Remove all remaining javadoc warnings |  Trivial | test | Murtaza Hassan | Murtaza Hassan |


### SUB-TASKS:

| JIRA | Summary | Priority | Component | Reporter | Contributor |
|:---- |:---- | :--- |:---- |:---- |:---- |
| [HBASE-22554](https://issues.apache.org/jira/browse/HBASE-22554) | Upgrade to surefire 2.22.2 |  Major | test | Peter Somogyi | Peter Somogyi |
| [HBASE-22627](https://issues.apache.org/jira/browse/HBASE-22627) | Port HBASE-22617 (Recovered WAL directories not getting cleaned up) to branch-1 |  Blocker | . | Andrew Kyle Purtell | Andrew Kyle Purtell |
| [HBASE-22719](https://issues.apache.org/jira/browse/HBASE-22719) | Add debug support for github PR pre commit job |  Major | build | Duo Zhang | Duo Zhang |
| [HBASE-22132](https://issues.apache.org/jira/browse/HBASE-22132) | Backport HBASE-22115 "HBase RPC aspires to grow an infinite tree of trace scopes; some other places are also unsafe" intent to branch-1 |  Major | . | Andrew Kyle Purtell | Viraj Jasani |
| [HBASE-22728](https://issues.apache.org/jira/browse/HBASE-22728) | Upgrade jackson dependencies in branch-1 |  Major | . | Andrew Kyle Purtell | Viraj Jasani |
| [HBASE-22891](https://issues.apache.org/jira/browse/HBASE-22891) | Use HBaseQA in HBase-PreCommit-GitHub-PR job |  Major | build, scripts | Duo Zhang | Duo Zhang |
| [HBASE-22706](https://issues.apache.org/jira/browse/HBASE-22706) | Backport HBASE-21292 "IdLock.getLockEntry() may hang if interrupted" to branch-1 |  Major | . | Pankaj Kumar | Pankaj Kumar |
| [HBASE-22988](https://issues.apache.org/jira/browse/HBASE-22988) | Backport HBASE-11062 "hbtop" to branch-1 |  Major | backport, hbtop | Toshihiro Suzuki | Toshihiro Suzuki |
| [HBASE-23110](https://issues.apache.org/jira/browse/HBASE-23110) | Backport HBASE-23054 "Remove synchronization block from MetaTableMetrics and fix LossyCounting algorithm" to branch-1 |  Major | metrics | Duo Zhang | Andrew Kyle Purtell |
| [HBASE-23101](https://issues.apache.org/jira/browse/HBASE-23101) | Backport HBASE-22380 to branch-1 |  Blocker | . | Wellington Chevreuil | Wellington Chevreuil |


### OTHER:

| JIRA | Summary | Priority | Component | Reporter | Contributor |
|:---- |:---- | :--- |:---- |:---- |:---- |
| [HBASE-22833](https://issues.apache.org/jira/browse/HBASE-22833) | MultiRowRangeFilter should provide a method for creating a filter which is functionally equivalent to multiple prefix filters |  Minor | Client | Itsuki Toyota | Itsuki Toyota |
| [HBASE-19230](https://issues.apache.org/jira/browse/HBASE-19230) | Write up fixVersion policy from dev discussion in refguide |  Major | documentation | Michael Stack | Murtaza Hassan |
| [HBASE-21606](https://issues.apache.org/jira/browse/HBASE-21606) | Document use of the meta table load metrics added in HBASE-19722 |  Critical | documentation, meta, metrics, Operability | Sean Busbey | Mate Szalay-Beko |
| [HBASE-22911](https://issues.apache.org/jira/browse/HBASE-22911) | fewer concurrent github PR builds |  Critical | build | Sean Busbey | Sean Busbey |
| [HBASE-22913](https://issues.apache.org/jira/browse/HBASE-22913) | Use Hadoop label for nightly builds |  Major | build | Duo Zhang | Gavin McDonald |
| [HBASE-23023](https://issues.apache.org/jira/browse/HBASE-23023) | upgrade shellcheck used to test in nightly and precommit |  Major | build | Sean Busbey | Sean Busbey |
| [HBASE-23053](https://issues.apache.org/jira/browse/HBASE-23053) | Disable concurrent nightly builds |  Minor | build | Peter Somogyi | Peter Somogyi |
| [HBASE-22991](https://issues.apache.org/jira/browse/HBASE-22991) | Release 1.4.11 |  Major | community | Sean Busbey | Sean Busbey |


