
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
# Apache Yetus  0.10.0 Release Notes

These release notes cover new developer and user-facing incompatibilities, important issues, features, and major improvements.


---

* [YETUS-782](https://issues.apache.org/jira/browse/YETUS-782) | *Major* | **Remove ruby-lint support**

Support for ruby-lint has been removed as the tool is no longer supported.  Instead, use rubocop.


---

* [YETUS-688](https://issues.apache.org/jira/browse/YETUS-688) | *Major* | **convert key globals from strings to arrays**

<!-- markdown -->
For developers, the various `yetus_*_entry` routines have been removed form yetuslib.  There were a lot of issues with duplicate names and other problems that really made them hard to use.  All of those routines and the variables that used them have been replaced with equivalent routines and variables that are array-based.


---

* [YETUS-474](https://issues.apache.org/jira/browse/YETUS-474) | *Blocker* | **Option to releasedocmaker to write empty files when no JIRA issues match**

<!-- markdown -->
releasedocmaker now has a `--empty` flag to allow the creation of release notes when there are no JIRAs assigned to a version.


---

* [YETUS-801](https://issues.apache.org/jira/browse/YETUS-801) | *Major* | **Remove deprecated private token support from Github**

<!-- markdown -->
The `--github-token` option has been removed from precommit. (Github has removed support private token support from Github and Github Enterprise.)


---

* [YETUS-807](https://issues.apache.org/jira/browse/YETUS-807) | *Major* | **SemaphoreCI Support**

<!-- markdown -->
Precommit now has some preliminary support for Semaphore CI.


---

* [YETUS-819](https://issues.apache.org/jira/browse/YETUS-819) | *Major* | **Azure Pipelines Support**

Precommit now has some preliminary support for Azure Pipelines. Note that artifact links and Docker are unsupported.


---

* [YETUS-809](https://issues.apache.org/jira/browse/YETUS-809) | *Blocker* | **findbugs isn't finding bugs in qbt-mode**

<!-- markdown -->
Previously, if the findbugs plug-in was given a parent module with no source code but children modules did have source code, findbugs would ignore the whole directory.  This has been fixed such that all reports generated by children of a parent module are merged and generated as a report of the parent.


---

* [YETUS-749](https://issues.apache.org/jira/browse/YETUS-749) | *Major* | **change findbugs to spotbugs**

<!-- markdown -->
Precommit now includes specific support for SpotBugs.  Note that only one of FindBugs or SpotBugs may be enabled.  By default, SpotBugs will disable FindBugs automatically.  To specifically pick one or the other, use the `--plugins` control. For example:

```
---plugins=all,-findbugs
```

will disable FindBugs whereas

```
--plugins=all,-spotbugs
```

will disable SpotBugs.

The SpotBugs plug-in requires the SPOTBUGS_HOME environment variable to be defined.  It should point to the location where SpotBugs has been installed.


---

* [YETUS-724](https://issues.apache.org/jira/browse/YETUS-724) | *Major* | **github diff vs. patch**

<!-- markdown -->
precommit will now attempt to try both forms of git patches (binary format-patch and ASCII git diff) when working with Github PRs or Gitlab MRs. It will prefer the format-patch style due to accuracy, but will fallback to diff style if the former does not apply successfully.



