---
category: Builds
---
# Quality and Security Checks
## Linting checks
 - Checkstyle for java
 - ESLint for javascript

[Standards are published here](https://github.com/ministryofjustice/digital-probation-standards/standards/linting-rules/)

## Owasp dependency checks
 - Owasp dependency check is run as part of the build for Java and Javascript projects
 - Any vulnerabilities found should be resolved and/or discussed and the risks considered, particularly if the vulnerability is already live.
 - Builds will automatically fail if critical vulnerabilities are found

## Docker image security analysis
 - The docker container images produced are checked with [Clair](https://github.com/coreos/clair) for any issues
 - Builds will fail if vulnerabilities are found in the base image or configuration
