
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
# Apache Hadoop Changelog

## Release 3.0.0-alpha2 - Unreleased (as of 2016-09-15)

### INCOMPATIBLE CHANGES:

| JIRA | Summary | Priority | Component | Reporter | Contributor |
|:---- |:---- | :--- |:---- |:---- |:---- |
| [YARN-5049](https://issues.apache.org/jira/browse/YARN-5049) | Extend NMStateStore to save queued container information |  Major | nodemanager, resourcemanager | Konstantinos Karanasos | Konstantinos Karanasos |
| [HADOOP-13301](https://issues.apache.org/jira/browse/HADOOP-13301) | Millisecond timestamp for FsShell console log and MapReduce jobsummary log |  Minor | . | John Zhuge | John Zhuge |
| [HDFS-10650](https://issues.apache.org/jira/browse/HDFS-10650) | DFSClient#mkdirs and DFSClient#primitiveMkdir should use default directory permission |  Minor | . | John Zhuge | John Zhuge |
| [HDFS-10725](https://issues.apache.org/jira/browse/HDFS-10725) | Caller context should always be constructed by a builder |  Minor | ipc | Mingliang Liu | Mingliang Liu |
| [HADOOP-13361](https://issues.apache.org/jira/browse/HADOOP-13361) | Modify hadoop\_verify\_user to be consistent with hadoop\_subcommand\_opts (ie more granularity) |  Major | scripts | Allen Wittenauer | Allen Wittenauer |
| [HDFS-6962](https://issues.apache.org/jira/browse/HDFS-6962) | ACL inheritance conflicts with umaskmode |  Critical | security | LINTE | John Zhuge |
| [HADOOP-13341](https://issues.apache.org/jira/browse/HADOOP-13341) | Deprecate HADOOP\_SERVERNAME\_OPTS; replace with (command)\_(subcommand)\_OPTS |  Major | scripts | Allen Wittenauer | Allen Wittenauer |
| [HADOOP-13588](https://issues.apache.org/jira/browse/HADOOP-13588) | ConfServlet should respect Accept request header |  Major | conf | Weiwei Yang | Weiwei Yang |
| [HDFS-10636](https://issues.apache.org/jira/browse/HDFS-10636) | Modify ReplicaInfo to remove the assumption that replica metadata and data are stored in java.io.File. |  Major | datanode, fs | Virajith Jalaparti | Virajith Jalaparti |
| [HADOOP-13218](https://issues.apache.org/jira/browse/HADOOP-13218) | Migrate other Hadoop side tests to prepare for removing WritableRPCEngine |  Major | test | Kai Zheng | Wei Zhou |


### NEW FEATURES:

| JIRA | Summary | Priority | Component | Reporter | Contributor |
|:---- |:---- | :--- |:---- |:---- |:---- |
| [HDFS-10584](https://issues.apache.org/jira/browse/HDFS-10584) | Allow long-running Mover tool to login with keytab |  Major | balancer & mover, security | Rakesh R | Rakesh R |


### IMPROVEMENTS:

| JIRA | Summary | Priority | Component | Reporter | Contributor |
|:---- |:---- | :--- |:---- |:---- |:---- |
| [HDFS-10425](https://issues.apache.org/jira/browse/HDFS-10425) | Clean up NNStorage and TestSaveNamespace |  Minor | . | Andras Bokor | Andras Bokor |
| [YARN-5456](https://issues.apache.org/jira/browse/YARN-5456) | container-executor support for FreeBSD, NetBSD, and others if conf path is absolute |  Major | nodemanager, security | Allen Wittenauer | Allen Wittenauer |
| [HDFS-10682](https://issues.apache.org/jira/browse/HDFS-10682) | Replace FsDatasetImpl object lock with a separate lock object |  Major | datanode | Chen Liang | Chen Liang |
| [YARN-5550](https://issues.apache.org/jira/browse/YARN-5550) | TestYarnCLI#testGetContainers should format according to CONTAINER\_PATTERN |  Minor | client, test | Jonathan Hung | Jonathan Hung |
| [HDFS-10814](https://issues.apache.org/jira/browse/HDFS-10814) | Add assertion for getNumEncryptionZones when no EZ is created |  Minor | test | Vinitha Reddy Gankidi | Vinitha Reddy Gankidi |
| [HDFS-10784](https://issues.apache.org/jira/browse/HDFS-10784) | Implement WebHdfsFileSystem#listStatusIterator |  Major | webhdfs | Andrew Wang | Andrew Wang |
| [HDFS-10817](https://issues.apache.org/jira/browse/HDFS-10817) | Add Logging for Long-held NN Read Locks |  Major | logging, namenode | Erik Krogen | Erik Krogen |
| [HADOOP-13465](https://issues.apache.org/jira/browse/HADOOP-13465) | Design Server.Call to be extensible for unified call queue |  Major | ipc | Daryn Sharp | Daryn Sharp |
| [HDFS-10822](https://issues.apache.org/jira/browse/HDFS-10822) | Log DataNodes in the write pipeline |  Trivial | hdfs-client | John Zhuge | John Zhuge |
| [HDFS-10833](https://issues.apache.org/jira/browse/HDFS-10833) | Fix JSON errors in WebHDFS.md examples |  Trivial | documentation | Andrew Wang | Andrew Wang |
| [HDFS-10778](https://issues.apache.org/jira/browse/HDFS-10778) | Add -format option to make the output of FileDistribution processor human-readable in OfflineImageViewer |  Major | tools | Yiqun Lin | Yiqun Lin |
| [HDFS-10847](https://issues.apache.org/jira/browse/HDFS-10847) | Complete the document for FileDistribution processor in OfflineImageViewer |  Minor | documentation | Yiqun Lin | Yiqun Lin |
| [HADOOP-13519](https://issues.apache.org/jira/browse/HADOOP-13519) | Make Path serializable |  Minor | io | Steve Loughran | Steve Loughran |
| [HDFS-10742](https://issues.apache.org/jira/browse/HDFS-10742) | Measure lock time in FsDatasetImpl |  Major | datanode | Chen Liang | Chen Liang |
| [HDFS-10831](https://issues.apache.org/jira/browse/HDFS-10831) | Add log when URLConnectionFactory.openConnection failed |  Minor | webhdfs | yunjiong zhao | yunjiong zhao |
| [HDFS-10855](https://issues.apache.org/jira/browse/HDFS-10855) | Fix typos in HDFS documents |  Minor | documentation | Yiqun Lin | Yiqun Lin |
| [HDFS-10837](https://issues.apache.org/jira/browse/HDFS-10837) | Standardize serializiation of WebHDFS DirectoryListing |  Major | webhdfs | Andrew Wang | Andrew Wang |
| [HADOOP-13598](https://issues.apache.org/jira/browse/HADOOP-13598) | Add eol=lf for unix format files in .gitattributes |  Major | . | Akira Ajisaka | Yiqun Lin |


### BUG FIXES:

| JIRA | Summary | Priority | Component | Reporter | Contributor |
|:---- |:---- | :--- |:---- |:---- |:---- |
| [HDFS-10639](https://issues.apache.org/jira/browse/HDFS-10639) | Fix typos in HDFSDiskbalancer.md |  Trivial | documentation | Akira Ajisaka | Yiqun Lin |
| [HADOOP-13073](https://issues.apache.org/jira/browse/HADOOP-13073) | RawLocalFileSystem does not react on changing umask |  Major | fs | Andras Bokor | Andras Bokor |
| [HADOOP-9427](https://issues.apache.org/jira/browse/HADOOP-9427) | Use JUnit assumptions to skip platform-specific tests |  Major | test | Arpit Agarwal | Gergely Novák |
| [YARN-5431](https://issues.apache.org/jira/browse/YARN-5431) | TimeLineReader daemon start should allow to pass its own reader opts |  Major | scripts, timelinereader | Rohith Sharma K S | Rohith Sharma K S |
| [YARN-5121](https://issues.apache.org/jira/browse/YARN-5121) | fix some container-executor portability issues |  Blocker | nodemanager, security | Allen Wittenauer | Allen Wittenauer |
| [HADOOP-13440](https://issues.apache.org/jira/browse/HADOOP-13440) | FileContext does not react on changing umask via configuration |  Major | . | Yufei Gu | Akira Ajisaka |
| [MAPREDUCE-6682](https://issues.apache.org/jira/browse/MAPREDUCE-6682) | TestMRCJCFileOutputCommitter fails intermittently |  Major | test | Brahma Reddy Battula | Akira Ajisaka |
| [HDFS-9696](https://issues.apache.org/jira/browse/HDFS-9696) | Garbage snapshot records lingering forever |  Critical | . | Kihwal Lee | Kihwal Lee |
| [HDFS-10773](https://issues.apache.org/jira/browse/HDFS-10773) | BlockSender should not synchronize on the dataset object |  Major | datanode | Arpit Agarwal | Chen Liang |
| [HDFS-10763](https://issues.apache.org/jira/browse/HDFS-10763) | Open files can leak permanently due to inconsistent lease update |  Critical | . | Kihwal Lee | Kihwal Lee |
| [HADOOP-13532](https://issues.apache.org/jira/browse/HADOOP-13532) | Fix typo in hadoop\_connect\_to\_hosts error message |  Trivial | scripts | Albert Chu | Albert Chu |
| [HADOOP-13533](https://issues.apache.org/jira/browse/HADOOP-13533) | User cannot set empty HADOOP\_SSH\_OPTS environment variable option |  Minor | scripts | Albert Chu | Albert Chu |
| [HDFS-8915](https://issues.apache.org/jira/browse/HDFS-8915) | TestFSNamesystem.testFSLockGetWaiterCount fails intermittently in jenkins |  Minor | test | Anu Engineer | Masatake Iwasaki |
| [MAPREDUCE-4784](https://issues.apache.org/jira/browse/MAPREDUCE-4784) | TestRecovery occasionally fails |  Major | mrv2, test | Jason Lowe | Haibo Chen |
| [HDFS-10760](https://issues.apache.org/jira/browse/HDFS-10760) | DataXceiver#run() should not log InvalidToken exception as an error |  Major | . | Pan Yuxuan | Pan Yuxuan |
| [HDFS-10729](https://issues.apache.org/jira/browse/HDFS-10729) | Improve log message for edit loading failures caused by FS limit checks. |  Major | namenode | Wei-Chiu Chuang | Wei-Chiu Chuang |
| [YARN-5221](https://issues.apache.org/jira/browse/YARN-5221) | Expose UpdateResourceRequest API to allow AM to request for change in container properties |  Major | . | Arun Suresh | Arun Suresh |
| [HADOOP-13375](https://issues.apache.org/jira/browse/HADOOP-13375) | o.a.h.security.TestGroupsCaching.testBackgroundRefreshCounters seems flaky |  Major | security, test | Mingliang Liu | Weiwei Yang |
| [HADOOP-13508](https://issues.apache.org/jira/browse/HADOOP-13508) | FsPermission string constructor does not recognize sticky bit |  Major | . | Atul Sikaria | Atul Sikaria |
| [HDFS-10820](https://issues.apache.org/jira/browse/HDFS-10820) | Reuse closeResponder to reset the response variable in DataStreamer#run |  Minor | . | Yiqun Lin | Yiqun Lin |
| [HDFS-10835](https://issues.apache.org/jira/browse/HDFS-10835) | Fix typos in httpfs.sh |  Trivial | httpfs | John Zhuge | John Zhuge |
| [HDFS-10841](https://issues.apache.org/jira/browse/HDFS-10841) | Remove duplicate or unused variable in appendFile() |  Minor | . | Kihwal Lee | Kihwal Lee |
| [HADOOP-13558](https://issues.apache.org/jira/browse/HADOOP-13558) | UserGroupInformation created from a Subject incorrectly tries to renew the Kerberos ticket |  Major | security | Alejandro Abdelnur | Xiao Chen |
| [HADOOP-13388](https://issues.apache.org/jira/browse/HADOOP-13388) | Clean up TestLocalFileSystemPermission |  Trivial | fs | Andras Bokor | Andras Bokor |
| [HDFS-10844](https://issues.apache.org/jira/browse/HDFS-10844) | test\_libhdfs\_threaded\_hdfs\_static and test\_libhdfs\_zerocopy\_hdfs\_static are failing |  Major | libhdfs | Akira Ajisaka | Akira Ajisaka |
| [HDFS-9038](https://issues.apache.org/jira/browse/HDFS-9038) | DFS reserved space is erroneously counted towards non-DFS used. |  Major | datanode | Chris Nauroth | Brahma Reddy Battula |
| [MAPREDUCE-6628](https://issues.apache.org/jira/browse/MAPREDUCE-6628) | Potential memory leak in CryptoOutputStream |  Major | security | Mariappan Asokan | Mariappan Asokan |
| [HDFS-10832](https://issues.apache.org/jira/browse/HDFS-10832) | Propagate ACL bit and isEncrypted bit in HttpFS FileStatus permissions |  Critical | httpfs | Andrew Wang | Andrew Wang |
| [HDFS-9781](https://issues.apache.org/jira/browse/HDFS-9781) | FsDatasetImpl#getBlockReports can occasionally throw NullPointerException |  Major | datanode | Wei-Chiu Chuang | Manoj Govindassamy |
| [HDFS-10830](https://issues.apache.org/jira/browse/HDFS-10830) | FsDatasetImpl#removeVolumes crashes with IllegalMonitorStateException when vol being removed is in use |  Major | hdfs | Manoj Govindassamy | Arpit Agarwal |
| [HADOOP-13587](https://issues.apache.org/jira/browse/HADOOP-13587) | distcp.map.bandwidth.mb is overwritten even when -bandwidth flag isn\'t set |  Minor | tools/distcp | Zoran Dimitrijevic | Zoran Dimitrijevic |
| [HDFS-10856](https://issues.apache.org/jira/browse/HDFS-10856) | Update the comment of BPServiceActor$Scheduler#scheduleNextBlockReport |  Minor | documentation | Akira Ajisaka | Yiqun Lin |
| [YARN-5630](https://issues.apache.org/jira/browse/YARN-5630) | NM fails to start after downgrade from 2.8 to 2.7 |  Blocker | nodemanager | Jason Lowe | Jason Lowe |
| [HADOOP-13616](https://issues.apache.org/jira/browse/HADOOP-13616) | Broken code snippet area in Hadoop Benchmarking |  Minor | documentation | Kai Sasaki | Kai Sasaki |


### SUB-TASKS:

| JIRA | Summary | Priority | Component | Reporter | Contributor |
|:---- |:---- | :--- |:---- |:---- |:---- |
| [HDFS-10588](https://issues.apache.org/jira/browse/HDFS-10588) | False alarm in datanode log - ERROR - Disk Balancer is not enabled |  Major | datanode, hdfs | Weiwei Yang | Weiwei Yang |
| [HDFS-10681](https://issues.apache.org/jira/browse/HDFS-10681) | DiskBalancer: query command should report Plan file path apart from PlanID |  Minor | diskbalancer | Manoj Govindassamy | Manoj Govindassamy |
| [YARN-5457](https://issues.apache.org/jira/browse/YARN-5457) | Refactor DistributedScheduling framework to pull out common functionality |  Major | resourcemanager | Arun Suresh | Arun Suresh |
| [HDFS-10598](https://issues.apache.org/jira/browse/HDFS-10598) | DiskBalancer does not execute multi-steps plan. |  Critical | diskbalancer | Lei (Eddy) Xu | Lei (Eddy) Xu |
| [HADOOP-13355](https://issues.apache.org/jira/browse/HADOOP-13355) | Handle HADOOP\_CLIENT\_OPTS in a function |  Major | scripts | Allen Wittenauer | Allen Wittenauer |
| [HADOOP-13554](https://issues.apache.org/jira/browse/HADOOP-13554) | Add an equivalent of hadoop\_subcmd\_opts for secure opts |  Major | scripts | Allen Wittenauer | Allen Wittenauer |
| [HADOOP-13562](https://issues.apache.org/jira/browse/HADOOP-13562) | Change hadoop\_subcommand\_opts to use only uppercase |  Major | scripts | Allen Wittenauer | Allen Wittenauer |
| [HADOOP-13358](https://issues.apache.org/jira/browse/HADOOP-13358) | Modify HDFS to use hadoop\_subcommand\_opts |  Major | scripts | Allen Wittenauer | Allen Wittenauer |
| [HADOOP-13356](https://issues.apache.org/jira/browse/HADOOP-13356) | Add a function to handle command\_subcommand\_OPTS |  Major | scripts | Allen Wittenauer | Allen Wittenauer |
| [HADOOP-13357](https://issues.apache.org/jira/browse/HADOOP-13357) | Modify common to use hadoop\_subcommand\_opts |  Major | scripts | Allen Wittenauer | Allen Wittenauer |
| [HADOOP-13359](https://issues.apache.org/jira/browse/HADOOP-13359) | Modify YARN to use hadoop\_subcommand\_opts |  Major | scripts | Allen Wittenauer | Allen Wittenauer |
| [HDFS-9392](https://issues.apache.org/jira/browse/HDFS-9392) | Admins support for maintenance state |  Major | . | Ming Ma | Ming Ma |
| [HADOOP-13564](https://issues.apache.org/jira/browse/HADOOP-13564) | modify mapred to use hadoop\_subcommand\_opts |  Major | scripts | Allen Wittenauer | Allen Wittenauer |
| [HDFS-10813](https://issues.apache.org/jira/browse/HDFS-10813) | DiskBalancer: Add the getNodeList method in Command |  Minor | balancer & mover | Yiqun Lin | Yiqun Lin |
| [HADOOP-13563](https://issues.apache.org/jira/browse/HADOOP-13563) | hadoop\_subcommand\_opts should print name not actual content during debug |  Major | scripts | Allen Wittenauer | Allen Wittenauer |
| [HADOOP-13360](https://issues.apache.org/jira/browse/HADOOP-13360) | Documentation for HADOOP\_subcommand\_OPTS |  Major | scripts | Allen Wittenauer | Allen Wittenauer |
| [YARN-5596](https://issues.apache.org/jira/browse/YARN-5596) | Fix failing unit test in TestDockerContainerRuntime |  Minor | nodemanager, yarn | Sidharta Seethana | Sidharta Seethana |
| [HADOOP-13547](https://issues.apache.org/jira/browse/HADOOP-13547) | Optimize IPC client protobuf decoding |  Major | . | Daryn Sharp | Daryn Sharp |
| [YARN-5576](https://issues.apache.org/jira/browse/YARN-5576) | Allow resource localization while container is running |  Major | . | Jian He | Jian He |
| [HADOOP-13549](https://issues.apache.org/jira/browse/HADOOP-13549) | Eliminate intermediate buffer for server-side PB encoding |  Major | ipc | Daryn Sharp | Daryn Sharp |
| [HADOOP-13447](https://issues.apache.org/jira/browse/HADOOP-13447) | Refactor S3AFileSystem to support introduction of separate metadata repository and tests. |  Major | fs/s3 | Chris Nauroth | Chris Nauroth |
| [HDFS-9847](https://issues.apache.org/jira/browse/HDFS-9847) | HDFS configuration should accept time units |  Major | . | Yiqun Lin | Yiqun Lin |
| [HDFS-8901](https://issues.apache.org/jira/browse/HDFS-8901) | Use ByteBuffer in striping positional read |  Major | erasure-coding | Kai Zheng | SammiChen |
| [HDFS-10845](https://issues.apache.org/jira/browse/HDFS-10845) | Change defaults in hdfs-site.xml to match timeunit type |  Minor | datanode, namenode | Yiqun Lin | Yiqun Lin |
| [HDFS-10553](https://issues.apache.org/jira/browse/HDFS-10553) | DiskBalancer: Rename Tools/DiskBalancer class to Tools/DiskBalancerCLI |  Minor | balancer & mover | Anu Engineer | Manoj Govindassamy |
| [HDFS-9849](https://issues.apache.org/jira/browse/HDFS-9849) | DiskBalancer : reduce lock path in shutdown code |  Major | balancer & mover | Anu Engineer | Yuanbo Liu |
| [YARN-5566](https://issues.apache.org/jira/browse/YARN-5566) | Client-side NM graceful decom is not triggered when jobs finish |  Major | nodemanager | Robert Kanter | Robert Kanter |
| [HADOOP-10940](https://issues.apache.org/jira/browse/HADOOP-10940) | RPC client does no bounds checking of responses |  Critical | ipc | Daryn Sharp | Daryn Sharp |
| [HDFS-10808](https://issues.apache.org/jira/browse/HDFS-10808) | DiskBalancer does not execute multi-steps plan-redux |  Major | balancer & mover | Anu Engineer | Anu Engineer |
| [HDFS-10821](https://issues.apache.org/jira/browse/HDFS-10821) | DiskBalancer: Report command support with multiple nodes |  Major | balancer & mover | Yiqun Lin | Yiqun Lin |
| [HDFS-10858](https://issues.apache.org/jira/browse/HDFS-10858) | FBR processing may generate incorrect reportedBlock-blockGroup mapping |  Blocker | erasure-coding | Jing Zhao | Jing Zhao |
| [HDFS-10599](https://issues.apache.org/jira/browse/HDFS-10599) | DiskBalancer: Execute CLI via Shell |  Major | balancer & mover | Anu Engineer | Manoj Govindassamy |
| [HDFS-10562](https://issues.apache.org/jira/browse/HDFS-10562) | DiskBalancer: update documentation on how to report issues and debug |  Minor | balancer & mover | Anu Engineer | Anu Engineer |
| [HDFS-10805](https://issues.apache.org/jira/browse/HDFS-10805) | Reduce runtime for append test |  Minor | test | Gergely Novák | Gergely Novák |
| [YARN-5620](https://issues.apache.org/jira/browse/YARN-5620) | Core changes in NodeManager to support re-initialization of Containers with new launchContext |  Major | . | Arun Suresh | Arun Suresh |


### OTHER:

| JIRA | Summary | Priority | Component | Reporter | Contributor |
|:---- |:---- | :--- |:---- |:---- |:---- |
| [YARN-5495](https://issues.apache.org/jira/browse/YARN-5495) | Remove import wildcard in CapacityScheduler |  Trivial | capacityscheduler | Ray Chiang | Ray Chiang |

