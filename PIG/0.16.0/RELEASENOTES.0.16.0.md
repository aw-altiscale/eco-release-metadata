
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
# Apache Pig  0.16.0 Release Notes

These release notes cover new developer and user-facing incompatibilities, features, and major improvements.


---

* [PIG-4639](https://issues.apache.org/jira/browse/PIG-4639) | *Major* | **Add better parser for Apache HTTPD access log.**

In piggybank there is now a generic Apache httpd access log loader that supports (almost) all custom LogFormats.


---

* [PIG-4638](https://issues.apache.org/jira/browse/PIG-4638) | *Major* | **Allow TOMAP to accept dynamically sized input**

The TOMAP function now also accepts a bag of key-value pairs as input.


---

* [PIG-4578](https://issues.apache.org/jira/browse/PIG-4578) | *Minor* | **ToDateISO should support optional ' ' space variant used by JDBC**

Built-in UDF ToDateISO(chararray) now allows a space character instead of requiring a 'T' between date and time in an ISO-8601 timestamp. Facilitates parsing of JDBC timestamp format.


---

* [PIG-4405](https://issues.apache.org/jira/browse/PIG-4405) | *Major* | **Adding 'map[]' support to mock/Storage**

The Storage mocking feature supports input and output of "map" types.


---

* [PIG-4365](https://issues.apache.org/jira/browse/PIG-4365) | *Major* | **TOP udf should implement Accumulator interface**

TOP udf implements Accumulator interface


