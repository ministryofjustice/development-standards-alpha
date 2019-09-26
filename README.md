# MOJ Digital Probation Software Development

Documents the coding standards and quality control tools proposed for use
as part of the Digital Probation Services, this builds on top of the guidance
provided in the [MOJ technical guidance](https://ministryofjustice.github.io/technical-guidance)

## Getting started

Install Ruby and [Bundler][bundler], preferably with a [Ruby version
manager][rvm].

[rvm]: https://www.ruby-lang.org/en/documentation/installation/#managers
[bundler]: http://bundler.io/

Once you have Ruby and Bundler set up, you can install this project's
dependencies by running the following in this directory:

```bash
bundle install
```

## Previewing

We can preview our changes locally by running this command:

```bash
bundle exec jekyll serve --watch
```

This will create a local web server, probably at http://127.0.0.1:4000
(look for the `Server address:` line). This is only accessible on our
own computer, and won't be accessible to anyone else. It's also set up
to automatically update (thanks to `--watch`) when we make changes to
the working Markdown files.

## Publishing changes

Because we're using GitHub Pages, any changes merged into the `master`
branch will be published automatically. Every change should be reviewed
in a pull request, no matter how minor.
