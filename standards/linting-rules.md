---
category: Code Standards
---
# Linting rules

All projects should be checked against the published linting rules to ensure a consistent developer experience across projects. Both locally during
development and as part of the build, builds should be failed if the linting checks fail.

## Java Projects

Should be checked as part of the build using [checkstyle](https://github.com/checkstyle/checkstyle) this can also be run locally using [this configuration file](https://github.com/ministryofjustice/digital-probation-standards/resources/checkstyle.xml) which is the Java sun checkstyle rule with slight alterations around Javadoc checks, hidden fields and line length.
The [configuration file](https://github.com/ministryofjustice/digital-probation-standards/resources/checkstyle.xml) can also be imported into IntelliJ, eclipse and netbeans using their CheckStyle plugins, which will show any warnings and format automatically.

## Javascript Projects
Should be checked as part of the build using [ESLint](https://eslint.org) which is available as node module, the Airbnb style is used and this module [eslint-config-airbnb-base](https://www.npmjs.com/package/eslint-config-airbnb-base) should be used on all projects. A coding style for the IntelliJ IDE is available [here](https://github.com/ministryofjustice/digital-probation-standards/resources/Webstorm-Airbnb-Javascript-codeStyle.xml)
