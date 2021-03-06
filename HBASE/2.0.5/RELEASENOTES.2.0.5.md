
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
# Apache HBase  2.0.5 Release Notes

These release notes cover new developer and user-facing incompatibilities, important issues, features, and major improvements.


---

* [HBASE-18569](https://issues.apache.org/jira/browse/HBASE-18569) | *Major* | **Add prefetch support for async region locator**

Add prefetch support for async region locator. The default value is 10. Set 'hbase.client.locate.prefetch.limit' in hbase-site.xml if you want to use another value for it.


---

* [HBASE-21712](https://issues.apache.org/jira/browse/HBASE-21712) | *Minor* | **Make submit-patch.py python3 compatible**

Python3 support was added to dev-support/submit-patch.py. To install newly required dependencies run \`pip install -r dev-support/python-requirements.txt\` command.


---

* [HBASE-21732](https://issues.apache.org/jira/browse/HBASE-21732) | *Critical* | **Should call toUpperCase before using Enum.valueOf in some methods for ColumnFamilyDescriptor**

Now all the Enum configs in ColumnFamilyDescriptor can accept lower case config value.


---

* [HBASE-21738](https://issues.apache.org/jira/browse/HBASE-21738) | *Critical* | **Remove all the CSLM#size operation in our memstore because it's an quite time consuming.**

We found the memstore snapshotting would cost much time because of calling the time-consuming ConcurrentSkipListMap#Size, it would make the p999 latency spike happen. So in this issue, we remove all ConcurrentSkipListMap#size in memstore by counting the cellsCount in MemstoreSizeing. As the issue described, the p999 latency spike was mitigated.


---

* [HBASE-21734](https://issues.apache.org/jira/browse/HBASE-21734) | *Major* | **Some optimization in FilterListWithOR**

After HBASE-21620, the filterListWithOR has been a bit slow because we need to merge each sub-filter's RC , while before HBASE-21620, we will skip many RC merging, but the logic was wrong. So here we choose another way to optimaze the performance: removing the KeyValueUtil#toNewKeyCell. 
Anoop Sam John suggested that the KeyValueUtil#toNewKeyCell can save some GC before because if we copy key part of cell into a single byte[], then the block the cell refering won't be refered by the filter list any more, the upper layer can GC the data block quickly. while after HBASE-21620, we will update the prevCellList for every encountered cell now, so the lifecycle of cell in prevCellList for FilterList will be quite shorter. so just use the cell ref for saving cpu.
BTW, we removed all the arrays streams usage in filter list, because it's also quite time-consuming in our test.


---

* [HBASE-21791](https://issues.apache.org/jira/browse/HBASE-21791) | *Blocker* | **Upgrade thrift dependency to 0.12.0**

IMPORTANT: Due to security issues, all users who use hbase thrift should avoid using releases which do not have this fix.

The effect releases are:
2.1.x: 2.1.2 and below
2.0.x: 2.0.4 and below
1.x: 1.4.x and below

If you are using the effect releases above, please consider upgrading to a newer release ASAP.


---

* [HBASE-21684](https://issues.apache.org/jira/browse/HBASE-21684) | *Major* | **Throw DNRIOE when connection or rpc client is closed**

Make StoppedRpcClientException extend DoNotRetryIOException.


---

* [HBASE-21764](https://issues.apache.org/jira/browse/HBASE-21764) | *Major* | **Size of in-memory compaction thread pool should be configurable**

Introduced an new config key in this issue: hbase.regionserver.inmemory.compaction.pool.size. the default value would be 10.  you can configure this to set the pool size of in-memory compaction pool. Note that all memstores in one region server will share the same pool, so if you have many regions in one region server,  you need to set this larger to compact faster for better read performance.


---

* [HBASE-21727](https://issues.apache.org/jira/browse/HBASE-21727) | *Minor* | **Simplify documentation around client timeout**

Deprecated HBaseConfiguration#getInt(Configuration, String, String, int) method and removed it from 3.0.0 version.


---

* [HBASE-21636](https://issues.apache.org/jira/browse/HBASE-21636) | *Major* | **Enhance the shell scan command to support missing scanner specifications like ReadType, IsolationLevel etc.**

Allows shell to set Scan options previously not exposed. See additions as part of the scan help by typing following hbase shell:

hbase\> help 'scan'


---

* [HBASE-22052](https://issues.apache.org/jira/browse/HBASE-22052) | *Major* | **pom cleaning; filter out jersey-core in hadoop2 to match hadoop3 and remove redunant version specifications**

<!-- markdown -->
Fixed awkward dependency issue that prevented site building.

#### note specific to HBase 2.1.4
HBase 2.1.4 shipped with an early version of this fix that incorrectly altered the libraries included in our binary assembly for using Apache Hadoop 2.7 (the current build default Hadoop version for 2.1.z). For folks running out of the box against a Hadoop 2.7 cluster (or folks who skip the installation step of [replacing the bundled Hadoop libraries](http://hbase.apache.org/book.html#hadoop)) this will result in a failure at Region Server startup due to a missing class definition. e.g.:
```
2019-03-27 09:02:05,779 ERROR [main] regionserver.HRegionServer: Failed construction RegionServer
java.lang.NoClassDefFoundError: org/apache/htrace/SamplerBuilder
	at org.apache.hadoop.hdfs.DFSClient.<init>(DFSClient.java:644)
	at org.apache.hadoop.hdfs.DFSClient.<init>(DFSClient.java:628)
	at org.apache.hadoop.hdfs.DistributedFileSystem.initialize(DistributedFileSystem.java:149)
	at org.apache.hadoop.fs.FileSystem.createFileSystem(FileSystem.java:2667)
	at org.apache.hadoop.fs.FileSystem.access$200(FileSystem.java:93)
	at org.apache.hadoop.fs.FileSystem$Cache.getInternal(FileSystem.java:2701)
	at org.apache.hadoop.fs.FileSystem$Cache.get(FileSystem.java:2683)
	at org.apache.hadoop.fs.FileSystem.get(FileSystem.java:372)
	at org.apache.hadoop.fs.FileSystem.get(FileSystem.java:171)
	at org.apache.hadoop.fs.FileSystem.get(FileSystem.java:356)
	at org.apache.hadoop.fs.Path.getFileSystem(Path.java:295)
	at org.apache.hadoop.hbase.util.CommonFSUtils.getRootDir(CommonFSUtils.java:362)
	at org.apache.hadoop.hbase.util.CommonFSUtils.isValidWALRootDir(CommonFSUtils.java:411)
	at org.apache.hadoop.hbase.util.CommonFSUtils.getWALRootDir(CommonFSUtils.java:387)
	at org.apache.hadoop.hbase.regionserver.HRegionServer.initializeFileSystem(HRegionServer.java:704)
	at org.apache.hadoop.hbase.regionserver.HRegionServer.<init>(HRegionServer.java:613)
	at sun.reflect.NativeConstructorAccessorImpl.newInstance0(Native Method)
	at sun.reflect.NativeConstructorAccessorImpl.newInstance(NativeConstructorAccessorImpl.java:62)
	at sun.reflect.DelegatingConstructorAccessorImpl.newInstance(DelegatingConstructorAccessorImpl.java:45)
	at java.lang.reflect.Constructor.newInstance(Constructor.java:423)
	at org.apache.hadoop.hbase.regionserver.HRegionServer.constructRegionServer(HRegionServer.java:3029)
	at org.apache.hadoop.hbase.regionserver.HRegionServerCommandLine.start(HRegionServerCommandLine.java:63)
	at org.apache.hadoop.hbase.regionserver.HRegionServerCommandLine.run(HRegionServerCommandLine.java:87)
	at org.apache.hadoop.util.ToolRunner.run(ToolRunner.java:70)
	at org.apache.hadoop.hbase.util.ServerCommandLine.doMain(ServerCommandLine.java:149)
	at org.apache.hadoop.hbase.regionserver.HRegionServer.main(HRegionServer.java:3047)
Caused by: java.lang.ClassNotFoundException: org.apache.htrace.SamplerBuilder
	at java.net.URLClassLoader.findClass(URLClassLoader.java:381)
	at java.lang.ClassLoader.loadClass(ClassLoader.java:424)
	at sun.misc.Launcher$AppClassLoader.loadClass(Launcher.java:349)
	at java.lang.ClassLoader.loadClass(ClassLoader.java:357)
	... 26 more

```

Workaround via any _one_ of the following:
* If you are running against a Hadoop cluster that is 2.8+, ensure you replace the Hadoop libaries in the default binary assembly with those for your version.
* If you are running against a Hadoop cluster that is 2.8+, build the binary assembly from the source release while specifying your Hadoop version.
* If you are running against a Hadoop cluster that is a supported 2.7 release, ensure the `hadoop` executable is in the `PATH` seen at Region Server startup and that you are not using the `HBASE_DISABLE_HADOOP_CLASSPATH_LOOKUP` bypass.
* For any supported Hadoop version, manually make the Apache HTrace artifact `htrace-core-3.1.0-incubating.jar` available to all Region Servers via the HBASE_CLASSPATH environment variable.
* For any supported Hadoop version, manually make the Apache HTrace artifact `htrace-core-3.1.0-incubating.jar` available to all Region Servers by copying it into the directory `${HBASE_HOME}/lib/client-facing-thirdparty/`.



