
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
# Apache Sentry  2.0.0 Release Notes

These release notes cover new developer and user-facing incompatibilities, important issues, features, and major improvements.


---

* [SENTRY-1477](https://issues.apache.org/jira/browse/SENTRY-1477) | *Major* | **Sentry clients should retry with another server when they get connection errors**

When Sentry clients get a connection error when talking to a server they should re-try connection with another server. This should be normal client behavior when one of the servers goes down.


---

* [SENTRY-1606](https://issues.apache.org/jira/browse/SENTRY-1606) | *Major* | **Sentry HDFS Sync should survive in presence of  bad paths objects**

Currently when Sentry encounters any problem with the path object it fails to construct a snapshot and the whole HDFS sync process breaks. 

To make things more robust it should skip bad paths and continue creating the snapshot.


---

* [SENTRY-1721](https://issues.apache.org/jira/browse/SENTRY-1721) | *Major* | **Unit test failures in TestSentryStore due to changeId miscount**

We encounter multiple incidents of unit test failures. They are mainly TestSentryStore.testPrivilegesWithPermUpdate and TestPrivilegeOperatePersistence.testGrantPrivilegeExternalComponentInvalidConf

These tests fail more often when HMSFollower is created after SentryService.Start() is called. And less frequent when HMSFollower is created in SentryService constructor. Need investigation on whether this is just a bug in test cases or reflect issues in synchronization between Sentry HMS metastore.


---

* [SENTRY-1895](https://issues.apache.org/jira/browse/SENTRY-1895) | *Major* | **Sentry should handle the case of multiple notifications with the same ID**

As shown in HIVE-16886, notification IDs generated by Hive may be non-unique and there may be cases with different evnts sharing the same ID. This creates various problems for Sentry/Hive interaction and we should fine some short -term solution until it is fixed in Hive.

The issue was addressed in SENTRY-1803 by removing a primary-key constraint on the notification Id which allows for multiple keys. But this creates other problems:

1. We are using the primary key constraint to prevent multiple instances of Sentry from processing the same notifications multiple times.
2. We are using max(notificationId) to find the last processed event. When the field is a primary key, this operation is an index scan, but when it isn't, it is a full table scan which is more expensive.

We also have a few other problems caused by duplicate IDs which are not related and not addressed by SENTRY-1803:

1. There is a  synchronization mechanism between HMS and Sentry which ensures that a given event is processed. This doesn't work in the presence of duplicate IDs.
2. Some events may be missed due to the way they are processed.


