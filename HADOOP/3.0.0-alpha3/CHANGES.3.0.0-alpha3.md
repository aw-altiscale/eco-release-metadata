
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

## Release 3.0.0-alpha3 - Unreleased (as of 2017-05-04)

### INCOMPATIBLE CHANGES:

| JIRA | Summary | Priority | Component | Reporter | Contributor |
|:---- |:---- | :--- |:---- |:---- |:---- |
| [HDFS-10860](https://issues.apache.org/jira/browse/HDFS-10860) | Switch HttpFS from Tomcat to Jetty |  Blocker | httpfs | John Zhuge | John Zhuge |
| [HADOOP-13929](https://issues.apache.org/jira/browse/HADOOP-13929) | ADLS connector should not check in contract-test-options.xml |  Major | fs/adl, test | John Zhuge | John Zhuge |
| [HDFS-11100](https://issues.apache.org/jira/browse/HDFS-11100) | Recursively deleting file protected by sticky bit should fail |  Critical | fs | John Zhuge | John Zhuge |
| [HADOOP-13805](https://issues.apache.org/jira/browse/HADOOP-13805) | UGI.getCurrentUser() fails if user does not have a keytab associated |  Major | security | Alejandro Abdelnur | Xiao Chen |
| [HDFS-11405](https://issues.apache.org/jira/browse/HDFS-11405) | Rename "erasurecode" CLI subcommand to "ec" |  Blocker | erasure-coding | Andrew Wang | Manoj Govindassamy |
| [HDFS-11426](https://issues.apache.org/jira/browse/HDFS-11426) | Refactor EC CLI to be similar to storage policies CLI |  Major | erasure-coding, shell | Andrew Wang | Andrew Wang |
| [HDFS-11427](https://issues.apache.org/jira/browse/HDFS-11427) | Rename "rs-default" to "rs" |  Major | erasure-coding | Andrew Wang | Andrew Wang |
| [HDFS-11382](https://issues.apache.org/jira/browse/HDFS-11382) | Persist Erasure Coding Policy ID in a new optional field in INodeFile in FSImage |  Major | hdfs | Manoj Govindassamy | Manoj Govindassamy |
| [HDFS-11428](https://issues.apache.org/jira/browse/HDFS-11428) | Change setErasureCodingPolicy to take a required string EC policy name |  Major | erasure-coding | Andrew Wang | Andrew Wang |
| [HADOOP-14138](https://issues.apache.org/jira/browse/HADOOP-14138) | Remove S3A ref from META-INF service discovery, rely on existing core-default entry |  Critical | fs/s3 | Steve Loughran | Steve Loughran |
| [HDFS-11152](https://issues.apache.org/jira/browse/HDFS-11152) | Start erasure coding policy ID number from 1 instead of 0 to void potential unexpected errors |  Blocker | erasure-coding | SammiChen | SammiChen |
| [HDFS-11314](https://issues.apache.org/jira/browse/HDFS-11314) | Enforce set of enabled EC policies on the NameNode |  Blocker | erasure-coding | Andrew Wang | Andrew Wang |
| [HDFS-11505](https://issues.apache.org/jira/browse/HDFS-11505) | Do not enable any erasure coding policies by default |  Major | erasure-coding | Andrew Wang | Manoj Govindassamy |
| [HADOOP-10101](https://issues.apache.org/jira/browse/HADOOP-10101) | Update guava dependency to the latest version |  Major | . | Rakesh R | Tsuyoshi Ozawa |
| [HADOOP-14267](https://issues.apache.org/jira/browse/HADOOP-14267) | Make DistCpOptions class immutable |  Major | tools/distcp | Mingliang Liu | Mingliang Liu |
| [HADOOP-14202](https://issues.apache.org/jira/browse/HADOOP-14202) | fix jsvc/secure user var inconsistencies |  Major | scripts | Allen Wittenauer | Allen Wittenauer |
| [HADOOP-14174](https://issues.apache.org/jira/browse/HADOOP-14174) | Set default ADLS access token provider type to ClientCredential |  Major | fs/adl | John Zhuge | John Zhuge |
| [YARN-6298](https://issues.apache.org/jira/browse/YARN-6298) | Metric preemptCall is not used in new preemption |  Blocker | fairscheduler | Yufei Gu | Yufei Gu |
| [HADOOP-14285](https://issues.apache.org/jira/browse/HADOOP-14285) | Update minimum version of Maven from 3.0 to 3.3 |  Major | . | Akira Ajisaka | Akira Ajisaka |
| [HADOOP-14225](https://issues.apache.org/jira/browse/HADOOP-14225) | Remove xmlenc dependency |  Minor | . | Chris Douglas | Chris Douglas |
| [HADOOP-13665](https://issues.apache.org/jira/browse/HADOOP-13665) | Erasure Coding codec should support fallback coder |  Blocker | io | Wei-Chiu Chuang | Kai Sasaki |
| [HADOOP-14248](https://issues.apache.org/jira/browse/HADOOP-14248) | Retire SharedInstanceProfileCredentialsProvider in trunk. |  Major | fs/s3 | Mingliang Liu | Mingliang Liu |
| [HDFS-11565](https://issues.apache.org/jira/browse/HDFS-11565) | Use compact identifiers for built-in ECPolicies in HdfsFileStatus |  Blocker | erasure-coding | Andrew Wang | Andrew Wang |
| [YARN-3427](https://issues.apache.org/jira/browse/YARN-3427) | Remove deprecated methods from ResourceCalculatorProcessTree |  Blocker | . | Karthik Kambatla | Miklos Szegedi |
| [HDFS-11402](https://issues.apache.org/jira/browse/HDFS-11402) | HDFS Snapshots should capture point-in-time copies of OPEN files |  Major | hdfs | Manoj Govindassamy | Manoj Govindassamy |
| [HADOOP-10105](https://issues.apache.org/jira/browse/HADOOP-10105) | remove httpclient dependency |  Blocker | build | Colin P. McCabe | Akira Ajisaka |
| [HADOOP-13200](https://issues.apache.org/jira/browse/HADOOP-13200) | Implement customizable and configurable erasure coders |  Blocker | . | Kai Zheng | Tim Yao |
| [YARN-2962](https://issues.apache.org/jira/browse/YARN-2962) | ZKRMStateStore: Limit the number of znodes under a znode |  Critical | resourcemanager | Karthik Kambatla | Varun Saxena |


### NEW FEATURES:

| JIRA | Summary | Priority | Component | Reporter | Contributor |
|:---- |:---- | :--- |:---- |:---- |:---- |
| [YARN-5910](https://issues.apache.org/jira/browse/YARN-5910) | Support for multi-cluster delegation tokens |  Minor | security | Clay B. | Jian He |
| [YARN-5864](https://issues.apache.org/jira/browse/YARN-5864) | YARN Capacity Scheduler - Queue Priorities |  Major | . | Wangda Tan | Wangda Tan |
| [HDFS-11194](https://issues.apache.org/jira/browse/HDFS-11194) | Maintain aggregated peer performance metrics on NameNode |  Major | namenode | Xiaobing Zhou | Arpit Agarwal |
| [HADOOP-14049](https://issues.apache.org/jira/browse/HADOOP-14049) | Honour AclBit flag associated to file/folder permission for Azure datalake account |  Major | fs/adl | Vishwajeet Dusane | Vishwajeet Dusane |
| [YARN-5280](https://issues.apache.org/jira/browse/YARN-5280) | Allow YARN containers to run with Java Security Manager |  Minor | nodemanager, yarn | Greg Phillips | Greg Phillips |
| [HADOOP-14048](https://issues.apache.org/jira/browse/HADOOP-14048) | REDO operation of WASB#AtomicRename should create placeholder blob for destination folder |  Critical | fs/azure | NITIN VERMA | NITIN VERMA |
| [YARN-6451](https://issues.apache.org/jira/browse/YARN-6451) | Add RM monitor validating metrics invariants |  Major | . | Carlo Curino | Carlo Curino |
| [MAPREDUCE-6871](https://issues.apache.org/jira/browse/MAPREDUCE-6871) | Allow users to specify racks and nodes for strict locality for AMs |  Major | client | Robert Kanter | Robert Kanter |
| [HDFS-11417](https://issues.apache.org/jira/browse/HDFS-11417) | Add datanode admin command to get the storage info. |  Major | . | Surendra Singh Lilhore | Surendra Singh Lilhore |
| [YARN-679](https://issues.apache.org/jira/browse/YARN-679) | add an entry point that can start any Yarn service |  Major | api | Steve Loughran | Steve Loughran |


### IMPROVEMENTS:

| JIRA | Summary | Priority | Component | Reporter | Contributor |
|:---- |:---- | :--- |:---- |:---- |:---- |
| [HADOOP-14002](https://issues.apache.org/jira/browse/HADOOP-14002) | Document -DskipShade property in BUILDING.txt |  Minor | build, documentation | Hanisha Koneru | Hanisha Koneru |
| [HADOOP-13956](https://issues.apache.org/jira/browse/HADOOP-13956) | Read ADLS credentials from Credential Provider |  Critical | fs/adl | John Zhuge | John Zhuge |
| [HADOOP-13962](https://issues.apache.org/jira/browse/HADOOP-13962) | Update ADLS SDK to 2.1.4 |  Major | fs/adl | John Zhuge | John Zhuge |
| [YARN-5547](https://issues.apache.org/jira/browse/YARN-5547) | NMLeveldbStateStore should be more tolerant of unknown keys |  Major | nodemanager | Jason Lowe | Ajith S |
| [HADOOP-13990](https://issues.apache.org/jira/browse/HADOOP-13990) | Document KMS usage of CredentialProvider API |  Minor | documentation, kms | John Zhuge | John Zhuge |
| [HDFS-10534](https://issues.apache.org/jira/browse/HDFS-10534) | NameNode WebUI should display DataNode usage histogram |  Major | namenode, ui | Zhe Zhang | Kai Sasaki |
| [MAPREDUCE-6829](https://issues.apache.org/jira/browse/MAPREDUCE-6829) | Add peak memory usage counter for each task |  Major | mrv2 | Yufei Gu | Miklos Szegedi |
| [HDFS-11374](https://issues.apache.org/jira/browse/HDFS-11374) | Skip FSync in Test util CreateEditsLog to speed up edit log generation |  Minor | hdfs | Hanisha Koneru | Hanisha Koneru |
| [HDFS-9884](https://issues.apache.org/jira/browse/HDFS-9884) | Use doxia macro to generate in-page TOC of HDFS site documentation |  Major | documentation | Masatake Iwasaki | Masatake Iwasaki |
| [YARN-6131](https://issues.apache.org/jira/browse/YARN-6131) | FairScheduler: Lower update interval for faster tests |  Major | fairscheduler | Karthik Kambatla | Karthik Kambatla |
| [YARN-6106](https://issues.apache.org/jira/browse/YARN-6106) | Document FairScheduler \'allowPreemptionFrom\' queue property |  Minor | fairscheduler | Yufei Gu | Yufei Gu |
| [YARN-4658](https://issues.apache.org/jira/browse/YARN-4658) | Typo in o.a.h.yarn.server.resourcemanager.scheduler.fair.TestFairScheduler comment |  Major | . | Daniel Templeton | Udai Kiran Potluri |
| [MAPREDUCE-6644](https://issues.apache.org/jira/browse/MAPREDUCE-6644) | Use doxia macro to generate in-page TOC of MapReduce site documentation |  Major | documentation | Masatake Iwasaki | Masatake Iwasaki |
| [HDFS-11370](https://issues.apache.org/jira/browse/HDFS-11370) | Optimize NamenodeFsck#getReplicaInfo |  Minor | namenode | Takanobu Asanuma | Takanobu Asanuma |
| [HDFS-11112](https://issues.apache.org/jira/browse/HDFS-11112) | Journal Nodes should refuse to format non-empty directories |  Major | . | Arpit Agarwal | Yiqun Lin |
| [HDFS-11353](https://issues.apache.org/jira/browse/HDFS-11353) | Improve the unit tests relevant to DataNode volume failure testing |  Major | . | Yiqun Lin | Yiqun Lin |
| [HADOOP-14053](https://issues.apache.org/jira/browse/HADOOP-14053) | Update the link to HTrace SpanReceivers |  Minor | documentation | Akira Ajisaka | Yiqun Lin |
| [HADOOP-12097](https://issues.apache.org/jira/browse/HADOOP-12097) | Allow port range to be specified while starting webapp |  Major | . | Varun Saxena | Varun Saxena |
| [HDFS-10219](https://issues.apache.org/jira/browse/HDFS-10219) | Change the default value for dfs.namenode.reconstruction.pending.timeout-sec from -1 to 300 |  Minor | . | Akira Ajisaka | Yiqun Lin |
| [MAPREDUCE-6404](https://issues.apache.org/jira/browse/MAPREDUCE-6404) | Allow AM to specify a port range for starting its webapp |  Major | applicationmaster | Varun Saxena | Varun Saxena |
| [MAPREDUCE-6842](https://issues.apache.org/jira/browse/MAPREDUCE-6842) | Update the links in PiEstimator document |  Minor | documentation | Akira Ajisaka | Jung Yoo |
| [HDFS-11210](https://issues.apache.org/jira/browse/HDFS-11210) | Enhance key rolling to guarantee new KeyVersion is returned from generateEncryptedKeys after a key is rolled |  Major | encryption, kms | Xiao Chen | Xiao Chen |
| [HDFS-11409](https://issues.apache.org/jira/browse/HDFS-11409) | DatanodeInfo getNetworkLocation and setNetworkLocation shoud use volatile instead of synchronized |  Minor | performance | Chen Liang | Chen Liang |
| [YARN-6061](https://issues.apache.org/jira/browse/YARN-6061) | Add an UncaughtExceptionHandler for critical threads in RM |  Major | resourcemanager | Yufei Gu | Yufei Gu |
| [YARN-4753](https://issues.apache.org/jira/browse/YARN-4753) | Use doxia macro to generate in-page TOC of YARN site documentation |  Major | documentation | Masatake Iwasaki | Masatake Iwasaki |
| [HDFS-11333](https://issues.apache.org/jira/browse/HDFS-11333) | Print a user friendly error message when plugins are not found |  Minor | namenode | Wei-Chiu Chuang | Wei-Chiu Chuang |
| [YARN-6174](https://issues.apache.org/jira/browse/YARN-6174) | Log files pattern should be same for both running and finished container |  Major | yarn | Sumana Sathish | Xuan Gong |
| [HDFS-11375](https://issues.apache.org/jira/browse/HDFS-11375) | Display the volume storage type in datanode UI |  Minor | datanode, ui | Surendra Singh Lilhore | Surendra Singh Lilhore |
| [YARN-6125](https://issues.apache.org/jira/browse/YARN-6125) | The application attempt\'s diagnostic message should have a maximum size |  Critical | resourcemanager | Daniel Templeton | Andras Piros |
| [HADOOP-14077](https://issues.apache.org/jira/browse/HADOOP-14077) | Improve the patch of HADOOP-13119 |  Major | security | Yuanbo Liu | Yuanbo Liu |
| [HDFS-11406](https://issues.apache.org/jira/browse/HDFS-11406) | Remove unused getStartInstance and getFinalizeInstance in FSEditLogOp |  Trivial | . | Andrew Wang | Alison Yu |
| [HDFS-11438](https://issues.apache.org/jira/browse/HDFS-11438) | Fix typo in error message of StoragePolicyAdmin tool |  Trivial | . | Alison Yu | Alison Yu |
| [YARN-6194](https://issues.apache.org/jira/browse/YARN-6194) | Cluster capacity in SchedulingPolicy is updated only on allocation file reload |  Major | fairscheduler | Karthik Kambatla | Yufei Gu |
| [HADOOP-13321](https://issues.apache.org/jira/browse/HADOOP-13321) | Deprecate FileSystem APIs that promote inefficient call patterns. |  Major | fs | Chris Nauroth | Mingliang Liu |
| [HADOOP-14097](https://issues.apache.org/jira/browse/HADOOP-14097) | Remove Java6 specific code from GzipCodec.java |  Minor | . | Akira Ajisaka | Elek, Marton |
| [HADOOP-13817](https://issues.apache.org/jira/browse/HADOOP-13817) | Add a finite shell command timeout to ShellBasedUnixGroupsMapping |  Minor | security | Harsh J | Harsh J |
| [HDFS-11295](https://issues.apache.org/jira/browse/HDFS-11295) | Check storage remaining instead of node remaining in BlockPlacementPolicyDefault.chooseReplicaToDelete() |  Major | namenode | Xiao Liang | Elek, Marton |
| [HADOOP-14127](https://issues.apache.org/jira/browse/HADOOP-14127) | Add log4j configuration to enable logging in hadoop-distcp\'s tests |  Minor | test | Xiao Chen | Xiao Chen |
| [HDFS-11466](https://issues.apache.org/jira/browse/HDFS-11466) | Change dfs.namenode.write-lock-reporting-threshold-ms default from 1000ms to 5000ms |  Major | namenode | Andrew Wang | Andrew Wang |
| [YARN-6189](https://issues.apache.org/jira/browse/YARN-6189) | Improve application status log message when RM restarted when app is in NEW state |  Major | . | Yesha Vora | Junping Du |
| [HDFS-11432](https://issues.apache.org/jira/browse/HDFS-11432) | Federation : Support fully qualified path for Quota/Snapshot/cacheadmin/cryptoadmin commands |  Major | federation | Brahma Reddy Battula | Brahma Reddy Battula |
| [HDFS-11461](https://issues.apache.org/jira/browse/HDFS-11461) | DataNode Disk Outlier Detection |  Major | hdfs | Hanisha Koneru | Hanisha Koneru |
| [HDFS-11416](https://issues.apache.org/jira/browse/HDFS-11416) | Refactor out system default erasure coding policy |  Major | erasure-coding | Andrew Wang | Andrew Wang |
| [HADOOP-13930](https://issues.apache.org/jira/browse/HADOOP-13930) | Azure: Add Authorization support to WASB |  Major | fs/azure | Dushyanth | Sivaguru Sankaridurg |
| [HDFS-11494](https://issues.apache.org/jira/browse/HDFS-11494) | Log message when DN is not selected for block replication |  Minor | . | Yiqun Lin | Yiqun Lin |
| [HDFS-8741](https://issues.apache.org/jira/browse/HDFS-8741) | Proper error msg to be printed when invalid operation type is given to WebHDFS operations |  Minor | webhdfs | Archana T | Surendra Singh Lilhore |
| [HADOOP-14108](https://issues.apache.org/jira/browse/HADOOP-14108) | CLI MiniCluster: add an option to specify NameNode HTTP port |  Minor | . | Takanobu Asanuma | Takanobu Asanuma |
| [HDFS-10838](https://issues.apache.org/jira/browse/HDFS-10838) | Last full block report received time for each DN should be easily discoverable |  Major | ui | Arpit Agarwal | Surendra Singh Lilhore |
| [HDFS-11477](https://issues.apache.org/jira/browse/HDFS-11477) | Simplify file IO profiling configuration |  Minor | . | Hanisha Koneru | Hanisha Koneru |
| [YARN-6287](https://issues.apache.org/jira/browse/YARN-6287) | RMCriticalThreadUncaughtExceptionHandler.rmContext should be final |  Minor | resourcemanager | Daniel Templeton | Corey Barker |
| [HADOOP-14150](https://issues.apache.org/jira/browse/HADOOP-14150) | Implement getHomeDirectory() method in NativeAzureFileSystem |  Critical | fs/azure | Namit Maheshwari | Santhosh G Nayak |
| [YARN-6300](https://issues.apache.org/jira/browse/YARN-6300) | NULL\_UPDATE\_REQUESTS is redundant in TestFairScheduler |  Minor | . | Daniel Templeton | Yuanbo Liu |
| [HDFS-11506](https://issues.apache.org/jira/browse/HDFS-11506) | Move ErasureCodingPolicyManager#getSystemDefaultPolicy to test code |  Major | erasure-coding | Andrew Wang | Manoj Govindassamy |
| [HADOOP-13946](https://issues.apache.org/jira/browse/HADOOP-13946) | Document how HDFS updates timestamps in the FS spec; compare with object stores |  Minor | documentation, fs | Steve Loughran | Steve Loughran |
| [YARN-6042](https://issues.apache.org/jira/browse/YARN-6042) | Dump scheduler and queue state information into FairScheduler DEBUG log |  Major | fairscheduler | Yufei Gu | Yufei Gu |
| [HDFS-11511](https://issues.apache.org/jira/browse/HDFS-11511) | Support Timeout when checking single disk |  Major | hdfs | Hanisha Koneru | Hanisha Koneru |
| [HDFS-10601](https://issues.apache.org/jira/browse/HDFS-10601) | Improve log message to include hostname when the NameNode is in safemode |  Minor | . | Kuhu Shukla | Kuhu Shukla |
| [HDFS-11517](https://issues.apache.org/jira/browse/HDFS-11517) | Expose slow disks via DataNode JMX |  Major | hdfs | Hanisha Koneru | Hanisha Koneru |
| [HADOOP-14169](https://issues.apache.org/jira/browse/HADOOP-14169) | Implement listStatusIterator, listLocatedStatus for ViewFs |  Minor | viewfs | Erik Krogen | Erik Krogen |
| [HDFS-11547](https://issues.apache.org/jira/browse/HDFS-11547) | Add logs for slow BlockReceiver while writing data to disk |  Major | datanode | Xiaobing Zhou | Xiaobing Zhou |
| [MAPREDUCE-6865](https://issues.apache.org/jira/browse/MAPREDUCE-6865) | Fix typo in javadoc for DistributedCache |  Trivial | . | Attila Sasvari | Attila Sasvari |
| [YARN-6309](https://issues.apache.org/jira/browse/YARN-6309) | Fair scheduler docs should have the queue and queuePlacementPolicy elements listed in bold so that they\'re easier to see |  Minor | fairscheduler | Daniel Templeton | esmaeil mirzaee |
| [HADOOP-13945](https://issues.apache.org/jira/browse/HADOOP-13945) | Azure: Add Kerberos and Delegation token support to WASB client. |  Major | fs/azure | Santhosh G Nayak | Santhosh G Nayak |
| [HDFS-11545](https://issues.apache.org/jira/browse/HDFS-11545) | Propagate DataNode\'s slow disks info to the NameNode via Heartbeat |  Major | . | Hanisha Koneru | Hanisha Koneru |
| [YARN-6284](https://issues.apache.org/jira/browse/YARN-6284) | hasAlreadyRun should be final in ResourceManager.StandByTransitionRunnable |  Major | resourcemanager | Daniel Templeton | Laura Adams |
| [HADOOP-14213](https://issues.apache.org/jira/browse/HADOOP-14213) | Move Configuration runtime check for hadoop-site.xml to initialization |  Major | . | Jonathan Eagles | Jonathan Eagles |
| [HDFS-10649](https://issues.apache.org/jira/browse/HDFS-10649) | Remove unused PermissionStatus#applyUMask |  Trivial | . | John Zhuge | Chen Liang |
| [HDFS-11574](https://issues.apache.org/jira/browse/HDFS-11574) | Spelling mistakes in the Java source |  Trivial | . | hu xiaodong | hu xiaodong |
| [HDFS-11534](https://issues.apache.org/jira/browse/HDFS-11534) | Add counters for number of blocks in pending IBR |  Major | hdfs | Xiaobing Zhou | Xiaobing Zhou |
| [YARN-5956](https://issues.apache.org/jira/browse/YARN-5956) | Refactor ClientRMService to unify error handling across apis |  Minor | resourcemanager | Kai Sasaki | Kai Sasaki |
| [YARN-6379](https://issues.apache.org/jira/browse/YARN-6379) | Remove unused argument in ClientRMService |  Trivial | . | Kai Sasaki | Kai Sasaki |
| [HADOOP-14233](https://issues.apache.org/jira/browse/HADOOP-14233) | Delay construction of PreCondition.check failure message in Configuration#set |  Major | . | Jonathan Eagles | Jonathan Eagles |
| [HADOOP-14240](https://issues.apache.org/jira/browse/HADOOP-14240) | Configuration#get return value optimization |  Major | . | Jonathan Eagles | Jonathan Eagles |
| [YARN-6339](https://issues.apache.org/jira/browse/YARN-6339) | Improve performance for createAndGetApplicationReport |  Major | . | yunjiong zhao | yunjiong zhao |
| [HDFS-11170](https://issues.apache.org/jira/browse/HDFS-11170) | Add builder-based create API to FileSystem |  Major | . | SammiChen | SammiChen |
| [YARN-6329](https://issues.apache.org/jira/browse/YARN-6329) | Remove unnecessary TODO comment from AppLogAggregatorImpl.java |  Minor | . | Akira Ajisaka | victor bertschinger |
| [HDFS-9705](https://issues.apache.org/jira/browse/HDFS-9705) | Refine the behaviour of getFileChecksum when length = 0 |  Minor | . | Kai Zheng | SammiChen |
| [HADOOP-14250](https://issues.apache.org/jira/browse/HADOOP-14250) | Correct spelling of \'separate\' and variants |  Minor | . | Doris Gu | Doris Gu |
| [HDFS-10974](https://issues.apache.org/jira/browse/HDFS-10974) | Document replication factor for EC files. |  Major | documentation, erasure-coding | Wei-Chiu Chuang | Yiqun Lin |
| [HDFS-11551](https://issues.apache.org/jira/browse/HDFS-11551) | Handle SlowDiskReport from DataNode at the NameNode |  Major | hdfs | Hanisha Koneru | Hanisha Koneru |
| [HDFS-11603](https://issues.apache.org/jira/browse/HDFS-11603) | Improve slow mirror/disk warnings in BlockReceiver |  Major | datanode | Arpit Agarwal | Arpit Agarwal |
| [HDFS-11560](https://issues.apache.org/jira/browse/HDFS-11560) | Expose slow disks via NameNode JMX |  Major | namenode | Hanisha Koneru | Hanisha Koneru |
| [HDFS-11598](https://issues.apache.org/jira/browse/HDFS-11598) | Improve -setrep for Erasure Coded files |  Major | shell | Wei-Chiu Chuang | Yiqun Lin |
| [HDFS-9651](https://issues.apache.org/jira/browse/HDFS-9651) | All web UIs should include a robots.txt file |  Minor | . | Lars Francke | Lars Francke |
| [HADOOP-14280](https://issues.apache.org/jira/browse/HADOOP-14280) | Fix compilation of TestKafkaMetrics |  Major | tools | Andrew Wang | Andrew Wang |
| [HDFS-11628](https://issues.apache.org/jira/browse/HDFS-11628) | Clarify the behavior of HDFS Mover in documentation |  Major | documentation | Xiaobing Zhou | Xiaobing Zhou |
| [YARN-6381](https://issues.apache.org/jira/browse/YARN-6381) | FSAppAttempt has several variables that should be final |  Major | fairscheduler | Daniel Templeton | Ameet Zaveri |
| [HDFS-11302](https://issues.apache.org/jira/browse/HDFS-11302) | Improve Logging for SSLHostnameVerifier |  Major | security | Xiaoyu Yao | Chen Liang |
| [HADOOP-14104](https://issues.apache.org/jira/browse/HADOOP-14104) | Client should always ask namenode for kms provider path. |  Major | kms | Rushabh S Shah | Rushabh S Shah |
| [YARN-5797](https://issues.apache.org/jira/browse/YARN-5797) | Add metrics to the node manager for cleaning the PUBLIC and PRIVATE caches |  Major | . | Chris Trezzo | Chris Trezzo |
| [HADOOP-14276](https://issues.apache.org/jira/browse/HADOOP-14276) | Add a nanosecond API to Time/Timer/FakeTimer |  Minor | util | Erik Krogen | Erik Krogen |
| [HDFS-11623](https://issues.apache.org/jira/browse/HDFS-11623) | Move system erasure coding policies into hadoop-hdfs-client |  Major | erasure-coding | Andrew Wang | Andrew Wang |
| [HADOOP-14008](https://issues.apache.org/jira/browse/HADOOP-14008) | Upgrade to Apache Yetus 0.4.0 |  Major | build, test | Allen Wittenauer | Allen Wittenauer |
| [YARN-6195](https://issues.apache.org/jira/browse/YARN-6195) | Export UsedCapacity and AbsoluteUsedCapacity to JMX |  Major | capacityscheduler, metrics, yarn | Benson Qiu | Benson Qiu |
| [HDFS-11558](https://issues.apache.org/jira/browse/HDFS-11558) | BPServiceActor thread name is too long |  Minor | datanode | Tsz Wo Nicholas Sze | Xiaobing Zhou |
| [HADOOP-14246](https://issues.apache.org/jira/browse/HADOOP-14246) | Authentication Tokens should use SecureRandom instead of Random and 256 bit secrets |  Major | security | Robert Kanter | Robert Kanter |
| [HDFS-11645](https://issues.apache.org/jira/browse/HDFS-11645) | DataXceiver thread should log the actual error when getting InvalidMagicNumberException |  Minor | datanode | Chen Liang | Chen Liang |
| [HDFS-11648](https://issues.apache.org/jira/browse/HDFS-11648) | Lazy construct the IIP pathname |  Major | . | Daryn Sharp | Daryn Sharp |
| [HADOOP-14274](https://issues.apache.org/jira/browse/HADOOP-14274) | Azure: Simplify Ranger-WASB policy model |  Major | fs/azure | Sivaguru Sankaridurg | Sivaguru Sankaridurg |
| [MAPREDUCE-6673](https://issues.apache.org/jira/browse/MAPREDUCE-6673) | Add a test example job that grows in memory usage over time |  Major | test | Karthik Kambatla | Karthik Kambatla |
| [HADOOP-11794](https://issues.apache.org/jira/browse/HADOOP-11794) | Enable distcp to copy blocks in parallel |  Major | tools/distcp | dhruba borthakur | Yongjun Zhang |
| [YARN-6406](https://issues.apache.org/jira/browse/YARN-6406) | Remove SchedulerRequestKeys when no more pending ResourceRequest |  Major | . | Arun Suresh | Arun Suresh |
| [HDFS-11652](https://issues.apache.org/jira/browse/HDFS-11652) | Improve ECSchema and ErasureCodingPolicy toString, hashCode, equals |  Minor | erasure-coding | Andrew Wang | Andrew Wang |
| [HDFS-11634](https://issues.apache.org/jira/browse/HDFS-11634) | Optimize BlockIterator when iterating starts in the middle. |  Major | . | Konstantin Shvachko | Konstantin Shvachko |
| [HDFS-11531](https://issues.apache.org/jira/browse/HDFS-11531) | Expose hedged read metrics via libHDFS API |  Major | libhdfs | Sailesh Mukil | Sailesh Mukil |
| [HADOOP-14316](https://issues.apache.org/jira/browse/HADOOP-14316) | Switch from Findbugs to Spotbugs |  Major | build | Allen Wittenauer | Allen Wittenauer |
| [HDFS-11421](https://issues.apache.org/jira/browse/HDFS-11421) | Make WebHDFS\' ACLs RegEx configurable |  Major | webhdfs | Harsh J | Harsh J |
| [YARN-6164](https://issues.apache.org/jira/browse/YARN-6164) | Expose Queue Configurations per Node Label through YARN client api |  Major | . | Benson Qiu | Benson Qiu |
| [YARN-6392](https://issues.apache.org/jira/browse/YARN-6392) | Add submit time to Application Summary log |  Minor | resourcemanager | zhihai xu | zhihai xu |
| [HADOOP-12856](https://issues.apache.org/jira/browse/HADOOP-12856) | FileUtil.checkDest() and RawLocalFileSystem.mkdirs() to throw stricter IOEs; RawLocalFS contract tests to verify |  Minor | fs | Steve Loughran | Steve Loughran |
| [HADOOP-14340](https://issues.apache.org/jira/browse/HADOOP-14340) | Enable KMS and HttpFS to exclude SSL ciphers |  Minor | kms | John Zhuge | John Zhuge |
| [HDFS-11384](https://issues.apache.org/jira/browse/HDFS-11384) | Add option for balancer to disperse getBlocks calls to avoid NameNode\'s rpc.CallQueueLength spike |  Major | balancer & mover | yunjiong zhao | Konstantin Shvachko |
| [HADOOP-14309](https://issues.apache.org/jira/browse/HADOOP-14309) | Add PowerShell NodeFencer |  Minor | ha | Inigo Goiri | Inigo Goiri |
| [HADOOP-14359](https://issues.apache.org/jira/browse/HADOOP-14359) | Remove unnecessary shading of commons-httpclient |  Minor | . | Akira Ajisaka | Wei-Chiu Chuang |
| [HADOOP-14367](https://issues.apache.org/jira/browse/HADOOP-14367) | Remove unused setting from pom.xml |  Minor | build | Akira Ajisaka | Chen Liang |
| [HADOOP-14352](https://issues.apache.org/jira/browse/HADOOP-14352) | Make some HttpServer2 SSL properties optional |  Minor | kms | John Zhuge | John Zhuge |
| [HDFS-11722](https://issues.apache.org/jira/browse/HDFS-11722) | Change Datanode file IO profiling sampling to percentage |  Major | hdfs | Hanisha Koneru | Hanisha Koneru |


### BUG FIXES:

| JIRA | Summary | Priority | Component | Reporter | Contributor |
|:---- |:---- | :--- |:---- |:---- |:---- |
| [HADOOP-13858](https://issues.apache.org/jira/browse/HADOOP-13858) | TestGridmixMemoryEmulation and TestResourceUsageEmulators fail on the environment other than Linux or Windows |  Major | test | Akira Ajisaka | Akira Ajisaka |
| [YARN-6012](https://issues.apache.org/jira/browse/YARN-6012) | Remove node label (removeFromClusterNodeLabels) document is missing |  Major | documentation | Weiwei Yang | Ying Zhang |
| [YARN-6117](https://issues.apache.org/jira/browse/YARN-6117) | SharedCacheManager does not start up |  Major | . | Chris Trezzo | Chris Trezzo |
| [YARN-6082](https://issues.apache.org/jira/browse/YARN-6082) | Invalid REST api response for getApps since queueUsagePercentage is coming as INF |  Critical | . | Sunil G | Sunil G |
| [HDFS-11365](https://issues.apache.org/jira/browse/HDFS-11365) | Log portnumber in PrivilegedNfsGatewayStarter |  Minor | nfs | Mukul Kumar Singh | Mukul Kumar Singh |
| [MAPREDUCE-6808](https://issues.apache.org/jira/browse/MAPREDUCE-6808) | Log map attempts as part of shuffle handler audit log |  Major | . | Jonathan Eagles | Gergő Pásztor |
| [HADOOP-13989](https://issues.apache.org/jira/browse/HADOOP-13989) | Remove erroneous source jar option from hadoop-client shade configuration |  Minor | build | Joe Pallas | Joe Pallas |
| [HDFS-11369](https://issues.apache.org/jira/browse/HDFS-11369) | Change exception message in StorageLocationChecker |  Minor | datanode | Arpit Agarwal | Arpit Agarwal |
| [YARN-4975](https://issues.apache.org/jira/browse/YARN-4975) | Fair Scheduler: exception thrown when a parent queue marked \'parent\' has configured child queues |  Major | fairscheduler | Ashwin Shankar | Yufei Gu |
| [HDFS-11364](https://issues.apache.org/jira/browse/HDFS-11364) | Add a test to verify Audit log entries for setfacl/getfacl commands over FS shell |  Major | hdfs, test | Manoj Govindassamy | Manoj Govindassamy |
| [HDFS-11376](https://issues.apache.org/jira/browse/HDFS-11376) | Revert HDFS-8377 Support HTTP/2 in datanode |  Major | datanode | Andrew Wang | Xiao Chen |
| [HADOOP-13988](https://issues.apache.org/jira/browse/HADOOP-13988) | KMSClientProvider does not work with WebHDFS and Apache Knox w/ProxyUser |  Major | common, kms | Greg Senia | Xiaoyu Yao |
| [HADOOP-14029](https://issues.apache.org/jira/browse/HADOOP-14029) | Fix KMSClientProvider for non-secure proxyuser use case |  Major | common,kms | Xiaoyu Yao | Xiaoyu Yao |
| [YARN-5641](https://issues.apache.org/jira/browse/YARN-5641) | Localizer leaves behind tarballs after container is complete |  Major | . | Eric Badger | Eric Badger |
| [HADOOP-13992](https://issues.apache.org/jira/browse/HADOOP-13992) | KMS should load SSL configuration the same way as SSLFactory |  Major | kms, security | John Zhuge | John Zhuge |
| [HDFS-11378](https://issues.apache.org/jira/browse/HDFS-11378) | Verify multiple DataNodes can be decommissioned/maintenance at the same time |  Major | hdfs | Manoj Govindassamy | Manoj Govindassamy |
| [YARN-6103](https://issues.apache.org/jira/browse/YARN-6103) | Log updates for ZKRMStateStore |  Trivial | . | Bibin A Chundatt | Daniel Sturman |
| [HADOOP-14018](https://issues.apache.org/jira/browse/HADOOP-14018) | shaded jars of hadoop-client modules are missing hadoop\'s root LICENSE and NOTICE files |  Critical | . | John Zhuge | Elek, Marton |
| [HDFS-11335](https://issues.apache.org/jira/browse/HDFS-11335) | Remove HdfsClientConfigKeys.DFS\_CLIENT\_SLOW\_IO\_WARNING\_THRESHOLD\_KEY usage from DNConf |  Major | . | Manoj Govindassamy | Manoj Govindassamy |
| [HADOOP-13895](https://issues.apache.org/jira/browse/HADOOP-13895) | Make FileStatus Serializable |  Minor | fs | Chris Douglas | Chris Douglas |
| [HADOOP-14045](https://issues.apache.org/jira/browse/HADOOP-14045) | Aliyun OSS documentation missing from website |  Major | documentation, fs/oss | Andrew Wang | Yiqun Lin |
| [HDFS-11363](https://issues.apache.org/jira/browse/HDFS-11363) | Need more diagnosis info when seeing Slow waitForAckedSeqno |  Major | . | Yongjun Zhang | Xiao Chen |
| [HDFS-11387](https://issues.apache.org/jira/browse/HDFS-11387) | Socket reuse address option is not honored in PrivilegedNfsGatewayStarter |  Major | nfs | Mukul Kumar Singh | Mukul Kumar Singh |
| [HADOOP-14044](https://issues.apache.org/jira/browse/HADOOP-14044) | Synchronization issue in delegation token cancel functionality |  Major | . | Hrishikesh Gadre | Hrishikesh Gadre |
| [HDFS-11371](https://issues.apache.org/jira/browse/HDFS-11371) | Document missing metrics of erasure coding |  Minor | documentation, erasure-coding | Yiqun Lin | Yiqun Lin |
| [MAPREDUCE-6338](https://issues.apache.org/jira/browse/MAPREDUCE-6338) | MR AppMaster does not honor ephemeral port range |  Major | mr-am, mrv2 | Frank Nguyen | Frank Nguyen |
| [HDFS-11377](https://issues.apache.org/jira/browse/HDFS-11377) | Balancer hung due to no available mover threads |  Major | balancer & mover | yunjiong zhao | yunjiong zhao |
| [HADOOP-14047](https://issues.apache.org/jira/browse/HADOOP-14047) | Require admin to access KMS instrumentation servlets |  Minor | kms | John Zhuge | John Zhuge |
| [YARN-6135](https://issues.apache.org/jira/browse/YARN-6135) | Node manager REST API documentation is not up to date |  Trivial | nodemanager, restapi | Miklos Szegedi | Miklos Szegedi |
| [YARN-6145](https://issues.apache.org/jira/browse/YARN-6145) | Improve log message on fail over |  Major | . | Jian He | Jian He |
| [YARN-6031](https://issues.apache.org/jira/browse/YARN-6031) | Application recovery has failed when node label feature is turned off during RM recovery |  Minor | scheduler | Ying Zhang | Ying Zhang |
| [YARN-6137](https://issues.apache.org/jira/browse/YARN-6137) | Yarn client implicitly invoke ATS client which accesses HDFS |  Major | . | Yesha Vora | Li Lu |
| [HADOOP-13433](https://issues.apache.org/jira/browse/HADOOP-13433) | Race in UGI.reloginFromKeytab |  Major | security | Duo Zhang | Duo Zhang |
| [YARN-6112](https://issues.apache.org/jira/browse/YARN-6112) | UpdateCallDuration is calculated only when debug logging is enabled |  Major | fairscheduler | Yufei Gu | Yufei Gu |
| [YARN-6144](https://issues.apache.org/jira/browse/YARN-6144) | FairScheduler: preempted resources can become negative |  Blocker | fairscheduler, resourcemanager | Miklos Szegedi | Miklos Szegedi |
| [YARN-6118](https://issues.apache.org/jira/browse/YARN-6118) | Add javadoc for Resources.isNone |  Minor | scheduler | Karthik Kambatla | Andres Perez |
| [HADOOP-13119](https://issues.apache.org/jira/browse/HADOOP-13119) | Add ability to secure log servlet using proxy users |  Major | . | Jeffrey E  Rodriguez | Yuanbo Liu |
| [YARN-6166](https://issues.apache.org/jira/browse/YARN-6166) | Unnecessary INFO logs in AMRMClientAsyncImpl$CallbackHandlerThread.run |  Trivial | . | Grant W | Grant W |
| [HADOOP-14055](https://issues.apache.org/jira/browse/HADOOP-14055) | SwiftRestClient includes pass length in exception if auth fails |  Minor | security | Marcell Hegedus | Marcell Hegedus |
| [HDFS-11403](https://issues.apache.org/jira/browse/HDFS-11403) | Zookeper ACLs on NN HA enabled clusters to be handled consistently |  Major | hdfs | Laszlo Puskas | Hanisha Koneru |
| [HADOOP-13233](https://issues.apache.org/jira/browse/HADOOP-13233) | help of stat is confusing |  Trivial | documentation, fs | Xiaohe Lan | Attila Bukor |
| [YARN-3933](https://issues.apache.org/jira/browse/YARN-3933) | FairScheduler: Multiple calls to completedContainer are not safe |  Major | fairscheduler | Lavkesh Lahngir | Shiwei Guo |
| [HDFS-11407](https://issues.apache.org/jira/browse/HDFS-11407) | Document the missing usages of OfflineImageViewer processors |  Minor | documentation, tools | Yiqun Lin | Yiqun Lin |
| [HDFS-11408](https://issues.apache.org/jira/browse/HDFS-11408) | The config name of balance bandwidth is out of date |  Minor | balancer & mover, documentation | Yiqun Lin | Yiqun Lin |
| [HADOOP-14058](https://issues.apache.org/jira/browse/HADOOP-14058) | Fix NativeS3FileSystemContractBaseTest#testDirWithDifferentMarkersWorks |  Major | fs/s3, test | Akira Ajisaka | Yiqun Lin |
| [HDFS-11084](https://issues.apache.org/jira/browse/HDFS-11084) | Add a regression test for sticky bit support of OIV ReverseXML processor |  Major | tools | Wei-Chiu Chuang | Wei-Chiu Chuang |
| [HDFS-11391](https://issues.apache.org/jira/browse/HDFS-11391) | Numeric usernames do no work with WebHDFS FS (write access) |  Major | webhdfs | Pierre Villard | Pierre Villard |
| [HADOOP-13924](https://issues.apache.org/jira/browse/HADOOP-13924) | Update checkstyle and checkstyle plugin version to handle indentation of JDK8 Lambdas |  Major | . | Xiaoyu Yao | Akira Ajisaka |
| [HDFS-11238](https://issues.apache.org/jira/browse/HDFS-11238) | Fix checkstyle warnings in NameNode#createNameNode |  Trivial | namenode | Ethan Li | Ethan Li |
| [YARN-4212](https://issues.apache.org/jira/browse/YARN-4212) | FairScheduler: Can\'t create a DRF queue under a FAIR policy queue |  Major | . | Arun Suresh | Yufei Gu |
| [YARN-6177](https://issues.apache.org/jira/browse/YARN-6177) | Yarn client should exit with an informative error message if an incompatible Jersey library is used at client |  Major | . | Weiwei Yang | Weiwei Yang |
| [YARN-6171](https://issues.apache.org/jira/browse/YARN-6171) | ConcurrentModificationException on FSAppAttempt.containersToPreempt |  Major | fairscheduler | Miklos Szegedi | Miklos Szegedi |
| [HDFS-11410](https://issues.apache.org/jira/browse/HDFS-11410) | Use the cached instance when edit logging SetAclOp, SetXAttrOp and RemoveXAttrOp |  Major | namenode | Xiao Chen | Xiao Chen |
| [YARN-6188](https://issues.apache.org/jira/browse/YARN-6188) | Fix OOM issue with decommissioningNodesWatcher in the case of clusters with large number of nodes |  Major | resourcemanager | Ajay Jadhav | Ajay Jadhav |
| [HDFS-11379](https://issues.apache.org/jira/browse/HDFS-11379) | DFSInputStream may infinite loop requesting block locations |  Critical | hdfs-client | Daryn Sharp | Daryn Sharp |
| [HADOOP-14092](https://issues.apache.org/jira/browse/HADOOP-14092) | Typo in hadoop-aws index.md |  Trivial | fs/s3 | John Zhuge | John Zhuge |
| [HDFS-11177](https://issues.apache.org/jira/browse/HDFS-11177) | \'storagepolicies -getStoragePolicy\' command should accept URI based path. |  Major | shell | Surendra Singh Lilhore | Surendra Singh Lilhore |
| [HDFS-11404](https://issues.apache.org/jira/browse/HDFS-11404) | Increase timeout on TestShortCircuitLocalRead.testDeprecatedGetBlockLocalPathInfoRpc |  Major | . | Eric Badger | Eric Badger |
| [HADOOP-13826](https://issues.apache.org/jira/browse/HADOOP-13826) | S3A Deadlock in multipart copy due to thread pool limits. |  Critical | fs/s3 | Sean Mackrory | Sean Mackrory |
| [HADOOP-14017](https://issues.apache.org/jira/browse/HADOOP-14017) | User friendly name for ADLS user and group |  Major | fs/adl | John Zhuge | Vishwajeet Dusane |
| [MAPREDUCE-6825](https://issues.apache.org/jira/browse/MAPREDUCE-6825) | YARNRunner#createApplicationSubmissionContext method is longer than 150 lines |  Trivial | . | Chris Trezzo | Gergely Novák |
| [YARN-6210](https://issues.apache.org/jira/browse/YARN-6210) | FS: Node reservations can interfere with preemption |  Major | fairscheduler | Karthik Kambatla | Karthik Kambatla |
| [YARN-6211](https://issues.apache.org/jira/browse/YARN-6211) | Synchronization improvement for moveApplicationAcrossQueues and updateApplicationPriority |  Major | . | Bibin A Chundatt | Bibin A Chundatt |
| [HADOOP-14100](https://issues.apache.org/jira/browse/HADOOP-14100) | Upgrade Jsch jar to latest version to fix vulnerability in old versions |  Critical | . | Vinayakumar B | Vinayakumar B |
| [YARN-6222](https://issues.apache.org/jira/browse/YARN-6222) | TestFairScheduler.testReservationMetrics is flaky |  Major | fairscheduler | Yufei Gu | Yufei Gu |
| [HADOOP-14114](https://issues.apache.org/jira/browse/HADOOP-14114) | S3A can no longer handle unencoded + in URIs |  Minor | fs/s3 | Sean Mackrory | Sean Mackrory |
| [HADOOP-14116](https://issues.apache.org/jira/browse/HADOOP-14116) | FailoverOnNetworkExceptionRetry does not wait when failover on certain exception |  Major | . | Jian He | Jian He |
| [HDFS-11433](https://issues.apache.org/jira/browse/HDFS-11433) | Document missing usages of OfflineEditsViewer processors |  Minor | documentation, tools | Yiqun Lin | Yiqun Lin |
| [HDFS-11462](https://issues.apache.org/jira/browse/HDFS-11462) | Fix occasional BindException in TestNameNodeMetricsLogger |  Major | test | Arpit Agarwal | Arpit Agarwal |
| [HADOOP-14028](https://issues.apache.org/jira/browse/HADOOP-14028) | S3A BlockOutputStreams doesn\'t delete temporary files in multipart uploads or handle part upload failures |  Critical | fs/s3 | Seth Fitzsimmons | Steve Loughran |
| [YARN-6172](https://issues.apache.org/jira/browse/YARN-6172) | FSLeafQueue demand update needs to be atomic |  Major | resourcemanager | Varun Saxena | Miklos Szegedi |
| [HADOOP-14119](https://issues.apache.org/jira/browse/HADOOP-14119) | Remove unused imports from GzipCodec.java |  Minor | . | Akira Ajisaka | Yiqun Lin |
| [MAPREDUCE-6841](https://issues.apache.org/jira/browse/MAPREDUCE-6841) | Fix dead link in MapReduce tutorial document |  Minor | documentation | Akira Ajisaka | Victor Nee |
| [YARN-6231](https://issues.apache.org/jira/browse/YARN-6231) | FairSchedulerTestBase helper methods should call scheduler.update to avoid flakiness |  Major | . | Arun Suresh | Karthik Kambatla |
| [YARN-6239](https://issues.apache.org/jira/browse/YARN-6239) | Fix javac warnings in YARN that caused by deprecated FileSystem APIs |  Minor | . | Yiqun Lin | Yiqun Lin |
| [YARN-1728](https://issues.apache.org/jira/browse/YARN-1728) | Workaround guice3x-undecoded pathInfo in YARN WebApp |  Major | . | Abraham Elmahrek | Yuanbo Liu |
| [HADOOP-12556](https://issues.apache.org/jira/browse/HADOOP-12556) | KafkaSink jar files are created but not copied to target dist |  Major | . | Babak Behzad | Babak Behzad |
| [HDFS-11479](https://issues.apache.org/jira/browse/HDFS-11479) | Socket re-use address option should be used in SimpleUdpServer |  Major | nfs | Mukul Kumar Singh | Mukul Kumar Singh |
| [HDFS-11478](https://issues.apache.org/jira/browse/HDFS-11478) | Update EC commands in HDFSCommands.md |  Minor | documentation, erasure-coding | Yiqun Lin | Yiqun Lin |
| [MAPREDUCE-6852](https://issues.apache.org/jira/browse/MAPREDUCE-6852) | Job#updateStatus() failed with NPE due to race condition |  Major | . | Junping Du | Junping Du |
| [MAPREDUCE-6753](https://issues.apache.org/jira/browse/MAPREDUCE-6753) | Variable in byte printed directly in mapreduce client |  Major | client | Nemo Chen | Kai Sasaki |
| [HADOOP-6801](https://issues.apache.org/jira/browse/HADOOP-6801) | io.sort.mb and io.sort.factor were renamed and moved to mapreduce but are still in CommonConfigurationKeysPublic.java and used in SequenceFile.java |  Minor | . | Erik Steffl | Harsh J |
| [YARN-6263](https://issues.apache.org/jira/browse/YARN-6263) | NMTokenSecretManagerInRM.createAndGetNMToken is not thread safe |  Major | yarn | Haibo Chen | Haibo Chen |
| [YARN-6218](https://issues.apache.org/jira/browse/YARN-6218) | Fix TestAMRMClient when using FairScheduler |  Minor | . | Miklos Szegedi | Miklos Szegedi |
| [HDFS-11476](https://issues.apache.org/jira/browse/HDFS-11476) | Fix NPE in FsDatasetImpl#checkAndUpdate |  Major | datanode | Xiaobing Zhou | Xiaobing Zhou |
| [YARN-6271](https://issues.apache.org/jira/browse/YARN-6271) | yarn rmadin -getGroups returns information from standby RM |  Critical | yarn | Sumana Sathish | Jian He |
| [YARN-6270](https://issues.apache.org/jira/browse/YARN-6270) | WebUtils.getRMWebAppURLWithScheme() needs to honor RM HA setting |  Major | . | Sumana Sathish | Xuan Gong |
| [YARN-6278](https://issues.apache.org/jira/browse/YARN-6278) | Enforce to use correct node and npm version in new YARN-UI build |  Critical | . | Sunil G | Sunil G |
| [YARN-6248](https://issues.apache.org/jira/browse/YARN-6248) | user is not removed from UsersManager’s when app is killed with pending container requests. |  Major | . | Eric Payne | Eric Payne |
| [HADOOP-14026](https://issues.apache.org/jira/browse/HADOOP-14026) | start-build-env.sh: invalid docker image name |  Major | build | Gergő Pásztor | Gergő Pásztor |
| [HDFS-11441](https://issues.apache.org/jira/browse/HDFS-11441) | Add escaping to error message in KMS web UI |  Minor | security | Aaron T. Myers | Aaron T. Myers |
| [YARN-5665](https://issues.apache.org/jira/browse/YARN-5665) | Enhance documentation for yarn.resourcemanager.scheduler.class property |  Trivial | documentation | Miklos Szegedi | Yufei Gu |
| [HDFS-11498](https://issues.apache.org/jira/browse/HDFS-11498) | Make RestCsrfPreventionHandler and WebHdfsHandler compatible with Netty 4.0 |  Major | . | Andrew Wang | Andrew Wang |
| [MAPREDUCE-6855](https://issues.apache.org/jira/browse/MAPREDUCE-6855) | Specify charset when create String in CredentialsTestJob |  Minor | . | Akira Ajisaka | Kai Sasaki |
| [HADOOP-14087](https://issues.apache.org/jira/browse/HADOOP-14087) | S3A typo in pom.xml test exclusions |  Major | fs/s3 | Aaron Fabbri | Aaron Fabbri |
| [HDFS-11508](https://issues.apache.org/jira/browse/HDFS-11508) | Fix bind failure in SimpleTCPServer & Portmap where bind fails because socket is in TIME\_WAIT state |  Major | nfs | Mukul Kumar Singh | Mukul Kumar Singh |
| [MAPREDUCE-6839](https://issues.apache.org/jira/browse/MAPREDUCE-6839) | TestRecovery.testCrashed failed |  Major | test | Gergő Pásztor | Gergő Pásztor |
| [YARN-6207](https://issues.apache.org/jira/browse/YARN-6207) | Move application across queues should handle delayed event processing |  Major | capacity scheduler | Bibin A Chundatt | Bibin A Chundatt |
| [MAPREDUCE-6859](https://issues.apache.org/jira/browse/MAPREDUCE-6859) | hadoop-mapreduce-client-jobclient.jar sets a main class that isn\'t in the JAR |  Minor | client | Daniel Templeton | Daniel Templeton |
| [YARN-6297](https://issues.apache.org/jira/browse/YARN-6297) | TestAppLogAggregatorImp.verifyFilesUploaded() should check # of filed uploaded with that of files expected |  Major | . | Haibo Chen | Haibo Chen |
| [YARN-6165](https://issues.apache.org/jira/browse/YARN-6165) | Intra-queue preemption occurs even when preemption is turned off for a specific queue. |  Major | capacity scheduler, scheduler preemption | Eric Payne | Eric Payne |
| [HADOOP-14052](https://issues.apache.org/jira/browse/HADOOP-14052) | Fix dead link in KMS document |  Minor | documentation | Akira Ajisaka | Christina Vu |
| [YARN-6264](https://issues.apache.org/jira/browse/YARN-6264) | AM not launched when a single vcore is available on the cluster |  Major | fairscheduler | Yufei Gu | Yufei Gu |
| [YARN-6310](https://issues.apache.org/jira/browse/YARN-6310) | OutputStreams in AggregatedLogFormat.LogWriter can be left open upon exceptions |  Major | yarn | Haibo Chen | Haibo Chen |
| [HADOOP-14062](https://issues.apache.org/jira/browse/HADOOP-14062) | ApplicationMasterProtocolPBClientImpl.allocate fails with EOFException when RPC privacy is enabled |  Critical | . | Steven Rand | Steven Rand |
| [YARN-6321](https://issues.apache.org/jira/browse/YARN-6321) | TestResources test timeouts are too aggressive |  Major | test | Jason Lowe | Eric Badger |
| [HDFS-11340](https://issues.apache.org/jira/browse/HDFS-11340) | DataNode reconfigure for disks doesn\'t remove the failed volumes |  Major | . | Manoj Govindassamy | Manoj Govindassamy |
| [HADOOP-14156](https://issues.apache.org/jira/browse/HADOOP-14156) | Fix grammar error in ConfTest.java |  Trivial | test | Andrey Dyatlov | Andrey Dyatlov |
| [HDFS-11512](https://issues.apache.org/jira/browse/HDFS-11512) | Increase timeout on TestShortCircuitLocalRead#testSkipWithVerifyChecksum |  Minor | . | Eric Badger | Eric Badger |
| [HDFS-11499](https://issues.apache.org/jira/browse/HDFS-11499) | Decommissioning stuck because of failing recovery |  Major | hdfs, namenode | Lukas Majercak | Lukas Majercak |
| [HDFS-11395](https://issues.apache.org/jira/browse/HDFS-11395) | RequestHedgingProxyProvider#RequestHedgingInvocationHandler hides the Exception thrown from NameNode |  Major | ha | Nandakumar | Nandakumar |
| [HDFS-11526](https://issues.apache.org/jira/browse/HDFS-11526) | Fix confusing block recovery message |  Minor | datanode | Wei-Chiu Chuang | Yiqun Lin |
| [YARN-6327](https://issues.apache.org/jira/browse/YARN-6327) | Removing queues from CapacitySchedulerQueueManager and ParentQueue should be done with iterator |  Major | capacityscheduler | Jonathan Hung | Jonathan Hung |
| [HADOOP-14170](https://issues.apache.org/jira/browse/HADOOP-14170) | FileSystemContractBaseTest is not cleaning up test directory clearly |  Major | fs | Mingliang Liu | Mingliang Liu |
| [YARN-6331](https://issues.apache.org/jira/browse/YARN-6331) | Fix flakiness in TestFairScheduler#testDumpState |  Major | fairscheduler | Yufei Gu | Yufei Gu |
| [YARN-6328](https://issues.apache.org/jira/browse/YARN-6328) | Fix a spelling mistake in CapacityScheduler |  Trivial | capacity scheduler | Jin Yibo | Jin Yibo |
| [YARN-6336](https://issues.apache.org/jira/browse/YARN-6336) | Jenkins report YARN new UI build failure |  Blocker | . | Junping Du | Sunil G |
| [HDFS-11420](https://issues.apache.org/jira/browse/HDFS-11420) | Edit file should not be processed by the same type processor in OfflineEditsViewer |  Major | tools | Yiqun Lin | Yiqun Lin |
| [YARN-6294](https://issues.apache.org/jira/browse/YARN-6294) | ATS client should better handle Socket closed case |  Major | timelineclient | Sumana Sathish | Li Lu |
| [YARN-6332](https://issues.apache.org/jira/browse/YARN-6332) | Make RegistrySecurity use short user names for ZK ACLs |  Major | . | Billie Rinaldi | Billie Rinaldi |
| [YARN-4051](https://issues.apache.org/jira/browse/YARN-4051) | ContainerKillEvent lost when container is still recovering and application finishes |  Critical | nodemanager | sandflee | sandflee |
| [HDFS-11533](https://issues.apache.org/jira/browse/HDFS-11533) | reuseAddress option should be used for child channels in Portmap and SimpleTcpServer |  Major | nfs | Mukul Kumar Singh | Mukul Kumar Singh |
| [HADOOP-14191](https://issues.apache.org/jira/browse/HADOOP-14191) | Duplicate hadoop-minikdc dependency in hadoop-common module |  Minor | build | Akira Ajisaka | Xiaobing Zhou |
| [HDFS-10394](https://issues.apache.org/jira/browse/HDFS-10394) | move declaration of okhttp version from hdfs-client to hadoop-project POM |  Minor | build | Steve Loughran | Xiaobing Zhou |
| [HDFS-11516](https://issues.apache.org/jira/browse/HDFS-11516) | Admin command line should print message to stderr in failure case |  Minor | . | Kai Sasaki | Kai Sasaki |
| [YARN-6217](https://issues.apache.org/jira/browse/YARN-6217) | TestLocalCacheDirectoryManager test timeout is too aggressive |  Major | test | Jason Lowe | Miklos Szegedi |
| [YARN-6353](https://issues.apache.org/jira/browse/YARN-6353) | Clean up OrderingPolicy javadoc |  Minor | resourcemanager | Daniel Templeton | Daniel Templeton |
| [HADOOP-14059](https://issues.apache.org/jira/browse/HADOOP-14059) | typo in s3a rename(self, subdir) error message |  Minor | . | Steve Loughran | Steve Loughran |
| [HDFS-6648](https://issues.apache.org/jira/browse/HDFS-6648) | Order of namenodes in ConfiguredFailoverProxyProvider is undefined |  Major | ha, hdfs-client | Rafal Wojdyla | Inigo Goiri |
| [HADOOP-14204](https://issues.apache.org/jira/browse/HADOOP-14204) | S3A multipart commit failing, "UnsupportedOperationException at java.util.Collections$UnmodifiableList.sort" |  Critical | fs/s3 | Steve Loughran | Steve Loughran |
| [HADOOP-14187](https://issues.apache.org/jira/browse/HADOOP-14187) | Update ZooKeeper dependency to 3.4.9 and Curator dependency to 2.12.0 |  Major | . | Tsuyoshi Ozawa | Tsuyoshi Ozawa |
| [YARN-5934](https://issues.apache.org/jira/browse/YARN-5934) | Fix TestTimelineWebServices.testPrimaryFilterNumericString |  Major | test | Akira Ajisaka | Akira Ajisaka |
| [HDFS-11561](https://issues.apache.org/jira/browse/HDFS-11561) | HttpFS doc errors |  Trivial | documentation, httpfs, test | Yuanbo Liu | Yuanbo Liu |
| [HADOOP-9631](https://issues.apache.org/jira/browse/HADOOP-9631) | ViewFs should use underlying FileSystem\'s server side defaults |  Major | fs, viewfs | Lohit Vijayarenu | Erik Krogen |
| [HADOOP-14214](https://issues.apache.org/jira/browse/HADOOP-14214) | DomainSocketWatcher::add()/delete() should not self interrupt while looping await() |  Critical | hdfs-client | Mingliang Liu | Mingliang Liu |
| [HADOOP-14195](https://issues.apache.org/jira/browse/HADOOP-14195) | CredentialProviderFactory$getProviders is not thread-safe |  Major | security | Vihang Karajgaonkar | Vihang Karajgaonkar |
| [HADOOP-14211](https://issues.apache.org/jira/browse/HADOOP-14211) | FilterFs and ChRootedFs are too aggressive about enforcing "authorityNeeded" |  Major | viewfs | Erik Krogen | Erik Krogen |
| [YARN-6360](https://issues.apache.org/jira/browse/YARN-6360) | Prevent FS state dump logger from cramming other log files |  Major | fairscheduler | Yufei Gu | Yufei Gu |
| [YARN-6334](https://issues.apache.org/jira/browse/YARN-6334) | TestRMFailover#testAutomaticFailover always passes even when it should fail |  Major | . | Yufei Gu | Yufei Gu |
| [MAPREDUCE-6866](https://issues.apache.org/jira/browse/MAPREDUCE-6866) | Fix getNumMapTasks() documentation in JobConf |  Minor | documentation | Joe Mészáros | Joe Mészáros |
| [MAPREDUCE-6868](https://issues.apache.org/jira/browse/MAPREDUCE-6868) | License check for jdiff output files should be ignored |  Major | build | Akira Ajisaka | Akira Ajisaka |
| [HDFS-11555](https://issues.apache.org/jira/browse/HDFS-11555) | Fix typos in class OfflineImageReconstructor |  Trivial | . | Yiqun Lin | Yiqun Lin |
| [HDFS-10506](https://issues.apache.org/jira/browse/HDFS-10506) | OIV\'s ReverseXML processor cannot reconstruct some snapshot details |  Major | tools | Colin P. McCabe | Akira Ajisaka |
| [HDFS-11486](https://issues.apache.org/jira/browse/HDFS-11486) | Client close() should not fail fast if the last block is being decommissioned |  Major | . | Wei-Chiu Chuang | Wei-Chiu Chuang |
| [YARN-6359](https://issues.apache.org/jira/browse/YARN-6359) | TestRM#testApplicationKillAtAcceptedState fails rarely due to race condition |  Major | test | Robert Kanter | Robert Kanter |
| [YARN-5368](https://issues.apache.org/jira/browse/YARN-5368) | Memory leak in timeline server |  Critical | timelineserver | Wataru Yukawa | Jonathan Eagles |
| [YARN-6050](https://issues.apache.org/jira/browse/YARN-6050) | AMs can\'t be scheduled on racks or nodes |  Major | . | Robert Kanter | Robert Kanter |
| [HDFS-11571](https://issues.apache.org/jira/browse/HDFS-11571) | Typo in DataStorage exception message |  Minor | datanode | Daniel Templeton | Anna Budai |
| [YARN-5685](https://issues.apache.org/jira/browse/YARN-5685) | RM configuration allows all failover methods to disabled when automatic failover is enabled |  Critical | resourcemanager | Daniel Templeton | Daniel Templeton |
| [HADOOP-14223](https://issues.apache.org/jira/browse/HADOOP-14223) | Extend FileStatus#toString() to include details like Erasure Coding and Encryption |  Major | fs | Manoj Govindassamy | Manoj Govindassamy |
| [HADOOP-14247](https://issues.apache.org/jira/browse/HADOOP-14247) | FileContextMainOperationsBaseTest should clean up test root path |  Minor | fs, test | Mingliang Liu | Mingliang Liu |
| [MAPREDUCE-6862](https://issues.apache.org/jira/browse/MAPREDUCE-6862) | Fragments are not handled correctly by resource limit checking |  Minor | . | Chris Trezzo | Chris Trezzo |
| [MAPREDUCE-6873](https://issues.apache.org/jira/browse/MAPREDUCE-6873) | MR Job Submission Fails if MR framework application path not on defaultFS |  Minor | mrv2 | Erik Krogen | Erik Krogen |
| [HADOOP-14256](https://issues.apache.org/jira/browse/HADOOP-14256) | [S3A DOC] Correct the format for "Seoul" example |  Minor | documentation, s3 | Brahma Reddy Battula | Brahma Reddy Battula |
| [MAPREDUCE-6850](https://issues.apache.org/jira/browse/MAPREDUCE-6850) | Shuffle Handler keep-alive connections are closed from the server side |  Major | . | Jonathan Eagles | Jonathan Eagles |
| [MAPREDUCE-6836](https://issues.apache.org/jira/browse/MAPREDUCE-6836) | exception thrown when accessing the job configuration web UI |  Minor | webapps | Sangjin Lee | Haibo Chen |
| [HDFS-11592](https://issues.apache.org/jira/browse/HDFS-11592) | Closing a file has a wasteful preconditions in NameNode |  Major | namenode | Eric Badger | Eric Badger |
| [YARN-6354](https://issues.apache.org/jira/browse/YARN-6354) | LeveldbRMStateStore can parse invalid keys when recovering reservations |  Major | resourcemanager | Jason Lowe | Jason Lowe |
| [YARN-5703](https://issues.apache.org/jira/browse/YARN-5703) | ReservationAgents are not correctly configured |  Major | capacity scheduler, resourcemanager | Sean Po | Manikandan R |
| [HADOOP-14268](https://issues.apache.org/jira/browse/HADOOP-14268) | Fix markdown itemization in hadoop-aws documents |  Minor | documentation, fs/s3 | Akira Ajisaka | Akira Ajisaka |
| [HADOOP-14271](https://issues.apache.org/jira/browse/HADOOP-14271) | Correct spelling of \'occurred\' and variants |  Trivial | . | Yeliang Cang | Yeliang Cang |
| [HADOOP-14272](https://issues.apache.org/jira/browse/HADOOP-14272) | Azure: WasbRemoteCallHelper should use String equals for comparison. |  Major | fs/azure | Santhosh G Nayak | Santhosh G Nayak |
| [HADOOP-14273](https://issues.apache.org/jira/browse/HADOOP-14273) | Azure: NativeAzureFileSystem should respect config for kerberosSupportEnabled flag |  Major | fs/azure | Santhosh G Nayak | Santhosh G Nayak |
| [YARN-6436](https://issues.apache.org/jira/browse/YARN-6436) | TestSchedulingPolicy#testParseSchedulingPolicy timeout is too low |  Major | test | Jason Lowe | Eric Badger |
| [YARN-6004](https://issues.apache.org/jira/browse/YARN-6004) | Refactor TestResourceLocalizationService#testDownloadingResourcesOnContainer so that it is less than 150 lines |  Trivial | test | Chris Trezzo | Chris Trezzo |
| [YARN-6420](https://issues.apache.org/jira/browse/YARN-6420) | RM startup failure due to wrong order in nodelabel editlog |  Critical | . | Bibin A Chundatt | Bibin A Chundatt |
| [MAPREDUCE-6824](https://issues.apache.org/jira/browse/MAPREDUCE-6824) | TaskAttemptImpl#createCommonContainerLaunchContext is longer than 150 lines |  Trivial | . | Chris Trezzo | Chris Trezzo |
| [YARN-6403](https://issues.apache.org/jira/browse/YARN-6403) | Invalid local resource request can raise NPE and make NM exit |  Major | nodemanager | Tao Yang | Tao Yang |
| [HDFS-11538](https://issues.apache.org/jira/browse/HDFS-11538) | Move ClientProtocol HA proxies into hadoop-hdfs-client |  Blocker | hdfs-client | Andrew Wang | Huafeng Wang |
| [YARN-6437](https://issues.apache.org/jira/browse/YARN-6437) | TestSignalContainer#testSignalRequestDeliveryToNM fails intermittently |  Major | test | Jason Lowe | Jason Lowe |
| [YARN-6448](https://issues.apache.org/jira/browse/YARN-6448) | Continuous scheduling thread crashes while sorting nodes |  Major | . | Yufei Gu | Yufei Gu |
| [HDFS-11596](https://issues.apache.org/jira/browse/HDFS-11596) | hadoop-hdfs-client jar is in the wrong directory in release tarball |  Critical | build | Andrew Wang | Yuanbo Liu |
| [MAPREDUCE-6846](https://issues.apache.org/jira/browse/MAPREDUCE-6846) | Fragments specified for libjar paths are not handled correctly |  Minor | . | Chris Trezzo | Chris Trezzo |
| [HDFS-11131](https://issues.apache.org/jira/browse/HDFS-11131) | TestThrottledAsyncChecker#testCancellation is flaky |  Major | test | Arpit Agarwal | Arpit Agarwal |
| [HDFS-11362](https://issues.apache.org/jira/browse/HDFS-11362) | StorageDirectory should initialize a non-null default StorageDirType |  Minor | hdfs | Hanisha Koneru | Hanisha Koneru |
| [HDFS-11608](https://issues.apache.org/jira/browse/HDFS-11608) | HDFS write crashed with block size greater than 2 GB |  Critical | hdfs-client | Xiaobing Zhou | Xiaobing Zhou |
| [MAPREDUCE-6201](https://issues.apache.org/jira/browse/MAPREDUCE-6201) | TestNetworkedJob fails on trunk |  Major | . | Robert Kanter | Peter Bacsko |
| [YARN-6288](https://issues.apache.org/jira/browse/YARN-6288) | Exceptions during aggregated log writes are mishandled |  Critical | log-aggregation | Akira Ajisaka | Akira Ajisaka |
| [HADOOP-14287](https://issues.apache.org/jira/browse/HADOOP-14287) | Compiling trunk with -DskipShade fails |  Major | build | Arpit Agarwal | Arun Suresh |
| [YARN-6368](https://issues.apache.org/jira/browse/YARN-6368) | Decommissioning an NM results in a -1 exit code |  Minor | . | Miklos Szegedi | Miklos Szegedi |
| [HDFS-11633](https://issues.apache.org/jira/browse/HDFS-11633) | FSImage failover disables all erasure coding policies |  Critical | erasure-coding, namenode | Wei-Chiu Chuang | Wei-Chiu Chuang |
| [HADOOP-14066](https://issues.apache.org/jira/browse/HADOOP-14066) | VersionInfo should be marked as public API |  Critical | common | Thejas M Nair | Akira Ajisaka |
| [YARN-6343](https://issues.apache.org/jira/browse/YARN-6343) | Docker docs MR example is broken |  Major | nodemanager | Daniel Templeton | Prashant Jha |
| [HADOOP-14293](https://issues.apache.org/jira/browse/HADOOP-14293) | Initialize FakeTimer with a less trivial value |  Major | test | Andrew Wang | Andrew Wang |
| [HADOOP-13545](https://issues.apache.org/jira/browse/HADOOP-13545) | Upgrade HSQLDB to 2.3.4 |  Minor | build | Giovanni Matteo Fumarola | Giovanni Matteo Fumarola |
| [HDFS-11637](https://issues.apache.org/jira/browse/HDFS-11637) | Fix javac warning caused by the deprecated key used in TestDFSClientRetries#testFailuresArePerOperation |  Minor | . | Yiqun Lin | Yiqun Lin |
| [YARN-6461](https://issues.apache.org/jira/browse/YARN-6461) | TestRMAdminCLI has very low test timeouts |  Major | test | Jason Lowe | Eric Badger |
| [YARN-6463](https://issues.apache.org/jira/browse/YARN-6463) | correct spelling mistake in FileSystemRMStateStore |  Trivial | . | Yeliang Cang | Yeliang Cang |
| [YARN-6439](https://issues.apache.org/jira/browse/YARN-6439) | Fix ReservationSystem creation of default ReservationQueue |  Major | . | Carlo Curino | Carlo Curino |
| [HDFS-11630](https://issues.apache.org/jira/browse/HDFS-11630) | TestThrottledAsyncCheckerTimeout fails intermittently in Jenkins builds |  Major | hdfs | Hanisha Koneru | Hanisha Koneru |
| [HDFS-11163](https://issues.apache.org/jira/browse/HDFS-11163) | Mover should move the file blocks to default storage once policy is unset |  Major | balancer & mover | Surendra Singh Lilhore | Surendra Singh Lilhore |
| [YARN-6421](https://issues.apache.org/jira/browse/YARN-6421) | Upgrade frontend-maven-plugin to 1.1 to fix new YARN UI build error in ppc64le |  Major | yarn-ui-v2 | Sonia Garudi | Sonia Garudi |
| [YARN-6450](https://issues.apache.org/jira/browse/YARN-6450) | TestContainerManagerWithLCE requires override for each new test added to ContainerManagerTest |  Major | test | Jason Lowe | Jason Lowe |
| [YARN-3760](https://issues.apache.org/jira/browse/YARN-3760) | FSDataOutputStream leak in AggregatedLogFormat.LogWriter.close() |  Critical | nodemanager | Daryn Sharp | Haibo Chen |
| [YARN-6216](https://issues.apache.org/jira/browse/YARN-6216) | Unify Container Resizing code paths with Container Updates making it scheduler agnostic |  Major | capacity scheduler, fairscheduler, resourcemanager | Arun Suresh | Arun Suresh |
| [YARN-5994](https://issues.apache.org/jira/browse/YARN-5994) | TestCapacityScheduler.testAMLimitUsage fails intermittently |  Major | . | Eric Badger | Eric Badger |
| [YARN-6433](https://issues.apache.org/jira/browse/YARN-6433) | Only accessible cgroup mount directories should be selected for a controller |  Major | nodemanager | Miklos Szegedi | Miklos Szegedi |
| [YARN-6480](https://issues.apache.org/jira/browse/YARN-6480) | Timeout is too aggressive for TestAMRestart.testPreemptedAMRestartOnRMRestart |  Major | . | Eric Badger | Eric Badger |
| [HADOOP-14311](https://issues.apache.org/jira/browse/HADOOP-14311) | Add python2.7-dev to Dockerfile |  Major | . | Allen Wittenauer | Allen Wittenauer |
| [MAPREDUCE-6875](https://issues.apache.org/jira/browse/MAPREDUCE-6875) | Rename mapred-site.xml.template to mapred-site.xml |  Minor | build | Allen Wittenauer | Yuanbo Liu |
| [YARN-6304](https://issues.apache.org/jira/browse/YARN-6304) | Skip rm.transitionToActive call to RM if RM is already active. |  Major | resourcemanager | Rohith Sharma K S | Rohith Sharma K S |
| [HDFS-11615](https://issues.apache.org/jira/browse/HDFS-11615) | FSNamesystemLock metrics can be inaccurate due to millisecond precision |  Major | hdfs | Erik Krogen | Erik Krogen |
| [HADOOP-14318](https://issues.apache.org/jira/browse/HADOOP-14318) | Remove non-existent setfattr command option from FileSystemShell.md |  Minor | documentation | Doris Gu | Doris Gu |
| [HADOOP-14315](https://issues.apache.org/jira/browse/HADOOP-14315) | Python example in the rack awareness document doesn\'t work due to bad indentation |  Minor | documentation | Kengo Seki | Kengo Seki |
| [HDFS-11665](https://issues.apache.org/jira/browse/HDFS-11665) | HttpFSServerWebServer$deprecateEnv may leak secret |  Major | httpfs, security | John Zhuge | John Zhuge |
| [HADOOP-14317](https://issues.apache.org/jira/browse/HADOOP-14317) | KMSWebServer$deprecateEnv may leak secret |  Major | kms, security | John Zhuge | John Zhuge |
| [HADOOP-13997](https://issues.apache.org/jira/browse/HADOOP-13997) | Typo in metrics docs |  Trivial | documentation | Daniel Templeton | Ana Krasteva |
| [YARN-6438](https://issues.apache.org/jira/browse/YARN-6438) | Code can be improved in ContainersMonitorImpl.java |  Minor | nodemanager | Miklos Szegedi | Miklos Szegedi |
| [YARN-6365](https://issues.apache.org/jira/browse/YARN-6365) | Get static SLS html resources from classpath |  Blocker | scheduler-load-simulator | Allen Wittenauer | Yufei Gu |
| [YARN-6202](https://issues.apache.org/jira/browse/YARN-6202) | Configuration item Dispatcher.DISPATCHER\_EXIT\_ON\_ERROR\_KEY is disregarded |  Major | nodemanager, resourcemanager | Yufei Gu | Yufei Gu |
| [YARN-6302](https://issues.apache.org/jira/browse/YARN-6302) | Fail the node if Linux Container Executor is not configured properly |  Minor | . | Miklos Szegedi | Miklos Szegedi |
| [HDFS-11671](https://issues.apache.org/jira/browse/HDFS-11671) | TestReconstructStripedBlocks#test2RecoveryTasksForSameBlockGroup fails |  Major | erasure-coding, test | Andrew Wang | Andrew Wang |
| [HDFS-11660](https://issues.apache.org/jira/browse/HDFS-11660) | TestFsDatasetCache#testPageRounder fails intermittently with AssertionError |  Major | test | Andrew Wang | Andrew Wang |
| [YARN-6453](https://issues.apache.org/jira/browse/YARN-6453) | fairscheduler-statedump.log gets generated regardless of service |  Blocker | fairscheduler, scheduler | Allen Wittenauer | Yufei Gu |
| [YARN-6363](https://issues.apache.org/jira/browse/YARN-6363) | Extending SLS: Synthetic Load Generator |  Major | . | Carlo Curino | Carlo Curino |
| [YARN-6153](https://issues.apache.org/jira/browse/YARN-6153) | keepContainer does not work when AM retry window is set |  Major | resourcemanager | kyungwan nam | kyungwan nam |
| [HDFS-11689](https://issues.apache.org/jira/browse/HDFS-11689) | New exception thrown by DFSClient#isHDFSEncryptionEnabled broke hacky hive code |  Major | . | Yongjun Zhang | Yongjun Zhang |
| [YARN-5889](https://issues.apache.org/jira/browse/YARN-5889) | Improve and refactor user-limit calculation in capacity scheduler |  Major | capacity scheduler | Sunil G | Sunil G |
| [HDFS-11529](https://issues.apache.org/jira/browse/HDFS-11529) | Add libHDFS API to return last exception |  Critical | libhdfs | Sailesh Mukil | Sailesh Mukil |
| [YARN-6500](https://issues.apache.org/jira/browse/YARN-6500) | Do not mount inaccessible cgroups directories in CgroupsLCEResourcesHandler |  Major | nodemanager | Miklos Szegedi | Miklos Szegedi |
| [HDFS-11691](https://issues.apache.org/jira/browse/HDFS-11691) | Add a proper scheme to the datanode links in NN web UI |  Major | . | Kihwal Lee | Kihwal Lee |
| [HADOOP-14207](https://issues.apache.org/jira/browse/HADOOP-14207) | "dfsadmin -refreshCallQueue" fails with DecayRpcScheduler |  Blocker | rpc-server | Surendra Singh Lilhore | Surendra Singh Lilhore |
| [HADOOP-14341](https://issues.apache.org/jira/browse/HADOOP-14341) | Support multi-line value for ssl.server.exclude.cipher.list |  Major | . | John Zhuge | John Zhuge |
| [YARN-5617](https://issues.apache.org/jira/browse/YARN-5617) | AMs only intended to run one attempt can be run more than once |  Major | resourcemanager | Jason Lowe | Jason Lowe |
| [YARN-6510](https://issues.apache.org/jira/browse/YARN-6510) | Fix profs stat file warning caused by process names that includes parenthesis |  Major | . | Wilfred Spiegelenburg | Wilfred Spiegelenburg |
| [HADOOP-14351](https://issues.apache.org/jira/browse/HADOOP-14351) | Azure: RemoteWasbAuthorizerImpl and RemoteSASKeyGeneratorImpl should not use Kerberos interactive user cache |  Major | fs/azure | Santhosh G Nayak | Santhosh G Nayak |
| [MAPREDUCE-6881](https://issues.apache.org/jira/browse/MAPREDUCE-6881) | Fix warnings from Spotbugs in hadoop-mapreduce |  Major | . | Weiwei Yang | Weiwei Yang |
| [HDFS-11709](https://issues.apache.org/jira/browse/HDFS-11709) | StandbyCheckpointer should handle an non-existing legacyOivImageDir gracefully |  Critical | ha, namenode | Zhe Zhang | Erik Krogen |
| [YARN-6534](https://issues.apache.org/jira/browse/YARN-6534) | ResourceManager failed due to TimelineClient try to init SSLFactory even https is not enabled |  Blocker | . | Junping Du | Rohith Sharma K S |
| [HADOOP-14354](https://issues.apache.org/jira/browse/HADOOP-14354) | SysInfoWindows is not thread safe |  Major | . | Inigo Goiri | Inigo Goiri |
| [YARN-5894](https://issues.apache.org/jira/browse/YARN-5894) | fixed license warning caused by de.ruedigermoeller:fst:jar:2.24 |  Blocker | yarn | Haibo Chen | Haibo Chen |
| [YARN-6472](https://issues.apache.org/jira/browse/YARN-6472) | Improve Java sandbox regex |  Major | . | Miklos Szegedi | Greg Phillips |
| [HADOOP-14320](https://issues.apache.org/jira/browse/HADOOP-14320) | TestIPC.testIpcWithReaderQueuing fails intermittently |  Major | . | Eric Badger | Eric Badger |
| [YARN-6536](https://issues.apache.org/jira/browse/YARN-6536) | TestAMRMClient.testAMRMClientWithSaslEncryption fails intermittently |  Major | . | Eric Badger | Jason Lowe |
| [HDFS-11718](https://issues.apache.org/jira/browse/HDFS-11718) | DFSStripedOutputStream hsync/hflush should not throw UnsupportedOperationException |  Blocker | erasure-coding | Manoj Govindassamy | Manoj Govindassamy |
| [HADOOP-14363](https://issues.apache.org/jira/browse/HADOOP-14363) | Inconsistent default block location in FileSystem javadoc |  Trivial | fs | Mingliang Liu | Chen Liang |
| [HADOOP-13901](https://issues.apache.org/jira/browse/HADOOP-13901) | Fix ASF License warnings |  Major | build | Akira Ajisaka | Akira Ajisaka |
| [YARN-6517](https://issues.apache.org/jira/browse/YARN-6517) | Fix warnings from Spotbugs in hadoop-yarn-common |  Major | . | Weiwei Yang | Weiwei Yang |
| [YARN-6518](https://issues.apache.org/jira/browse/YARN-6518) | Fix warnings from Spotbugs in hadoop-yarn-server-timelineservice |  Major | . | Weiwei Yang | Weiwei Yang |
| [YARN-6520](https://issues.apache.org/jira/browse/YARN-6520) | Fix warnings from Spotbugs in hadoop-yarn-client |  Major | . | Weiwei Yang | Weiwei Yang |
| [HDFS-11609](https://issues.apache.org/jira/browse/HDFS-11609) | Some blocks can be permanently lost if nodes are decommissioned while dead |  Blocker | namenode | Kihwal Lee | Kihwal Lee |
| [HDFS-11724](https://issues.apache.org/jira/browse/HDFS-11724) | libhdfs compilation is broken on OS X |  Blocker | libhdfs | Allen Wittenauer | John Zhuge |
| [HDFS-8498](https://issues.apache.org/jira/browse/HDFS-8498) | Blocks can be committed with wrong size |  Critical | hdfs-client | Daryn Sharp | Jing Zhao |
| [HDFS-11714](https://issues.apache.org/jira/browse/HDFS-11714) | Newly added NN storage directory won\'t get initialized and cause space exhaustion |  Critical | . | Kihwal Lee | Kihwal Lee |
| [HADOOP-14366](https://issues.apache.org/jira/browse/HADOOP-14366) | maven upgrade broke start-build-env.sh |  Blocker | build | Allen Wittenauer | Akira Ajisaka |
| [HDFS-11593](https://issues.apache.org/jira/browse/HDFS-11593) | Change SimpleHttpProxyHandler#exceptionCaught log level from info to debug |  Minor | datanode | Xiaoyu Yao | Xiaobing Zhou |
| [HDFS-11710](https://issues.apache.org/jira/browse/HDFS-11710) | hadoop-hdfs-native-client build fails in trunk in Windows after HDFS-11529 |  Blocker | native | Vinayakumar B | Sailesh Mukil |
| [HADOOP-14371](https://issues.apache.org/jira/browse/HADOOP-14371) | License error in TestLoadBalancingKMSClientProvider.java |  Major | . | hu xiaodong | hu xiaodong |
| [HADOOP-14369](https://issues.apache.org/jira/browse/HADOOP-14369) | NetworkTopology calls expensive toString() when logging |  Major | . | Inigo Goiri | Inigo Goiri |
| [HADOOP-14281](https://issues.apache.org/jira/browse/HADOOP-14281) | Fix TestKafkaMetrics#testPutMetrics |  Major | metrics | Akira Ajisaka | Alison Yu |
| [YARN-6519](https://issues.apache.org/jira/browse/YARN-6519) | Fix warnings from Spotbugs in hadoop-yarn-server-resourcemanager |  Major | resourcemanager | Weiwei Yang | Weiwei Yang |
| [YARN-6481](https://issues.apache.org/jira/browse/YARN-6481) | Yarn top shows negative container number in FS |  Major | yarn | Yufei Gu | Tao Jie |
| [HADOOP-14306](https://issues.apache.org/jira/browse/HADOOP-14306) | TestLocalFileSystem tests have very low timeouts |  Major | . | Eric Badger | Eric Badger |
| [HADOOP-14372](https://issues.apache.org/jira/browse/HADOOP-14372) | TestSymlinkLocalFS timeouts are too low |  Major | . | Eric Badger | Eric Badger |
| [HDFS-11739](https://issues.apache.org/jira/browse/HDFS-11739) | Fix regression in tests caused by YARN-679 |  Major | test | Steve Loughran | Steve Loughran |


### TESTS:

| JIRA | Summary | Priority | Component | Reporter | Contributor |
|:---- |:---- | :--- |:---- |:---- |:---- |
| [HDFS-11570](https://issues.apache.org/jira/browse/HDFS-11570) | Unit test for NameNodeStatusMXBean |  Major | hdfs, test | Hanisha Koneru | Hanisha Koneru |
| [HADOOP-14218](https://issues.apache.org/jira/browse/HADOOP-14218) | Replace assertThat with assertTrue in MetricsAsserts |  Minor | . | Akira Ajisaka | Akira Ajisaka |


### SUB-TASKS:

| JIRA | Summary | Priority | Component | Reporter | Contributor |
|:---- |:---- | :--- |:---- |:---- |:---- |
| [HDFS-11296](https://issues.apache.org/jira/browse/HDFS-11296) | Maintenance state expiry should be an epoch time and not jvm monotonic |  Major | . | Manoj Govindassamy | Manoj Govindassamy |
| [HDFS-11121](https://issues.apache.org/jira/browse/HDFS-11121) | Add assertions to BlockInfo#addStorage to protect from breaking reportedBlock-blockGroup mapping |  Critical | erasure-coding | Takanobu Asanuma | Takanobu Asanuma |
| [YARN-6099](https://issues.apache.org/jira/browse/YARN-6099) | Improve webservice to list aggregated log files |  Major | . | Xuan Gong | Xuan Gong |
| [HDFS-11124](https://issues.apache.org/jira/browse/HDFS-11124) | Report blockIds of internal blocks for EC files in Fsck |  Major | erasure-coding | Takanobu Asanuma | Takanobu Asanuma |
| [YARN-5830](https://issues.apache.org/jira/browse/YARN-5830) | FairScheduler: Avoid preempting AM containers |  Major | fairscheduler | Karthik Kambatla | Yufei Gu |
| [YARN-3637](https://issues.apache.org/jira/browse/YARN-3637) | Handle localization sym-linking correctly at the YARN level |  Major | . | Chris Trezzo | Chris Trezzo |
| [YARN-6126](https://issues.apache.org/jira/browse/YARN-6126) | Obtaining app logs for Running application fails with "Unable to parse json from webservice. Error:" |  Major | . | Sumana Sathish | Xuan Gong |
| [YARN-5866](https://issues.apache.org/jira/browse/YARN-5866) | Fix few issues reported by jshint in new YARN UI |  Major | yarn-ui-v2 | Akhil PB | Akhil PB |
| [YARN-6100](https://issues.apache.org/jira/browse/YARN-6100) | improve YARN webservice to output aggregated container logs |  Major | . | Xuan Gong | Xuan Gong |
| [YARN-6108](https://issues.apache.org/jira/browse/YARN-6108) | Improve AHS webservice to accept NM address as a parameter to get container logs |  Major | . | Xuan Gong | Xuan Gong |
| [YARN-5917](https://issues.apache.org/jira/browse/YARN-5917) | Make navigation link active when selecting sub tabs in "Applications" and "Nodes" page for new UI |  Minor | yarn-ui-v2 | Kai Sasaki | Kai Sasaki |
| [YARN-5258](https://issues.apache.org/jira/browse/YARN-5258) | Document Use of Docker with LinuxContainerExecutor |  Critical | documentation | Daniel Templeton | Daniel Templeton |
| [HADOOP-14065](https://issues.apache.org/jira/browse/HADOOP-14065) | AliyunOSS: oss directory filestatus should use meta time |  Major | fs/oss | Fei Hui | Fei Hui |
| [HADOOP-14032](https://issues.apache.org/jira/browse/HADOOP-14032) | Reduce fair call queue priority inversion |  Major | ipc | Daryn Sharp | Daryn Sharp |
| [HADOOP-14034](https://issues.apache.org/jira/browse/HADOOP-14034) | Allow ipc layer exceptions to selectively close connections |  Major | ipc | Daryn Sharp | Daryn Sharp |
| [HADOOP-14033](https://issues.apache.org/jira/browse/HADOOP-14033) | Reduce fair call queue lock contention |  Major | ipc | Daryn Sharp | Daryn Sharp |
| [HADOOP-13768](https://issues.apache.org/jira/browse/HADOOP-13768) | AliyunOSS: handle the failure in the batch delete operation \`deleteDirs\`. |  Major | fs | Genmao Yu | Genmao Yu |
| [YARN-6170](https://issues.apache.org/jira/browse/YARN-6170) | TimelineReaderServer should wait to join with HttpServer2 |  Minor | timelinereader | Sangjin Lee | Sangjin Lee |
| [HADOOP-13075](https://issues.apache.org/jira/browse/HADOOP-13075) | Add support for SSE-KMS and SSE-C in s3a filesystem |  Major | fs/s3 | Andrew Olson | Steve Moist |
| [HADOOP-14069](https://issues.apache.org/jira/browse/HADOOP-14069) | AliyunOSS: listStatus returns wrong file info |  Major | fs/oss | Fei Hui | Fei Hui |
| [HADOOP-13769](https://issues.apache.org/jira/browse/HADOOP-13769) | AliyunOSS: update oss sdk version |  Major | fs, fs/oss | Genmao Yu | Genmao Yu |
| [YARN-6113](https://issues.apache.org/jira/browse/YARN-6113) | re-direct NM Web Service to get container logs for finished applications |  Major | . | Xuan Gong | Xuan Gong |
| [YARN-5966](https://issues.apache.org/jira/browse/YARN-5966) | AMRMClient changes to support ExecutionType update |  Major | . | Arun Suresh | Arun Suresh |
| [YARN-5912](https://issues.apache.org/jira/browse/YARN-5912) | Fix breadcrumb issues for various pages in new YARN UI |  Minor | yarn-ui-v2 | Akhil PB | Akhil PB |
| [HADOOP-14072](https://issues.apache.org/jira/browse/HADOOP-14072) | AliyunOSS: Failed to read from stream when seek beyond the download size |  Major | fs/oss | Genmao Yu | Genmao Yu |
| [YARN-6156](https://issues.apache.org/jira/browse/YARN-6156) | AM blacklisting to consider node label partition |  Major | . | Bibin A Chundatt | Bibin A Chundatt |
| [YARN-6183](https://issues.apache.org/jira/browse/YARN-6183) | Few missing informations in Application and Application Attempt pages for new YARN UI. |  Major | . | Akhil PB | Akhil PB |
| [HDFS-11265](https://issues.apache.org/jira/browse/HDFS-11265) | Extend visualization for Maintenance Mode under Datanode tab in the NameNode UI |  Major | datanode, namenode | Manoj Govindassamy | Elek, Marton |
| [YARN-6163](https://issues.apache.org/jira/browse/YARN-6163) | FS Preemption is a trickle for severely starved applications |  Major | fairscheduler | Karthik Kambatla | Karthik Kambatla |
| [YARN-5798](https://issues.apache.org/jira/browse/YARN-5798) | Set UncaughtExceptionHandler for all FairScheduler threads |  Major | fairscheduler | Karthik Kambatla | Yufei Gu |
| [YARN-4675](https://issues.apache.org/jira/browse/YARN-4675) | Reorganize TimelineClient and TimelineClientImpl into separate classes for ATSv1.x and ATSv2 |  Major | timelineserver | Naganarasimha G R | Naganarasimha G R |
| [HADOOP-14019](https://issues.apache.org/jira/browse/HADOOP-14019) | fix some typos in the s3a docs |  Minor | documentation, fs/s3 | Steve Loughran | Steve Loughran |
| [HADOOP-14040](https://issues.apache.org/jira/browse/HADOOP-14040) | Use shaded aws-sdk uber-JAR 1.11.86 |  Major | build, fs/s3 | Steve Loughran | Steve Loughran |
| [YARN-6193](https://issues.apache.org/jira/browse/YARN-6193) | FairScheduler might not trigger preemption when using DRF |  Major | fairscheduler | Karthik Kambatla | Karthik Kambatla |
| [HADOOP-14081](https://issues.apache.org/jira/browse/HADOOP-14081) | S3A: Consider avoiding array copy in S3ABlockOutputStream (ByteArrayBlock) |  Minor | fs/s3 | Rajesh Balamohan | Rajesh Balamohan |
| [YARN-6159](https://issues.apache.org/jira/browse/YARN-6159) | Documentation changes for TimelineV2Client |  Minor | documentation | Varun Saxena | Naganarasimha G R |
| [HDFS-11430](https://issues.apache.org/jira/browse/HDFS-11430) | Separate class InnerNode from class NetworkTopology and make it extendable |  Major | namenode | Chen Liang | Tsz Wo Nicholas Sze |
| [YARN-6184](https://issues.apache.org/jira/browse/YARN-6184) | Introduce loading icon in each page of new YARN UI |  Major | . | Akhil PB | Akhil PB |
| [HADOOP-14099](https://issues.apache.org/jira/browse/HADOOP-14099) | Split S3 testing documentation out into its own file |  Minor | documentation, fs/s3 | Steve Loughran | Steve Loughran |
| [HDFS-11411](https://issues.apache.org/jira/browse/HDFS-11411) | Avoid OutOfMemoryError in TestMaintenanceState test runs |  Major | datanode, namenode | Manoj Govindassamy | Manoj Govindassamy |
| [HADOOP-14102](https://issues.apache.org/jira/browse/HADOOP-14102) | Relax error message assertion in S3A test ITestS3AEncryptionSSEC |  Minor | fs/s3 | Mingliang Liu | Mingliang Liu |
| [HDFS-4025](https://issues.apache.org/jira/browse/HDFS-4025) | QJM: Sychronize past log segments to JNs that missed them |  Major | ha | Todd Lipcon | Hanisha Koneru |
| [YARN-6069](https://issues.apache.org/jira/browse/YARN-6069) | CORS support in timeline v2 |  Major | timelinereader | Sreenath Somarajapuram | Rohith Sharma K S |
| [YARN-6143](https://issues.apache.org/jira/browse/YARN-6143) | Fix incompatible issue caused by YARN-3583 |  Blocker | rolling upgrade | Wangda Tan | Sunil G |
| [HADOOP-14113](https://issues.apache.org/jira/browse/HADOOP-14113) | review ADL Docs |  Minor | documentation, fs/adl | Steve Loughran | Steve Loughran |
| [YARN-4779](https://issues.apache.org/jira/browse/YARN-4779) | Fix AM container allocation logic in SLS |  Major | scheduler-load-simulator | Wangda Tan | Wangda Tan |
| [YARN-6228](https://issues.apache.org/jira/browse/YARN-6228) | EntityGroupFSTimelineStore should allow configurable cache stores. |  Major | timelineserver | Li Lu | Li Lu |
| [YARN-6215](https://issues.apache.org/jira/browse/YARN-6215) | FairScheduler preemption and update should not run concurrently |  Major | fairscheduler, test | Sunil G | Tao Jie |
| [YARN-6123](https://issues.apache.org/jira/browse/YARN-6123) | [YARN-5864] Add a test to make sure queues of orderingPolicy will be updated when childQueues is added or removed. |  Major | . | Wangda Tan | Wangda Tan |
| [HADOOP-14118](https://issues.apache.org/jira/browse/HADOOP-14118) | move jets3t into a dependency on hadoop-aws JAR |  Major | build, fs/s3 | Steve Loughran | Akira Ajisaka |
| [YARN-5335](https://issues.apache.org/jira/browse/YARN-5335) | Use em-table in app/nodes pages for new YARN UI |  Major | . | Sunil G | Sunil G |
| [HDFS-11450](https://issues.apache.org/jira/browse/HDFS-11450) | HDFS specific network topology classes with storage type info included |  Major | namenode | Chen Liang | Chen Liang |
| [HDFS-11412](https://issues.apache.org/jira/browse/HDFS-11412) | Maintenance minimum replication config value allowable range should be [0, DefaultReplication] |  Major | datanode, namenode | Manoj Govindassamy | Manoj Govindassamy |
| [HADOOP-14057](https://issues.apache.org/jira/browse/HADOOP-14057) | Fix package.html to compile with Java 9 |  Major | documentation | Akira Ajisaka | Akira Ajisaka |
| [HDFS-8112](https://issues.apache.org/jira/browse/HDFS-8112) | Relax permission checking for EC related operations |  Blocker | erasure-coding | Kai Zheng | Andrew Wang |
| [HADOOP-14056](https://issues.apache.org/jira/browse/HADOOP-14056) | Update maven-javadoc-plugin to 2.10.4 |  Major | build | Akira Ajisaka | Akira Ajisaka |
| [YARN-6275](https://issues.apache.org/jira/browse/YARN-6275) | Fail to show real-time tracking charts in SLS |  Major | scheduler-load-simulator | Yufei Gu | Yufei Gu |
| [HDFS-10983](https://issues.apache.org/jira/browse/HDFS-10983) | OIV tool should make an EC file explicit |  Major | . | Wei-Chiu Chuang | Manoj Govindassamy |
| [YARN-5669](https://issues.apache.org/jira/browse/YARN-5669) | Add support for Docker pull |  Major | yarn | Zhankun Tang | luhuichun |
| [YARN-1047](https://issues.apache.org/jira/browse/YARN-1047) | Expose # of pre-emptions as a queue counter |  Major | fairscheduler | Philip Zeyliger | Karthik Kambatla |
| [HADOOP-14123](https://issues.apache.org/jira/browse/HADOOP-14123) | Remove misplaced ADL service provider config file for FileSystem |  Minor | fs/adl | John Zhuge | John Zhuge |
| [HADOOP-14153](https://issues.apache.org/jira/browse/HADOOP-14153) | ADL module has messed doc structure |  Major | fs/adl | Mingliang Liu | Mingliang Liu |
| [YARN-6196](https://issues.apache.org/jira/browse/YARN-6196) | Improve Resource Donut chart with better label in Node page of new YARN UI |  Major | . | Akhil PB | Akhil PB |
| [HADOOP-14111](https://issues.apache.org/jira/browse/HADOOP-14111) | cut some obsolete, ignored s3 tests in TestS3Credentials |  Minor | fs/s3, test | Steve Loughran | Yuanbo Liu |
| [HADOOP-14173](https://issues.apache.org/jira/browse/HADOOP-14173) | Remove unused AdlConfKeys#ADL\_EVENTS\_TRACKING\_SOURCE |  Trivial | fs/adl | John Zhuge | John Zhuge |
| [HDFS-11482](https://issues.apache.org/jira/browse/HDFS-11482) | Add storage type demand to into DFSNetworkTopology#chooseRandom |  Major | namenode | Chen Liang | Chen Liang |
| [YARN-5496](https://issues.apache.org/jira/browse/YARN-5496) | Make Node Heatmap Chart categories clickable in new YARN UI |  Major | . | Yesha Vora | Gergely Novák |
| [YARN-6314](https://issues.apache.org/jira/browse/YARN-6314) | Potential infinite redirection on YARN log redirection web service |  Major | . | Xuan Gong | Xuan Gong |
| [YARN-6313](https://issues.apache.org/jira/browse/YARN-6313) | yarn logs cli should provide logs for a completed container even when application is still running |  Major | . | Siddharth Seth | Xuan Gong |
| [HDFS-11514](https://issues.apache.org/jira/browse/HDFS-11514) | DFSTopologyNodeImpl#chooseRandom optimizations |  Major | namenode | Chen Liang | Chen Liang |
| [HDFS-10530](https://issues.apache.org/jira/browse/HDFS-10530) | BlockManager reconstruction work scheduling should correctly adhere to EC block placement policy |  Major | namenode | Rui Gao | Manoj Govindassamy |
| [HADOOP-14192](https://issues.apache.org/jira/browse/HADOOP-14192) | Aliyun OSS FileSystem contract test should implement getTestBaseDir() |  Major | fs/oss | Mingliang Liu | Mingliang Liu |
| [YARN-6362](https://issues.apache.org/jira/browse/YARN-6362) | Use frontend-maven-plugin 0.0.22 version for new yarn ui |  Major | . | Kai Sasaki | Kai Sasaki |
| [HDFS-11358](https://issues.apache.org/jira/browse/HDFS-11358) | DiskBalancer: Report command supports reading nodes from host file |  Major | diskbalancer | Yiqun Lin | Yiqun Lin |
| [YARN-6367](https://issues.apache.org/jira/browse/YARN-6367) | YARN logs CLI needs alway check containerLogsInfo/containerLogInfo before parse the JSON object from NMWebService |  Major | . | Siddharth Seth | Xuan Gong |
| [YARN-6326](https://issues.apache.org/jira/browse/YARN-6326) | Shouldn\'t use AppAttemptIds to fetch applications while AM Simulator tracks app in SLS |  Major | scheduler-load-simulator | Yufei Gu | Yufei Gu |
| [HADOOP-14120](https://issues.apache.org/jira/browse/HADOOP-14120) | needless S3AFileSystem.setOptionalPutRequestParameters in S3ABlockOutputStream putObject() |  Minor | fs/s3 | Steve Loughran | Yuanbo Liu |
| [HADOOP-14135](https://issues.apache.org/jira/browse/HADOOP-14135) | Remove URI parameter in AWSCredentialProvider constructors |  Major | fs/s3 | Mingliang Liu | Mingliang Liu |
| [HADOOP-14196](https://issues.apache.org/jira/browse/HADOOP-14196) | Azure Data Lake doc is missing required config entry |  Major | fs/adl | Atul Sikaria | Atul Sikaria |
| [HADOOP-14197](https://issues.apache.org/jira/browse/HADOOP-14197) | Fix ADLS doc for credential provider |  Major | documentation, fs/adl | John Zhuge | John Zhuge |
| [HADOOP-13715](https://issues.apache.org/jira/browse/HADOOP-13715) | Add isErasureCoded() API to FileStatus class |  Blocker | fs | Wei-Chiu Chuang | Manoj Govindassamy |
| [HADOOP-14230](https://issues.apache.org/jira/browse/HADOOP-14230) | TestAdlFileSystemContractLive fails to clean up |  Minor | fs/adl, test | John Zhuge | John Zhuge |
| [HADOOP-14038](https://issues.apache.org/jira/browse/HADOOP-14038) | Rename ADLS credential properties |  Minor | fs/adl | John Zhuge | John Zhuge |
| [HDFS-11577](https://issues.apache.org/jira/browse/HDFS-11577) | Combine the old and the new chooseRandom for better performance |  Major | namenode | Chen Liang | Chen Liang |
| [YARN-6357](https://issues.apache.org/jira/browse/YARN-6357) | Implement putEntitiesAsync API in TimelineCollector |  Major | ATSv2, timelineserver | Joep Rottinghuis | Haibo Chen |
| [HDFS-10971](https://issues.apache.org/jira/browse/HDFS-10971) | Distcp should not copy replication factor if source file is erasure coded |  Blocker | distcp | Wei-Chiu Chuang | Manoj Govindassamy |
| [HDFS-11541](https://issues.apache.org/jira/browse/HDFS-11541) | Call RawErasureEncoder and RawErasureDecoder release() methods |  Major | erasure-coding | László Bence Nagy | SammiChen |
| [YARN-5654](https://issues.apache.org/jira/browse/YARN-5654) | Not be able to run SLS with FairScheduler |  Major | . | Wangda Tan | Yufei Gu |
| [YARN-6342](https://issues.apache.org/jira/browse/YARN-6342) | Make TimelineV2Client\'s drain timeout after stop configurable |  Major | . | Jian He | Haibo Chen |
| [YARN-6376](https://issues.apache.org/jira/browse/YARN-6376) | Exceptions caused by synchronous putEntities requests can be swallowed |  Critical | ATSv2 | Haibo Chen | Haibo Chen |
| [YARN-6414](https://issues.apache.org/jira/browse/YARN-6414) | ATSv2 HBase related tests fail due to guava version upgrade |  Major | timelineserver | Sonia Garudi | Haibo Chen |
| [YARN-6377](https://issues.apache.org/jira/browse/YARN-6377) | NMTimelinePublisher#serviceStop does not stop timeline clients |  Major | yarn | Haibo Chen | Haibo Chen |
| [YARN-6109](https://issues.apache.org/jira/browse/YARN-6109) | Add an ability to convert ChildQueue to ParentQueue |  Major | capacity scheduler | Xuan Gong | Xuan Gong |
| [YARN-6424](https://issues.apache.org/jira/browse/YARN-6424) | TimelineCollector is not stopped when an app finishes in RM |  Critical | timelineserver | Varun Saxena | Varun Saxena |
| [YARN-6258](https://issues.apache.org/jira/browse/YARN-6258) | localBaseAddress for CORS proxy configuration is not working when suffixed with forward slash in new YARN UI. |  Major | . | Gergely Novák | Gergely Novák |
| [HADOOP-14290](https://issues.apache.org/jira/browse/HADOOP-14290) | Update SLF4J from 1.7.10 to 1.7.25 |  Major | . | Akira Ajisaka | Akira Ajisaka |
| [YARN-5153](https://issues.apache.org/jira/browse/YARN-5153) | Add a toggle button to switch between timeline view / table view for containers and application-attempts in new YARN UI |  Major | webapp | Wangda Tan | Akhil PB |
| [YARN-6372](https://issues.apache.org/jira/browse/YARN-6372) | Add default value for NM disk validator |  Major | nodemanager | Yufei Gu | Yufei Gu |
| [HDFS-10996](https://issues.apache.org/jira/browse/HDFS-10996) | Ability to specify per-file EC policy at create time |  Major | erasure-coding | Andrew Wang | SammiChen |
| [HADOOP-14255](https://issues.apache.org/jira/browse/HADOOP-14255) | S3A to delete unnecessary fake directory objects in mkdirs() |  Major | fs/s3 | Mingliang Liu | Mingliang Liu |
| [YARN-6432](https://issues.apache.org/jira/browse/YARN-6432) | FairScheduler: Reserve preempted resources for corresponding applications |  Major | . | Miklos Szegedi | Miklos Szegedi |
| [HADOOP-14321](https://issues.apache.org/jira/browse/HADOOP-14321) | Explicitly exclude S3A root dir ITests from parallel runs |  Minor | fs/s3, test | Steve Loughran | Steve Loughran |
| [HADOOP-14241](https://issues.apache.org/jira/browse/HADOOP-14241) | Add ADLS sensitive config keys to default list |  Minor | fs, fs/adl, security | John Zhuge | John Zhuge |
| [YARN-6402](https://issues.apache.org/jira/browse/YARN-6402) | Move \'Long Running Services\' to an independent tab at top level for new Yarn UI |  Major | webapp | Sunil G | Akhil PB |
| [HADOOP-14324](https://issues.apache.org/jira/browse/HADOOP-14324) | Refine S3 server-side-encryption key as encryption secret; improve error reporting and diagnostics |  Blocker | fs/s3 | Steve Loughran | Steve Loughran |
| [HDFS-11604](https://issues.apache.org/jira/browse/HDFS-11604) | Define and parse erasure code policies |  Major | erasure-coding | Kai Zheng | Lin Zeng |
| [HADOOP-14261](https://issues.apache.org/jira/browse/HADOOP-14261) | Some refactoring work for erasure coding raw coder |  Major | . | Kai Zheng | Lin Zeng |
| [YARN-6291](https://issues.apache.org/jira/browse/YARN-6291) | Introduce query parameters (sort, filter, etc.) for tables to keep state on refresh/navigation in new YARN UI |  Major | . | Gergely Novák | Gergely Novák |
| [YARN-6423](https://issues.apache.org/jira/browse/YARN-6423) | Queue metrics doesn\'t work for Fair Scheduler in SLS |  Major | scheduler-load-simulator | Yufei Gu | Yufei Gu |
| [HADOOP-14349](https://issues.apache.org/jira/browse/HADOOP-14349) | Rename ADLS CONTRACT\_ENABLE\_KEY |  Minor | fs/adl | Mingliang Liu | Mingliang Liu |
| [HDFS-6708](https://issues.apache.org/jira/browse/HDFS-6708) | StorageType should be encoded in the block token |  Major | datanode, namenode | Arpit Agarwal | Ewan Higgs |
| [HDFS-11697](https://issues.apache.org/jira/browse/HDFS-11697) | Add javadoc for storage policy and erasure coding policy |  Minor | documentation | Kai Sasaki | Kai Sasaki |
| [HADOOP-11614](https://issues.apache.org/jira/browse/HADOOP-11614) | Remove httpclient dependency from hadoop-openstack |  Blocker | . | Akira Ajisaka | Akira Ajisaka |
| [YARN-6455](https://issues.apache.org/jira/browse/YARN-6455) | Enhance the timelinewriter.flush() race condition fix |  Major | yarn | Haibo Chen | Haibo Chen |
| [HDFS-11605](https://issues.apache.org/jira/browse/HDFS-11605) | Allow user to customize new erasure code policies |  Major | erasure-coding | Kai Zheng | Huafeng Wang |
| [YARN-4359](https://issues.apache.org/jira/browse/YARN-4359) | Update LowCost agents logic to take advantage of YARN-4358 |  Major | capacityscheduler, fairscheduler, resourcemanager | Carlo Curino | Ishai Menache |
| [YARN-6542](https://issues.apache.org/jira/browse/YARN-6542) | Fix the logger in TestAlignedPlanner and TestGreedyReservationAgent |  Major | reservation system | Subru Krishnan | Subru Krishnan |
| [YARN-5331](https://issues.apache.org/jira/browse/YARN-5331) | Extend RLESparseResourceAllocation with period for supporting recurring reservations in YARN ReservationSystem |  Major | resourcemanager | Subru Krishnan | Sangeetha Abdu Jyothi |


### OTHER:

| JIRA | Summary | Priority | Component | Reporter | Contributor |
|:---- |:---- | :--- |:---- |:---- |:---- |
| [HDFS-11026](https://issues.apache.org/jira/browse/HDFS-11026) | Convert BlockTokenIdentifier to use Protobuf |  Major | hdfs, hdfs-client | Ewan Higgs | Ewan Higgs |
| [HADOOP-14091](https://issues.apache.org/jira/browse/HADOOP-14091) | AbstractFileSystem implementaion for \'wasbs\' scheme |  Major | fs/azure | Varada Hemeswari | Varada Hemeswari |
| [YARN-6274](https://issues.apache.org/jira/browse/YARN-6274) | Documentation refers to incorrect nodemanager health checker interval property |  Trivial | documentation | Charles Zhang | Weiwei Yang |
| [YARN-6411](https://issues.apache.org/jira/browse/YARN-6411) | Clean up the overwrite of createDispatcher() in subclass of MockRM |  Minor | resourcemanager | Yufei Gu | Yufei Gu |
| [HADOOP-14344](https://issues.apache.org/jira/browse/HADOOP-14344) | Revert HADOOP-13606 swift FS to add a service load metadata file |  Major | . | John Zhuge | John Zhuge |
| [HDFS-11717](https://issues.apache.org/jira/browse/HDFS-11717) | Add unit test for HDFS-11709 StandbyCheckpointer should handle non-existing legacyOivImageDir gracefully |  Minor | ha, namenode | Erik Krogen | Erik Krogen |

