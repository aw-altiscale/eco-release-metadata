
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
# Apache Tez  0.6.2 Release Notes

These release notes cover new developer and user-facing incompatibilities, features, and major improvements.


---

* [TEZ-2636](https://issues.apache.org/jira/browse/TEZ-2636) | *Major* | **MRInput and MultiMRInput should work for cases when there are 0 physical inputs**

It's possible that an Input is setup without any actual data. This is especially valid when a task is processing multiple MRInputs. One side has data, but the other does not. In such cases - we currently end up generating an error.


---

* [TEZ-2635](https://issues.apache.org/jira/browse/TEZ-2635) | *Major* | **Limit number of attempts being downloaded in unordered fetch**

{noformat}
2015-07-22 23:39:14,221 WARN [Fetcher [Map\_3] #4] shuffle.Fetcher: Fetch Failure from host while connecting: machine123, attempt: InputAttemptIdentifier [inputIdentifier=InputIdentifier [inputIndex=12], attemptNumber=0, pathComponent=attempt\_1437098194051\_0178\_2\_02\_000012\_0\_10003\_0, fetchTypeInfo=INCREMENTAL\_UPDATE, spillEventId=0] Informing ShuffleManager: 
java.io.IOException: Server returned HTTP response code: 400 for URL: http://machine123:13562/mapOutput?job=job\_1437098194051\_0178&reduce=279&map=attempt\_1437098194051\_0178\_2\_02\_000012\_0\_10003\_0,attempt\_1437098194051\_0178\_2\_02\_000012\_0\_10003\_1,attempt\_1437098194051\_0178\_2\_02\_000012\_0\_10003\_2,attempt\_1437098194051\_0178\_2\_02\_000012\_0\_10003\_3,attempt\_1437098194051\_0178\_2\_02\_000031\_0\_10006\_0,attempt\_1437098194051\_0178\_2\_02\_000031\_0\_10006\_1,attempt\_1437098194051\_0178\_2\_02\_000031\_0\_10006\_2,attempt\_1437098194051\_0178\_2\_02\_000031\_0\_10006\_3,attempt\_1437098194051\_0178\_2\_02\_000031\_0\_10006\_4,attempt\_1437098194051\_0178\_2\_02\_000050\_0\_10009\_0,attempt\_1437098194051\_0178\_2\_02\_000050\_0\_10009\_1,attempt\_1437098194051\_0178\_2\_02\_000050\_0\_10009\_2,attempt\_1437098194051\_0178\_2\_02\_000050\_0\_10009\_3,attempt\_1437098194051\_0178\_2\_02\_000069\_0\_10012\_0,attempt\_1437098194051\_0178\_2\_02\_000088\_0\_10033\_0,attempt\_1437098194051\_0178\_2\_02\_000107\_0\_10033\_0,attempt\_1437098194051\_0178\_2\_02\_000126\_0\_10006\_0,attempt\_1437098194051\_0178\_2\_02\_000069\_0\_10012\_1,attempt\_1437098194051\_0178\_2\_02\_000088\_0\_10033\_1,attempt\_1437098194051\_0178\_2\_02\_000145\_0\_10006\_0,attempt\_1437098194051\_0178\_2\_02\_000107\_0\_10033\_1,attempt\_1437098194051\_0178\_2\_02\_000126\_0\_10006\_1,attempt\_1437098194051\_0178\_2\_02\_000069\_0\_10012\_2,attempt\_1437098194051\_0178\_2\_02\_000069\_0\_10012\_3,attempt\_1437098194051\_0178\_2\_02\_000145\_0\_10006\_1,attempt\_1437098194051\_0178\_2\_02\_000088\_0\_10033\_2,attempt\_1437098194051\_0178\_2\_02\_000107\_0\_10033\_2,attempt\_1437098194051\_0178\_2\_02\_000126\_0\_10006\_2,attempt\_1437098194051\_0178\_2\_02\_000164\_0\_10030\_0,attempt\_1437098194051\_0178\_2\_02\_000183\_0\_10006\_0,attempt\_1437098194051\_0178\_2\_02\_000107\_0\_10033\_3,attempt\_1437098194051\_0178\_2\_02\_000145\_0\_10006\_2,attempt\_1437098194051\_0178\_2\_02\_000088\_0\_10033\_3,attempt\_1437098194051\_0178\_2\_02\_000088\_0\_10033\_4,attempt\_1437098194051\_0178\_2\_02\_000202\_0\_10015\_0,attempt\_1437098194051\_0178\_2\_02\_000145\_0\_10006\_3,attempt\_1437098194051\_0178\_2\_02\_000126\_0\_10006\_3,attempt\_1437098194051\_0178\_2\_02\_000126\_0\_10006\_4,attempt\_1437098194051\_0178\_2\_02\_000164\_0\_10030\_1,attempt\_1437098194051\_0178\_2\_02\_000183\_0\_10006\_1,attempt\_1437098194051\_0178\_2\_02\_000202\_0\_10015\_1,attempt\_1437098194051\_0178\_2\_02\_000183\_0\_10006\_2,attempt\_1437098194051\_0178\_2\_02\_000164\_0\_10030\_2,attempt\_1437098194051\_0178\_2\_02\_000164\_0\_10030\_3,attempt\_1437098194051\_0178\_2\_02\_000183\_0\_10006\_3,attempt\_1437098194051\_0178\_2\_02\_000202\_0\_10015\_2,attempt\_1437098194051\_0178\_2\_02\_000202\_0\_10015\_3,attempt\_1437098194051\_0178\_2\_02\_000133\_0\_10036\_0,attempt\_1437098194051\_0178\_2\_02\_000096\_0\_10012\_0,attempt\_1437098194051\_0178\_2\_02\_000114\_0\_10009\_0,attempt\_1437098194051\_0178\_2\_02\_000095\_0\_10009\_0,attempt\_1437098194051\_0178\_2\_02\_000153\_0\_10041\_0,attempt\_1437098194051\_0178\_2\_02\_000143\_0\_10036\_0,attempt\_1437098194051\_0178\_2\_02\_000190\_0\_10015\_0,attempt\_1437098194051\_0178\_2\_02\_000181\_0\_10042\_0,attempt\_1437098194051\_0178\_2\_02\_000133\_0\_10036\_1,attempt\_1437098194051\_0178\_2\_02\_000143\_0\_10036\_1,attempt\_1437098194051\_0178\_2\_02\_000153\_0\_10041\_1,attempt\_1437098194051\_0178\_2\_02\_000190\_0\_10015\_1,attempt\_1437098194051\_0178\_2\_02\_000209\_0\_10018\_0,attempt\_1437098194051\_0178\_2\_02\_000095\_0\_10009\_1,attempt\_1437098194051\_0178\_2\_02\_000114\_0\_10009\_1,attempt\_1437098194051\_0178\_2\_02\_000096\_0\_10012\_1,attempt\_1437098194051\_0178\_2\_02\_000181\_0\_10042\_1,attempt\_1437098194051\_0178\_2\_02\_000133\_0\_10036\_2,attempt\_1437098194051\_0178\_2\_02\_000153\_0\_10041\_2,attempt\_1437098194051\_0178\_2\_02\_000143\_0\_10036\_2,attempt\_1437098194051\_0178\_2\_02\_000114\_0\_10009\_2,attempt\_1437098194051\_0178\_2\_02\_000190\_0\_10015\_2,attempt\_1437098194051\_0178\_2\_02\_000133\_0\_10036\_3,attempt\_1437098194051\_0178\_2\_02\_000095\_0\_10009\_2,attempt\_1437098194051\_0178\_2\_02\_000096\_0\_10012\_2,attempt\_1437098194051\_0178\_2\_02\_000209\_0\_10018\_1,attempt\_1437098194051\_0178\_2\_02\_000181\_0\_10042\_2,attempt\_1437098194051\_0178\_2\_02\_000153\_0\_10041\_3,attempt\_1437098194051\_0178\_2\_02\_000095\_0\_10009\_3,attempt\_1437098194051\_0178\_2\_02\_000096\_0\_10012\_3,attempt\_1437098194051\_0178\_2\_02\_000114\_0\_10009\_3,attempt\_1437098194051\_0178\_2\_02\_000190\_0\_10015\_3,attempt\_1437098194051\_0178\_2\_02\_000143\_0\_10036\_3,attempt\_1437098194051\_0178\_2\_02\_000190\_0\_10015\_4,attempt\_1437098194051\_0178\_2\_02\_000143\_0\_10036\_4,attempt\_1437098194051\_0178\_2\_02\_000181\_0\_10042\_3,attempt\_1437098194051\_0178\_2\_02\_000153\_0\_10041\_4,attempt\_1437098194051\_0178\_2\_02\_000181\_0\_10042\_4,attempt\_1437098194051\_0178\_2\_02\_000209\_0\_10018\_2,attempt\_1437098194051\_0178\_2\_02\_000209\_0\_10018\_3&keepAlive=true
	at sun.net.www.protocol.http.HttpURLConnection.getInputStream0(HttpURLConnection.java:1839)
	at sun.net.www.protocol.http.HttpURLConnection.getInputStream(HttpURLConnection.java:1440)
	at org.apache.tez.http.HttpConnection.getInputStream(HttpConnection.java:248)
	at org.apache.tez.runtime.library.common.shuffle.Fetcher.setupConnection(Fetcher.java:441)
	at org.apache.tez.runtime.library.common.shuffle.Fetcher.doHttpFetch(Fetcher.java:470)
	at org.apache.tez.runtime.library.common.shuffle.Fetcher.doHttpFetch(Fetcher.java:403)
	at org.apache.tez.runtime.library.common.shuffle.Fetcher.callInternal(Fetcher.java:199)
	at org.apache.tez.runtime.library.common.shuffle.Fetcher.callInternal(Fetcher.java:71)
	at org.apache.tez.common.CallableWithNdc.call(CallableWithNdc.java:36)
	at java.util.concurrent.FutureTask.run(FutureTask.java:266)
	at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1142)
	at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:617)
	at java.lang.Thread.run(Thread.java:745)
{noformat}

tez.runtime.shuffle.fetch.max.task.output.at.once is provided only for ordered fetch, which defaults to 20. But for unordered case, this is not honored.

[~gopalv] got this issue when executing "select p.p\_partkey, li.l\_suppkey from (select distinct l\_partkey as p\_partkey from lineitem) p join lineitem li on p.p\_partkey = li.l\_partkey where li.l\_linenumber = 1 and li.l\_orderkey in (select l\_orderkey from lineitem where l\_shipmode = 'AIR') limit 2" @ 10 TB scale


---

* [TEZ-2623](https://issues.apache.org/jira/browse/TEZ-2623) | *Major* | **Fix module dependencies related to hadoop-auth**

Tez doesn't compile when the {{.m2}} directory is empty. It needs to depend on {{hadoop-auth}} as well.

{code}
[ERROR] /Users/rjain/workspace/tez/tez-runtime-library/src/main/java/org/apache/tez/runtime/library/common/shuffle/HttpConnection.java:[402,51] cannot access org.apache.hadoop.security.authentication.client.ConnectionConfigurator
  class file for org.apache.hadoop.security.authentication.client.ConnectionConfigurator not found
[INFO] 1 error
{code}


---

* [TEZ-2600](https://issues.apache.org/jira/browse/TEZ-2600) | *Major* | **When used with HDFS federation(viewfs) ,tez will throw a error**

When I execute the exapmle of tez,orderedwordcount ,Tez throw a error
{code}
java.lang.IllegalArgumentException: Wrong FS: hdfs://SunshineNameNode2/user/wang/tez-0.6.0.tar.gz, expected: viewfs://nsX/
        at org.apache.hadoop.fs.FileSystem.checkPath(FileSystem.java:645)
        at org.apache.hadoop.fs.viewfs.ViewFileSystem.getUriPath(ViewFileSystem.java:117)
        at org.apache.hadoop.fs.viewfs.ViewFileSystem.getFileStatus(ViewFileSystem.java:346)
        at org.apache.hadoop.fs.FileSystem.isDirectory(FileSystem.java:1413)
        at org.apache.tez.client.TezClientUtils.getLRFileStatus(TezClientUtils.java:130)
        at org.apache.tez.client.TezClientUtils.setupTezJarsLocalResources(TezClientUtils.java:179)
        at org.apache.tez.client.TezClient.getTezJarResources(TezClient.java:757)
        at org.apache.tez.client.TezClient.submitDAGApplication(TezClient.java:725)
        at org.apache.tez.client.TezClient.submitDAGApplication(TezClient.java:703)
        at org.apache.tez.client.TezClient.submitDAG(TezClient.java:383)
        at org.apache.tez.examples.OrderedWordCount.run(OrderedWordCount.java:208)
        at org.apache.tez.examples.OrderedWordCount.run(OrderedWordCount.java:232)
        at org.apache.hadoop.util.ToolRunner.run(ToolRunner.java:70)
        at org.apache.tez.examples.OrderedWordCount.main(OrderedWordCount.java:240)
        at sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
        at sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:57)
        at sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
        at java.lang.reflect.Method.invoke(Method.java:606)
        at org.apache.hadoop.util.ProgramDriver$ProgramDescription.invoke(ProgramDriver.java:72)
        at org.apache.hadoop.util.ProgramDriver.run(ProgramDriver.java:145)
        at org.apache.tez.examples.ExampleDriver.main(ExampleDriver.java:61)
        at sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
        at sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:57)
        at sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
        at java.lang.reflect.Method.invoke(Method.java:606)
        at org.apache.hadoop.util.RunJar.main(RunJar.java:212)

{code}


---

* [TEZ-2579](https://issues.apache.org/jira/browse/TEZ-2579) | *Major* | **Incorrect comparison of TaskAttemptId**

TaskImpl#AttemptSucceededTransition
{code}
      // issue kill to all other attempts
      for (TaskAttempt attempt : task.attempts.values()) {
        if (attempt.getID() != task.successfulAttempt &&  // should use !equals 
        !attempt.isFinished()) {           // but it won't affect the state machine transition, because the successful task attempt should already complete. 
{code}


---

* [TEZ-2566](https://issues.apache.org/jira/browse/TEZ-2566) | *Major* | **Allow TaskAttemptFinishedEvent without TaskAttemptStartedEvent when it is KILLED/FAILED**

TEZ-2304 allow logging TaskAttempFinishedEvent even without TaskAttemptStartedEvent but don't change the logic in Task#restoreFromEvent.
Task attempt is possible to be KILLED/FAILED before it is started, but not possible to be SUCCEEDED without started.


---

* [TEZ-2561](https://issues.apache.org/jira/browse/TEZ-2561) | *Major* | **Port for TaskAttemptListenerImpTezDag should be configurable**

Noticed sporadic DAG failures in our ec2 test environment.
Tasks failing with that:
{noformat}
2015-06-17 11:19:51,064 INFO [main] impl.MetricsSystemImpl: Scheduled snapshot period at 10 second(s).
2015-06-17 11:19:51,064 INFO [main] impl.MetricsSystemImpl: TezTask metrics system started
2015-06-17 11:19:51,259 INFO [TezChild] task.ContainerReporter: Attempting to fetch new task
2015-06-17 11:20:11,311 INFO [TezChild] ipc.Client: Retrying connect to server: ip-10-149-102-100.ec2.internal/10.149.102.100:60630. Already tried 0 time(s); maxRetries=5
2015-06-17 11:20:31,312 INFO [TezChild] ipc.Client: Retrying connect to server: ip-10-149-102-100.ec2.internal/10.149.102.100:60630. Already tried 1 time(s); maxRetries=5
2015-06-17 11:20:51,313 INFO [TezChild] ipc.Client: Retrying connect to server: ip-10-149-102-100.ec2.internal/10.149.102.100:60630. Already tried 2 time(s); maxRetries=5
2015-06-17 11:21:11,314 INFO [TezChild] ipc.Client: Retrying connect to server: ip-10-149-102-100.ec2.internal/10.149.102.100:60630. Already tried 3 time(s); maxRetries=5
2015-06-17 11:21:31,315 INFO [TezChild] ipc.Client: Retrying connect to server: ip-10-149-102-100.ec2.internal/10.149.102.100:60630. Already tried 4 time(s); maxRetries=5
2015-06-17 11:21:51,317 INFO [main] impl.MetricsSystemImpl: Stopping TezTask metrics system...
2015-06-17 11:21:51,318 INFO [main] impl.MetricsSystemImpl: TezTask metrics system stopped.
2015-06-17 11:21:51,318 INFO [main] impl.MetricsSystemImpl: TezTask metrics system shutdown complete.
{noformat}

From the AppMaster:
{noformat}
Created DAGAppMaster for application appattempt\_1434553606315\_0022\_000001
2015-06-17 11:19:43,655 INFO [Socket Reader #1 for port 60630] ipc.Server: Starting Socket Reader #1 for port 60630
2015-06-17 11:19:43,656 INFO [Socket Reader #1 for port 31001] ipc.Server: Starting Socket Reader #1 for port 31001
2015-06-17 11:19:43,713 WARN [ServiceThread:org.apache.tez.dag.history.HistoryEventHandler] conf.Configuration: mapred-site.xml:an attempt to override final parameter: mapreduce.cluster.local.dir;  Ignoring.
{noformat}

[~hitesh] mentioned its likely to be the TaskAttemptListenerImpTezDag which starts on that port. Would be nice if the port(-range) can be configured!!!


---

* [TEZ-2560](https://issues.apache.org/jira/browse/TEZ-2560) | *Major* | **fix tex-ui build for maven 3.3+**

currently tez-ui build fails if mvn version is 3.3 due to the frontend-maven-plugin. this is fixed in 0.0.23 version of the plugin but it fails on maven version below 3.1


---

* [TEZ-2552](https://issues.apache.org/jira/browse/TEZ-2552) | *Major* | **CRC errors can cause job to run for very long time in large jobs**

Ran a fairly large job at 10 TB scale which had 1009 reducers.

One of the machine had bad disk and NM did not delist that disk.  Machine hosting NM has disk issues (sdf & sde holds shuffle data).  exceptions.

{noformat}
Info fld=0x8960894
sd 6:0:5:0: [sdf]  Add. Sense: Unrecovered read error
sd 6:0:5:0: [sdf] CDB: Read(10): 28 00 08 96 08 90 00 00 08 00
end\_request: critical medium error, dev sdf, sector 144050320
sd 6:0:5:0: [sdf]  Result: hostbyte=DID\_OK driverbyte=DRIVER\_SENSE
sd 6:0:5:0: [sdf]  Sense Key : Medium Error [current]
Info fld=0x895a2b9
sd 6:0:5:0: [sdf]  Add. Sense: Unrecovered read error
sd 6:0:5:0: [sdf] CDB: Read(10): 28 00 08 95 a2 b8 00 00 08 00
end\_request: critical medium error, dev sdf, sector 144024248
sd 6:0:5:0: [sdf]  Result: hostbyte=DID\_OK driverbyte=DRIVER\_SENSE
sd 6:0:5:0: [sdf]  Sense Key : Medium Error [current]
Info fld=0x895a2b9
sd 6:0:5:0: [sdf]  Add. Sense: Unrecovered read error
sd 6:0:5:0: [sdf] CDB: Read(10): 28 00 08 95 a2 b8 00 00 08 00
end\_request: critical medium error, dev sdf, sector 144024248
sd 6:0:5:0: [sdf]  Result: hostbyte=DID\_OK driverbyte=DRIVER\_SENSE
sd 6:0:5:0: [sdf]  Sense Key : Medium Error [current]
Info fld=0x8849edb
sd 6:0:5:0: [sdf]  Add. Sense: Unrecovered read error
sd 6:0:5:0: [sdf] CDB: Read(10): 28 00 08 84 9e d8 00 00 08 00
end\_request: critical medium error, dev sdf, sector 142909144
sd 6:0:5:0: [sdf]  Result: hostbyte=DID\_OK driverbyte=DRIVER\_SENSE
sd 6:0:5:0: [sdf]  Sense Key : Medium Error [current]
Info fld=0x8849edb
sd 6:0:5:0: [sdf]  Add. Sense: Unrecovered read error
sd 6:0:5:0: [sdf] CDB: Read(10): 28 00 08 84 9e d8 00 00 08 00
end\_request: critical medium error, dev sdf, sector 142909144
{noformat}

In-memory fetches start throwing CRC as follows.  

{noformat}
2015-06-11 01:01:03,728 INFO [ShuffleAndMergeRunner [Map\_11]] orderedgrouped.ShuffleScheduler: PendingHosts=[]
2015-06-11 01:01:03,730 INFO [Fetcher [Map\_11] #0] http.HttpConnection: for url=http://cn056-10.l42scl.hortonworks.com:13562/mapOutput?job=job\_1433813751839\_0124&reduce=3&map=attempt\_1433813751839\_0124\_1\_04\_000446\_0\_10027&keepAlive=true sent hash and receievd reply 0 ms
2015-06-11 01:01:03,730 INFO [Fetcher [Map\_11] #0] orderedgrouped.FetcherOrderedGrouped: fetcher#439 about to shuffle output of map InputAttemptIdentifier [inputIdentifier=InputIdentifier [inputIndex=446], attemptNumber=0, pathComponent=attempt\_1433813751839\_0124\_1\_04\_000446\_0\_10027, fetchTypeInfo=FINAL\_MERGE\_ENABLED, spillEventId=-1] decomp: 45475 len: 23974 to MEMORY
2015-06-11 01:01:07,206 INFO [Fetcher [Map\_11] #0] impl.IFileInputStream:  CurrentOffset=2510, offset=2510, off=2502, dataLength=23966, origLen=21456, len=21456, length=23970, checksumSize=4
2015-06-11 01:01:07,207 INFO [Fetcher [Map\_11] #0] impl.IFileInputStream:  CurrentOffset=2510, offset=2510, off=0, dataLength=23966, origLen=21456, len=21456, length=23970, checksumSize=4
2015-06-11 01:01:07,207 WARN [Fetcher [Map\_11] #0] orderedgrouped.FetcherOrderedGrouped: Failed to shuffle output of InputAttemptIdentifier [inputIdentifier=InputIdentifier [inputIndex=446], attemptNumber=0, pathComponent=attempt\_1433813751839\_0124\_1\_04\_000446\_0\_10027, fetchTypeInfo=FINAL\_MERGE\_ENABLED, spillEventId=-1] from cn056-10.l42scl.hortonworks.com:13562
org.apache.hadoop.fs.ChecksumException: Checksum Error:  CurrentOffset=2510, offset=2510, off=2502, dataLength=23966, origLen=21456, len=21456, length=23970, checksumSize=4
	at org.apache.tez.runtime.library.common.sort.impl.IFileInputStream.doRead(IFileInputStream.java:255)
	at org.apache.tez.runtime.library.common.sort.impl.IFileInputStream.read(IFileInputStream.java:185)
	at org.apache.hadoop.io.compress.BlockDecompressorStream.getCompressedData(BlockDecompressorStream.java:127)
	at org.apache.hadoop.io.compress.BlockDecompressorStream.decompress(BlockDecompressorStream.java:98)
	at org.apache.hadoop.io.compress.DecompressorStream.read(DecompressorStream.java:85)
	at org.apache.hadoop.io.IOUtils.readFully(IOUtils.java:192)
	at org.apache.tez.runtime.library.common.sort.impl.IFile$Reader.readToMemory(IFile.java:619)
	at org.apache.tez.runtime.library.common.shuffle.ShuffleUtils.shuffleToMemory(ShuffleUtils.java:113)
	at org.apache.tez.runtime.library.common.shuffle.orderedgrouped.FetcherOrderedGrouped.copyMapOutput(FetcherOrderedGrouped.java:471)
	at org.apache.tez.runtime.library.common.shuffle.orderedgrouped.FetcherOrderedGrouped.copyFromHost(FetcherOrderedGrouped.java:267)
	at org.apache.tez.runtime.library.common.shuffle.orderedgrouped.FetcherOrderedGrouped.fetchNext(FetcherOrderedGrouped.java:164)
	at org.apache.tez.runtime.library.common.shuffle.orderedgrouped.FetcherOrderedGrouped.callInternal(FetcherOrderedGrouped.java:177)
	at org.apache.tez.runtime.library.common.shuffle.orderedgrouped.FetcherOrderedGrouped.callInternal(FetcherOrderedGrouped.java:52)
	at org.apache.tez.common.CallableWithNdc.call(CallableWithNdc.java:36)
	at java.util.concurrent.FutureTask.run(FutureTask.java:266)
	at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1142)
	at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:617)
	at java.lang.Thread.run(Thread.java:745)
{noformat}

TaskAttemptImpl didn't fail it due to the following code

{noformat}
float failureFraction = ((float) attempt.uniquefailedOutputReports.size())
          / outputFailedEvent.getConsumerTaskNumber();
{noformat}

In this case, reducer ran in 180 slot waves.  So even if all 180 tasks report the error, it would be around 180/1009 = 0.17 (which is less than 0.25 MAX\_ALLOWED\_OUTPUT\_FAILURES\_FRACTION) and the job runs for ever (killed the job after 2 hours; normally run in couple of minutes)

In fetcher side, reducer state would be healthy and it would continue to wait.

Env: Tez master & Hive master
Ref: Query\_88 @ 10 TB scale.


---

* [TEZ-2548](https://issues.apache.org/jira/browse/TEZ-2548) | *Major* | **TezClient submitDAG can hang if the AM is in the process of shutting down**

submitDAG and serviceStop are both synchronized causing submitDAG to be locked out during the shutdown process. 

Seen by [~gopalv]


---

* [TEZ-2534](https://issues.apache.org/jira/browse/TEZ-2534) | *Major* | **Error handling summary event when shutting down AM**

When AM is shutting down, it will close the summary stream, but there may be still some events in the queue which will cause exception when handling summary event. And this would cause the next AM fail to recover the running dag. 
One way to resolve this issue is to always drain the events in the queue before closing the summary stream (set drainEventsFlag as true), but this flag may be useful in unit test. 
{noformat}
2015-06-03 16:37:15,761 INFO [Thread-1] app.DAGAppMaster: DAGAppMasterShutdownHook invoked
2015-06-03 16:37:15,761 INFO [Thread-1] app.DAGAppMaster: DAGAppMaster received a signal. Signaling TaskScheduler
2015-06-03 16:37:15,761 INFO [Thread-1] rm.TaskSchedulerEventHandler: TaskScheduler notified that iSignalled was : true
2015-06-03 16:37:15,762 INFO [Thread-1] history.HistoryEventHandler: Stopping HistoryEventHandler
2015-06-03 16:37:15,762 INFO [Thread-1] recovery.RecoveryService: Stopping RecoveryService
2015-06-03 16:37:15,762 INFO [Thread-1] recovery.RecoveryService: Closing Summary Stream
2015-06-03 16:37:15,772 INFO [Thread-1] recovery.RecoveryService: Closing Output Stream for DAG dag\_1433320263267\_0019\_1
2015-06-03 16:37:15,773 ERROR [Dispatcher thread: Central] recovery.RecoveryService: Error handling summary event, eventType=VERTEX\_FINISHED
java.nio.channels.ClosedChannelException
	at org.apache.hadoop.hdfs.DFSOutputStream.checkClosed(DFSOutputStream.java:1622)
	at org.apache.hadoop.fs.FSOutputSummer.write(FSOutputSummer.java:104)
	at org.apache.hadoop.fs.FSDataOutputStream$PositionCache.write(FSDataOutputStream.java:58)
	at java.io.DataOutputStream.write(DataOutputStream.java:107)
	at com.google.protobuf.CodedOutputStream.refreshBuffer(CodedOutputStream.java:833)
	at com.google.protobuf.CodedOutputStream.flush(CodedOutputStream.java:843)
	at com.google.protobuf.AbstractMessageLite.writeDelimitedTo(AbstractMessageLite.java:91)
	at org.apache.tez.dag.history.events.VertexFinishedEvent.toSummaryProtoStream(VertexFinishedEvent.java:207)
	at org.apache.tez.dag.history.recovery.RecoveryService.handleSummaryEvent(RecoveryService.java:373)
	at org.apache.tez.dag.history.recovery.RecoveryService.handle(RecoveryService.java:285)
	at org.apache.tez.dag.history.HistoryEventHandler.handleCriticalEvent(HistoryEventHandler.java:105)
	at org.apache.tez.dag.app.dag.impl.VertexImpl.logJobHistoryVertexCompletedHelper(VertexImpl.java:1890)
	at org.apache.tez.dag.app.dag.impl.VertexImpl.logJobHistoryVertexFinishedEvent(VertexImpl.java:1869)
	at org.apache.tez.dag.app.dag.impl.VertexImpl.finished(VertexImpl.java:2107)
	at org.apache.tez.dag.app.dag.impl.VertexImpl.finished(VertexImpl.java:2125)
	at org.apache.tez.dag.app.dag.impl.VertexImpl.checkTasksForCompletion(VertexImpl.java:1989)
	at org.apache.tez.dag.app.dag.impl.VertexImpl$TaskCompletedTransition.transition(VertexImpl.java:3833)
	at org.apache.tez.dag.app.dag.impl.VertexImpl$TaskCompletedTransition.transition(VertexImpl.java:1)
	at org.apache.hadoop.yarn.state.StateMachineFactory$MultipleInternalArc.doTransition(StateMachineFactory.java:385)
	at org.apache.hadoop.yarn.state.StateMachineFactory.doTransition(StateMachineFactory.java:302)
	at org.apache.hadoop.yarn.state.StateMachineFactory.access$300(StateMachineFactory.java:46)
	at org.apache.hadoop.yarn.state.StateMachineFactory$InternalStateMachine.doTransition(StateMachineFactory.java:448)
	at org.apache.tez.state.StateMachineTez.doTransition(StateMachineTez.java:57)
	at org.apache.tez.dag.app.dag.impl.VertexImpl.handle(VertexImpl.java:1799)
	at org.apache.tez.dag.app.dag.impl.VertexImpl.handle(VertexImpl.java:1)
	at org.apache.tez.dag.app.DAGAppMaster$VertexEventDispatcher.handle(DAGAppMaster.java:1954)
	at org.apache.tez.dag.app.DAGAppMaster$VertexEventDispatcher.handle(DAGAppMaster.java:1)
	at org.apache.tez.common.AsyncDispatcher.dispatch(AsyncDispatcher.java:183)
	at org.apache.tez.common.AsyncDispatcher$1.run(AsyncDispatcher.java:114)
	at java.lang.Thread.run(Thread.java:745)
2015-06-03 16:37:15,775 ERROR [Dispatcher thread: Central] recovery.RecoveryService: Adding a flag to ensure next AM attempt does not start up, flagFile=hdfs://localhost:58857/tmp/owc-staging-dir/.tez/application\_1433320263267\_0019/recovery/1/RecoveryFatalErrorOccurred
2015-06-03 16:37:15,781 ERROR [Dispatcher thread: Central] recovery.RecoveryService: Recovery failure occurred. Skipping all events
2015-06-03 16:37:15,781 INFO [HistoryEventHandlingThread] impl.SimpleHistoryLoggingService: Writing event VERTEX\_FINISHED to history file
{noformat}


---

* [TEZ-2533](https://issues.apache.org/jira/browse/TEZ-2533) | *Major* | **AM deadlock when shutdown**

AM is shutdown due to AM\_REBOOT signal
{noformat}
2015-06-03 15:44:25,637 INFO [Dispatcher thread: Central] app.DAGAppMaster: Received an AM\_REBOOT signal
2015-06-03 15:44:25,637 INFO [Dispatcher thread: Central] app.DAGAppMaster: DAGAppMasterShutdownHandler invoked
2015-06-03 15:44:25,637 INFO [Dispatcher thread: Central] app.DAGAppMaster: Handling DAGAppMaster shutdown
2015-06-03 15:44:25,639 INFO [AMShutdownThread] app.DAGAppMaster: Calling stop for all the services
2015-06-03 15:44:25,640 INFO [AMShutdownThread] history.HistoryEventHandler: Stopping HistoryEventHandler
2015-06-03 15:44:25,640 INFO [AMShutdownThread] recovery.RecoveryService: Stopping RecoveryService
2015-06-03 15:44:25,640 INFO [AMShutdownThread] recovery.RecoveryService: Handle the remaining events in queue, queue size=0
2015-06-03 15:44:25,640 INFO [RecoveryEventHandlingThread] recovery.RecoveryService: EventQueue take interrupted. Returning
{noformat}
Then AM is failed to shutdown 
{noformat}
2015-06-03 15:44:25,814 WARN [AMShutdownThread] app.DAGAppMaster: Graceful stop failed
{noformat}
And at the same time AM shutdown hook is invoked and hang there, wait for lock of DAGAppMaster#shutdownHandlerRunning
{noformat}
2015-06-03 15:44:25,818 INFO [Thread-1] app.DAGAppMaster: DAGAppMasterShutdownHook invoked
2015-06-03 15:44:25,818 INFO [Thread-1] app.DAGAppMaster: The shutdown handler is still running, waiting for it to complete
{noformat}


---

* [TEZ-2511](https://issues.apache.org/jira/browse/TEZ-2511) | *Major* | **Add exitCode to diagnostics when container fails**

Currently we only identify the container failure cause for PREEMPTED / DISKS\_FAILED, that means except for these 2 cases, there would be no clear diagnostic message for other cases. 

{code}
      String message = "Container completed. ";
      TaskAttemptTerminationCause errCause = TaskAttemptTerminationCause.CONTAINER\_EXITED;
      int exitStatus = containerStatus.getExitStatus();
      if (exitStatus == ContainerExitStatus.PREEMPTED) {
        message = "Container preempted externally. ";
        errCause = TaskAttemptTerminationCause.EXTERNAL\_PREEMPTION;
      } else if (exitStatus == ContainerExitStatus.DISKS\_FAILED) {
        message = "Container disk failed. ";
        errCause = TaskAttemptTerminationCause.NODE\_DISK\_ERROR;
      } else if (exitStatus != ContainerExitStatus.SUCCESS){
        message = "Container failed. ";
      }
      if (containerStatus.getDiagnostics() != null) {
        message += containerStatus.getDiagnostics();
      }
      sendEvent(new AMContainerEventCompleted(amContainer.getContainerId(), exitStatus, message, errCause));
{code}


---

* [TEZ-2509](https://issues.apache.org/jira/browse/TEZ-2509) | *Major* | **YarnTaskSchedulerService should not try to allocate containers if AM is shutting down**

Observed when doing some recovery testing: 

Failure as during dag shutdown, 4 attempts of the same task failed. 

{code}
2015-06-01 07:38:27,184 INFO [Dispatcher thread: Central] history.HistoryEventHandler: [HISTORY][DAG:dag\_1433141118424\_0012\_2][Event:TASK\_FINISHED]: vertexName=initialmap, taskId=task\_1433141118424\_0012\_2\_00\_000003, startTime=1433144297281, finishTime=1433144307184, timeTaken=9903, status=FAILED, successfulAttemptID=null, diagnostics=TaskAttempt 0 failed, info=[Container container\_e02\_1433141118424\_0012\_01\_000018 hit an invalid transition - C\_NM\_STOP\_SENT at RUNNING]
TaskAttempt 1 failed, info=[AttemptId: attempt\_1433141118424\_0012\_2\_00\_000003\_1 cannot be allocated to container: container\_e02\_1433141118424\_0012\_01\_000011 in STOP\_REQUESTED state]
TaskAttempt 2 failed, info=[Container container\_e02\_1433141118424\_0012\_01\_000012 hit an invalid transition - C\_NM\_STOP\_SENT at RUNNING]
TaskAttempt 3 failed, info=[Container container\_e02\_1433141118424\_0012\_01\_000025 hit an invalid transition - C\_NM\_STOP\_SENT at RUNNING], counters=Counters: 0
{code}
  

DAG kill signal received.
{code}
2015-06-01 07:38:25,811 INFO [Thread-3] app.DAGAppMaster: DAGAppMasterShutdownHook invoked
2015-06-01 07:38:25,811 INFO [Thread-3] app.DAGAppMaster: DAGAppMaster received a signal. Signaling TaskScheduler
{code}

First attempt marked as failed as container was killed.
{code}
2015-06-01 07:38:26,906 INFO [Dispatcher thread: Central] history.HistoryEventHandler: [HISTORY][DAG:dag\_1433141118424\_0012\_2][Event:TASK\_ATTEMPT\_FINISHED]: vertexName=initialmap, taskAttemptId=attempt\_1433141118424\_0012\_2\_00\_000003\_0, startTime=1433144297281, finishTime=1433144306904, timeTaken=9623, status=FAILED, errorEnum=FRAMEWORK\_ERROR, diagnostics=Container container\_e02\_1433141118424\_0012\_01\_000018 hit an invalid transition - C\_NM\_STOP\_SENT at RUNNING, counters=Counters: 0
{code}

Subsequent attempt scheduled, assigned and eventually fails. 
{code}
2015-06-01 07:38:26,919 INFO [DelayedContainerManager] rm.YarnTaskSchedulerService: Assigning container to task, container=Container: [ContainerId: container\_e02\_1433141118424\_0012\_01\_000011, NodeId: ip-172-31-18-41.ec2.internal:45454, NodeHttpAddress: ip-172-31-18-41.ec2.internal:8042, Resource: <memory:1536, vCores:1>, Priority: 2, Token: Token { kind: ContainerToken, service: 172.31.18.41:45454 }, ], task=attempt\_1433141118424\_0012\_2\_00\_000003\_1, containerHost=ip-172-31, localityMatchType=NodeLocal, matchedLocation=ip-172-31-18-41.ec2.internal, honorLocalityFlags=true, reusedContainer=true, delayedContainers=4, containerResourceMemory=1536, containerResourceVCores=1
{code}

Scheduler stops too late.
{code}
2015-06-01 07:38:27,403 DEBUG [Thread-3] service.AbstractService: Service: org.apache.tez.dag.app.rm.YarnTaskSchedulerService entered state STOPPED
{code}


---

* [TEZ-2489](https://issues.apache.org/jira/browse/TEZ-2489) | *Major* | **Disable warn log for Timeline ACL error when tez.allow.disabled.timeline-domains set to true**

15/05/26 22:57:38 WARN client.TezClient: Could not instantiate object for org.apache.tez.dag.history.ats.acls.ATSHistoryACLPolicyManager. ACLs cannot be enforced correctly for history data in Timeline
org.apache.tez.dag.api.TezUncheckedException: Unable to load class: org.apache.tez.dag.history.ats.acls.ATSHistoryACLPolicyManager
       at org.apache.tez.common.ReflectionUtils.getClazz(ReflectionUtils.java:45)
       at org.apache.tez.common.ReflectionUtils.createClazzInstance(ReflectionUtils.java:88)
       at org.apache.tez.client.TezClient.start(TezClient.java:317)
       at cascading.flow.tez.planner.Hadoop2TezFlowStepJob.internalNonBlockingStart(Hadoop2TezFlowStepJob.java:137)
       at cascading.flow.planner.FlowStepJob.blockOnJob(FlowStepJob.java:248)
       at cascading.flow.planner.FlowStepJob.start(FlowStepJob.java:172)
       at cascading.flow.planner.FlowStepJob.call(FlowStepJob.java:134)
       at cascading.flow.planner.FlowStepJob.call(FlowStepJob.java:45)
       at java.util.concurrent.FutureTask.run(FutureTask.java:262)
       at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1145)
       at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:615)
       at java.lang.Thread.run(Thread.java:745)
Caused by: java.lang.ClassNotFoundException: org.apache.tez.dag.history.ats.acls.ATSHistoryACLPolicyManager
       at java.net.URLClassLoader$1.run(URLClassLoader.java:366)
       at java.net.URLClassLoader$1.run(URLClassLoader.java:355)

Reported by @chris wensel


---

* [TEZ-2483](https://issues.apache.org/jira/browse/TEZ-2483) | *Major* | **Tez should close task if processor fail**

The symptom is if PigProcessor fail, MRInput is not closed. On Windows, this creates a problem since Pig client cannot remove the input file.

In general, if a task fail, Tez shall close all input/output handles in cleanup. MROutput is closed in MROutput.abort() which Pig invokes explicitly right now. Attach a demo patch.


---

* [TEZ-2475](https://issues.apache.org/jira/browse/TEZ-2475) | *Major* | **Tez local mode hanging in big testsuite**

we have a big test suite for lingual, our SQL layer for cascading. We are trying very hard to make it work correctly on Tez, but I am stuck:

The setup is a huge suite of SQL based tests (6000+), which are being executed in order in local mode. At certain moments the whole process just stops. Nothing gets executed any longer. This is not all the time, but quite often. Note that it is not happening at the same line of code, more at random, which makes it quite complex to debug.

What I am seeing, is these kind of stacktraces in the middle of the run:

2015-05-21 16:07:42,413 ERROR [TaskHeartbeatThread] task.TezTaskRunner (TezTaskRunner.java:reportError(333)) - TaskReporter reported error
    java.lang.InterruptedException
        at java.util.concurrent.locks.AbstractQueuedSynchronizer$ConditionObject.reportInterruptAfterWait(AbstractQueuedSynchronizer.java:2017)
        at java.util.concurrent.locks.AbstractQueuedSynchronizer$ConditionObject.await(AbstractQueuedSynchronizer.java:2188)
        at org.apache.tez.runtime.task.TaskReporter$HeartbeatCallable.call(TaskReporter.java:187)
        at org.apache.tez.runtime.task.TaskReporter$HeartbeatCallable.call(TaskReporter.java:118)
        at java.util.concurrent.FutureTask.run(FutureTask.java:262)
        at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1145)
        at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:615)
        at java.lang.Thread.run(Thread.java:745)

This looks like it could be related to the hang, but the hang is not happening immediately afterwards, but some time later.

I have gone through quite a few JIRAs and saw that there were problems with locks and hanging threads before, which should be fixed, but it still happens.

I have tried 0.6.1 and 0.7.0. Both show the same behaviour.

This gist contains a thread dump of a hanging build: https://gist.github.com/fs111/1ee44469bf5cc31e5a52


---

* [TEZ-2311](https://issues.apache.org/jira/browse/TEZ-2311) | *Major* | **AM can hang if kill received while recovering from previous attempt**

We saw an instance of a Tez job hanging despite receiving multiple kill requests from clients.  The AM was recovering from a prior attempt when the first kill request arrived.


---

* [TEZ-2304](https://issues.apache.org/jira/browse/TEZ-2304) | *Major* | **InvalidStateTransitonException TA\_SCHEDULE at START\_WAIT during recovery**

I saw a Tez AM throw a few InvalidStateTransitonException (sic) instances during recovery complaining about TA\_SCHEDULE arriving at the START\_WAIT state.


---

* [TEZ-2080](https://issues.apache.org/jira/browse/TEZ-2080) | *Major* | **Localclient should be using tezconf in init instead of yarnconf**

currently in the LocalClient the config used is yarnconf. this should be tezconf.

{code:title=LocalClient.java}
@Override
  public void init(TezConfiguration tezConf, YarnConfiguration yarnConf) {
    this.conf = yarnConf;
{code}


---

* [TEZ-1529](https://issues.apache.org/jira/browse/TEZ-1529) | *Blocker* | **ATS and TezClient integration  in secure kerberos enabled cluster**

This is a follow up for TEZ-1495 which address ATS - TezClient integration. however it does not enable it  in secure kerberos enabled cluster.


