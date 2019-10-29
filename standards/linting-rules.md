---
category: Code Standards
---
# Linting rules

All projects should be checked against the published linting rules to ensure a consistent developer experience across projects. Both locally during
development and as part of the build, builds should be failed if the linting checks fail. This lets the committer know if their editor is not set up correctly or they have checked in something without the editor autoformatting it, and [encourages reviewers to give more useful feedback](https://technology.blog.gov.uk/2016/09/30/easing-the-process-of-pull-request-reviews/) instead of nitpicking style errors.

Having a chosen style is more important than having the perfect style, since house styles need maintaining and can encourage [bikeshedding](https://en.wikipedia.org/wiki/Law_of_triviality).


## Java Projects
We recommend following the [Google Style Guide](https://google.github.io/styleguide/javaguide.html).
This has formatters which can be imported into [IntelliJ](https://github.com/google/styleguide/blob/gh-pages/intellij-java-google-style.xml) or [Eclipse](https://github.com/google/styleguide/blob/gh-pages/eclipse-java-google-style.xml).

For linting builds, you can use [CheckStyle](https://github.com/checkstyle/checkstyle), which can also be run locally before committing changes. Other static analysis tools for Java include [SonarQube](https://www.sonarqube.org/), [Codacy](https://www.codacy.com/) and [FindBugs](http://findbugs.sourceforge.net/).

To configure checkstyle in Gradle, add the following to your build.gradle:

```groovy
plugins {
    id 'checkstyle'
}
```

Then add your chosen configuration to `config/checkstyle/checkstyle.xml`:

- [Google style config](https://github.com/checkstyle/checkstyle/blob/master/src/main/resources/google_checks.xml)
- [Modified Sun style config](https://github.com/ministryofjustice/development-standards-alpha/blob/master/resources/checkstyle.xml)

The latter is the Java sun checkstyle rule with slight alterations around Javadoc checks, hidden fields and line length.

Checkstyle configurations can also be imported into IntelliJ, eclipse and netbeans using their CheckStyle plugins, which will show any warnings and format automatically.

## Javascript Projects
Should be checked as part of the build using [ESLint](https://eslint.org) which is available as node module, the Airbnb style is used and this module [eslint-config-airbnb-base](https://www.npmjs.com/package/eslint-config-airbnb-base) should be used on all projects. A coding style for the IntelliJ IDE is available [here](https://github.com/ministryofjustice/digital-probation-standards/resources/Webstorm-Airbnb-Javascript-codeStyle.xml)

## Introducing a code style to existing projects
Introducing a new coding convention to an existing project will flag up a lot of violations.

It's simplest to fix these in one go, when there are not many other branches being worked on.

`git rebase -Xignore-space-change master` is a helpful command for resolving conflicts with branches if the whitespace conventions have changed.
