---
category: Code Standards
---
# Java Language Conventions

## Code style
Teams should adopt a consistent coding style, and use tooling to automatically check
that it is being followed.

We recommend following the [Google Style Guide](https://google.github.io/styleguide/javaguide.html).
This has formatters which can be imported into [IntelliJ](https://github.com/google/styleguide/blob/gh-pages/intellij-java-google-style.xml) or [Eclipse](https://github.com/google/styleguide/blob/gh-pages/eclipse-java-google-style.xml).

Having a chosen style is more important than having the perfect style, since house styles need maintaining and can encourage [bikeshedding](https://en.wikipedia.org/wiki/Law_of_triviality).

You should also run a static analysis tool as part of your CI build - this will let the committer know straight away if their IDE is not set up correctly or they have checked in something without the IDE autoformatting it. This allows the reviewer of the PR to focus on the actual changes. Static analysis tools for Java include [SonarQube](https://www.sonarqube.org/), [Codacy](https://www.codacy.com/), [FindBugs](http://findbugs.sourceforge.net/) and [CheckStyle](http://checkstyle.sourceforge.net/).

### Introducing a code style to existing projects
Introducing a new coding convention to an existing project will flag up a lot of violations.

It's simplest to fix these in one go, when there are not many other branches being worked on.

`git rebase -Xignore-space-change master` is a helpful command for resolving conflicts with branches if the whitespace conventions have changed.

## JDK
New versions of OpenJDK are released on a 6 monthly cycle. You should choose an up to date JDK and continue updating your JDK to keep pace with new releases. Not updating makes it harder to update in the future.

OpenJDK is developed by Oracle but [distributed by other vendors](https://en.wikipedia.org/wiki/OpenJDK#OpenJDK_builds). Make sure you understand how long that vendor supports the version you are using.

Oracle offers two builds of OpenJDK: a commercial build and a [free to use, open source build](https://jdk.java.net/) (under the GPLv2 with the Classpath Exception). The commercial build requires an Oracle licence to run in production, and Oracle only provide an open source build of the most recent version.

The [AdoptOpenJDK](https://adoptopenjdk.net/) project (backed by big names including IBM and Microsoft) provides fully open-source pre-built OpenJDK binaries. For LTS releases (such as Java 8 and Java 11), AdoptOpenJDK have committed to releasing free updates for several years.

In addition, AdoptOpenJDK has niceties such as being available in package repositories, having friendly installers for desktop use, and offering ready-made [Docker images containing OpenJDK](https://hub.docker.com/u/adoptopenjdk).

## Prefer functionality in the Java standard library

Where possible, use functionality from the Java standard library rather than external libraries.

Be mindful that improvements to the Java standard library mean that some external libraries that were popular in the past now add less value. For example, while Joda-Time was significantly better than the date and time libraries built in to older Java versions, the `java.time` package introduced in Java 8 renders it redundant. Similarly, [Google’s Guava](https://github.com/google/guava) is very useful (and recommended) but the unmodifiable collections built in to Java 9 largely obviate the need for Guava’s immutable collections.

When using external libraries, favour those that play nicely with the Java standard library. For example, be wary of any library that introduces a new type that replicates the functionality of an existing type in the Java standard library without implementing the same interfaces (e.g. a list type that does not implement `java.util.List`).

## Fix compiler warnings
Try to minimise compiler warnings. If you cannot remove a warning, use an appropriate annotation to suppress it, preferably with a comment explaining why. For example:

```java
public void frobulateFoos() {
    LOGGER.info("Frobulating foos");

    // LibFoo returns a raw list but every element is always a Foo
    @SuppressWarnings("unchecked")
    List<Foo> foos = (List<Foo>) fooService.getFoos();

    foos.forEach(foo -> foo.frobulate());
}
```

## See also
- [Tech menu](/guides/tech-menu)
- [Skeleton Projects - Java](/standards/skeleton-projects#java)
