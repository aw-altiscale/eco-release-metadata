
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
# Apache Orc Changelog

## Release 1.2.0 - 2016-08-25



### IMPROVEMENTS:

| JIRA | Summary | Priority | Component | Reporter | Contributor |
|:---- |:---- | :--- |:---- |:---- |:---- |
| [ORC-65](https://issues.apache.org/jira/browse/ORC-65) | Write new documentation for site |  Major | site | Owen O'Malley | Owen O'Malley |
| [ORC-71](https://issues.apache.org/jira/browse/ORC-71) | Apache ORC C++ ONLY build |  Trivial | C++ | Sudhir Babu Pothineni | Sudhir Babu Pothineni |
| [ORC-69](https://issues.apache.org/jira/browse/ORC-69) | Add batch option support in orc-contents and orc-scan tools. |  Trivial | tools | hongwu | hongwu |
| [ORC-75](https://issues.apache.org/jira/browse/ORC-75) | Don't create backup versions of the poms when version change |  Major | . | Owen O'Malley | Owen O'Malley |
| [ORC-84](https://issues.apache.org/jira/browse/ORC-84) | Create a separate java tool module |  Major | . | Owen O'Malley | Owen O'Malley |
| [ORC-85](https://issues.apache.org/jira/browse/ORC-85) | Update the C++ library with the newer WriterVersion values. |  Major | . | Owen O'Malley | Owen O'Malley |
| [ORC-54](https://issues.apache.org/jira/browse/ORC-54) | Evolve schemas based on field name rather than index |  Major | . | Mark Wagner | Mark Wagner |
| [ORC-96](https://issues.apache.org/jira/browse/ORC-96) | Pass Context to Orc tree readers |  Major | Reader | Prasanth Jayachandran | Prasanth Jayachandran |


### BUG FIXES:

| JIRA | Summary | Priority | Component | Reporter | Contributor |
|:---- |:---- | :--- |:---- |:---- |:---- |
| [ORC-76](https://issues.apache.org/jira/browse/ORC-76) | Update website with ORC 1.1.1 |  Major | . | Owen O'Malley | Owen O'Malley |
| [ORC-79](https://issues.apache.org/jira/browse/ORC-79) | Minor updates to the website. |  Major | . | Owen O'Malley | Owen O'Malley |
| [ORC-80](https://issues.apache.org/jira/browse/ORC-80) | C++ build breaks due to warnings with gcc-4.9 |  Major | . | Deepak Majeti | Deepak Majeti |
| [ORC-82](https://issues.apache.org/jira/browse/ORC-82) | Fix compilation on ubuntu 12. |  Major | . | Owen O'Malley | Owen O'Malley |
| [ORC-83](https://issues.apache.org/jira/browse/ORC-83) | Protected users from Reader.rows(Options) modifying the Options object |  Major | . | Owen O'Malley | Owen O'Malley |
| [ORC-88](https://issues.apache.org/jira/browse/ORC-88) | Add a raw metadata switch to orc-metadata |  Major | . | Owen O'Malley | Owen O'Malley |
| [ORC-81](https://issues.apache.org/jira/browse/ORC-81) | Add support for lzo and lz4 to c++ reader |  Major | . | Owen O'Malley | Owen O'Malley |
| [ORC-77](https://issues.apache.org/jira/browse/ORC-77) | Support Snappy, LZO, and LZ4 from aircompressor. |  Major | . | Owen O'Malley | Owen O'Malley |
| [ORC-93](https://issues.apache.org/jira/browse/ORC-93) | remove log message about seeking into an empty stream |  Major | . | Owen O'Malley | Owen O'Malley |
| [ORC-94](https://issues.apache.org/jira/browse/ORC-94) | Remove obsolete MaxPermSize from pom file |  Major | . | Owen O'Malley | Owen O'Malley |
| [ORC-95](https://issues.apache.org/jira/browse/ORC-95) | Fix some missing ASF headers |  Major | . | Owen O'Malley | Owen O'Malley |


