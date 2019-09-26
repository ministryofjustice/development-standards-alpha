---
category: Builds
---
# Sonarqube

Sonarqube is used to check code quality, and also monitor code coverage trends over time.

- Sonarqube branch builds are enabled
- Before merging (as the build breaker plugin is not enabled) the sonarqube report for the branch build should be checked to ensure it is not showing red. If so these should be corrected, details of the failure reasons can be seen in sonarqube (code coverage dropped, bugs or code issues).
- If new issues are found or code quality/security issues not currently covered then new rules should be added.
- All reports on code quality that are supported should be fed into sonarqube
- Plugins (such as checkstyle) are not currently used as they are run separately to simplify local checks.
