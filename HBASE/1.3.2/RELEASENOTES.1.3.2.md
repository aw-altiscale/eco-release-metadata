
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
# Apache HBase  1.3.2 Release Notes

These release notes cover new developer and user-facing incompatibilities, important issues, features, and major improvements.


---

* [HBASE-17514](https://issues.apache.org/jira/browse/HBASE-17514) | *Minor* | **Warn when Thrift Server 1 is configured for proxy users but not the HTTP transport**

If users of the Thrift 1 Server enable proxy user support without enabling the prerequisite HTTP transport, we now log a WARN message about the mismatch.


---

* [HBASE-17877](https://issues.apache.org/jira/browse/HBASE-17877) | *Major* | **Improve HBase\'s byte[] comparator**

updated the lexicographic byte array comparator to use a slightly more optimized version similar to the one available in the guava library that compares only the first index where left[index] != right[index]. The comparator also returns the diff directly instead of mapping it to -1, 0, +1 range as was being done in the earlier version. We have seen significant performance gains, calculated in terms of throughput (ops/ms) with these changes ranging from approx 20% for smaller byte arrays upto 200 bytes and almost 100% for large byte array sizes that are in few KB\'s. We benchmarked with upto 16KB arrays and the general trend indicates that the performance improvement increases as the size of the byte array increases.


---

* [HBASE-17817](https://issues.apache.org/jira/browse/HBASE-17817) | *Major* | **Make Regionservers log which tables it removed coprocessors from when aborting**

Add table name to exception logging when a coprocessor is removed from a table by the region server


