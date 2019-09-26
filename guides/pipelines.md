---
category: Builds
---
# Pipelines

## Builds
Shared libaries are used for the builds, these contain all the standard build steps required (compile, check, test, deploy, test and publish). The skeleton projects contain build files which reference the shared libaries.

When a new project is created from the skeleton projects, the variables in it's build file should be updated and then the repository added to the build servers configuration file (under source control).

Branch builds are enabled, therefore a full build can be tested prior to merging to master.

***Important***

Custom pipelines should not be used, rather the shared build file should be extended.
