
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

## Release 2.7.1 - Unreleased

### INCOMPATIBLE CHANGES:

| JIRA | Summary | Priority | Component | Reporter | Contributor |
|:---- |:---- | :--- |:---- |:---- |:---- |


### NEW FEATURES:

| JIRA | Summary | Priority | Component | Reporter | Contributor |
|:---- |:---- | :--- |:---- |:---- |:---- |


### IMPROVEMENTS:

| JIRA | Summary | Priority | Component | Reporter | Contributor |
|:---- |:---- | :--- |:---- |:---- |:---- |
| [YARN-3539](https://issues.apache.org/jira/browse/YARN-3539) | Compatibility doc to state that ATS v1 is a stable REST API |  Major | documentation | Steve Loughran | Steve Loughran |
| [YARN-3469](https://issues.apache.org/jira/browse/YARN-3469) | ZKRMStateStore: Avoid setting watches that are not required |  Minor | . | Jun Gong | Jun Gong |
| [YARN-3193](https://issues.apache.org/jira/browse/YARN-3193) | When visit standby RM webui, it will redirect to the active RM webui slowly. |  Minor | webapp | Japs\_123 | Steve Loughran |
| [YARN-3006](https://issues.apache.org/jira/browse/YARN-3006) | Improve the error message when attempting manual failover with auto-failover enabled |  Minor | . | Akira AJISAKA | Akira AJISAKA |


### BUG FIXES:

| JIRA | Summary | Priority | Component | Reporter | Contributor |
|:---- |:---- | :--- |:---- |:---- |:---- |
| [YARN-3554](https://issues.apache.org/jira/browse/YARN-3554) | Default value for maximum nodemanager connect wait time is too high |  Major | . | Jason Lowe | Naganarasimha G R |
| [YARN-3537](https://issues.apache.org/jira/browse/YARN-3537) | NPE when NodeManager.serviceInit fails and stopRecoveryStore invoked |  Major | nodemanager | Brahma Reddy Battula | Brahma Reddy Battula |
| [YARN-3526](https://issues.apache.org/jira/browse/YARN-3526) | ApplicationMaster tracking URL is incorrectly redirected on a QJM cluster |  Major | resourcemanager, webapp | Weiwei Yang | Weiwei Yang |
| [YARN-3522](https://issues.apache.org/jira/browse/YARN-3522) | DistributedShell uses the wrong user to put timeline data |  Blocker | timelineserver | Zhijie Shen | Zhijie Shen |
| [YARN-3516](https://issues.apache.org/jira/browse/YARN-3516) | killing ContainerLocalizer action doesn't take effect when private localizer receives FETCH\_FAILURE status. |  Minor | nodemanager | zhihai xu | zhihai xu |
| [YARN-3497](https://issues.apache.org/jira/browse/YARN-3497) | ContainerManagementProtocolProxy modifies IPC timeout conf without making a copy |  Major | client | Jason Lowe | Jason Lowe |
| [YARN-3493](https://issues.apache.org/jira/browse/YARN-3493) | RM fails to come up with error "Failed to load/recover state" when  mem settings are changed |  Critical | yarn | Sumana Sathish | Jian He |
| [YARN-3485](https://issues.apache.org/jira/browse/YARN-3485) | FairScheduler headroom calculation doesn't consider maxResources for Fifo and FairShare policies |  Critical | fairscheduler | Karthik Kambatla | Karthik Kambatla |
| [YARN-3476](https://issues.apache.org/jira/browse/YARN-3476) | Nodemanager can fail to delete local logs if log aggregation fails |  Major | log-aggregation, nodemanager | Jason Lowe | Rohith |
| [YARN-3472](https://issues.apache.org/jira/browse/YARN-3472) | Possible leak in DelegationTokenRenewer#allTokens |  Major | . | Jian He | Rohith |
| [YARN-3466](https://issues.apache.org/jira/browse/YARN-3466) | Fix RM nodes web page to sort by node HTTP-address, #containers and node-label column |  Major | resourcemanager, webapp | Jason Lowe | Jason Lowe |
| [YARN-3465](https://issues.apache.org/jira/browse/YARN-3465) | Use LinkedHashMap to preserve order of resource requests |  Major | nodemanager | zhihai xu | zhihai xu |
| [YARN-3464](https://issues.apache.org/jira/browse/YARN-3464) | Race condition in LocalizerRunner kills localizer before localizing all resources |  Critical | nodemanager | zhihai xu | zhihai xu |
| [YARN-3462](https://issues.apache.org/jira/browse/YARN-3462) | Patches applied for YARN-2424 are inconsistent between trunk and branch-2 |  Major | . | Sidharta Seethana | Naganarasimha G R |
| [YARN-3457](https://issues.apache.org/jira/browse/YARN-3457) | NPE when NodeManager.serviceInit fails and stopRecoveryStore called |  Minor | nodemanager | Bibin A Chundatt | Bibin A Chundatt |
| [YARN-3434](https://issues.apache.org/jira/browse/YARN-3434) | Interaction between reservations and userlimit can result in significant ULF violation |  Major | capacityscheduler | Thomas Graves | Thomas Graves |
| [YARN-3385](https://issues.apache.org/jira/browse/YARN-3385) | Race condition: KeeperException$NoNodeException will cause RM shutdown during ZK node deletion. |  Critical | resourcemanager | zhihai xu | zhihai xu |
| [YARN-3382](https://issues.apache.org/jira/browse/YARN-3382) | Some of UserMetricsInfo metrics are incorrectly set to root queue metrics |  Major | webapp | Rohit Agarwal | Rohit Agarwal |
| [YARN-3358](https://issues.apache.org/jira/browse/YARN-3358) | Audit log not present while refreshing Service ACLs |  Minor | resourcemanager | Varun Saxena | Varun Saxena |
| [YARN-3351](https://issues.apache.org/jira/browse/YARN-3351) | AppMaster tracking URL is broken in HA |  Major | webapp | Anubhav Dhoot | Anubhav Dhoot |
| [YARN-3243](https://issues.apache.org/jira/browse/YARN-3243) | CapacityScheduler should pass headroom from parent to children to make sure ParentQueue obey its capacity limits. |  Major | capacityscheduler, resourcemanager | Wangda Tan | Wangda Tan |


### TESTS:

| JIRA | Summary | Priority | Component | Reporter | Contributor |
|:---- |:---- | :--- |:---- |:---- |:---- |


### SUB-TASKS:

| JIRA | Summary | Priority | Component | Reporter | Contributor |
|:---- |:---- | :--- |:---- |:---- |:---- |
| [YARN-3544](https://issues.apache.org/jira/browse/YARN-3544) | AM logs link missing in the RM UI for a completed app |  Blocker | . | Hitesh Shah | Xuan Gong |
| [YARN-3487](https://issues.apache.org/jira/browse/YARN-3487) | CapacityScheduler scheduler lock obtained unnecessarily when calling getQueue |  Critical | capacityscheduler | Jason Lowe | Jason Lowe |
| [YARN-2605](https://issues.apache.org/jira/browse/YARN-2605) | [RM HA] Rest api endpoints doing redirect incorrectly |  Major | resourcemanager | bc Wong | Xuan Gong |


### OTHER:

| JIRA | Summary | Priority | Component | Reporter | Contributor |
|:---- |:---- | :--- |:---- |:---- |:---- |

