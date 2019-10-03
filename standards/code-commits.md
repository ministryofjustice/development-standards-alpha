---
category: Code Standards
---
# Code Commits

## Commit best practice

Commit messages should follow the suggest best-suggested practice: 

- Separate subject from the body with a blank line
- Limit the subject line to 50 characters
- Capitalize the subject line
- Do not end the subject line with a period
- Use the imperative mood in the subject line, for example Update dependencies to latest version.
- Wrap the body at 72 characters
- Use the body to explain what and why vs how

## Squishing your commits

Commits should also be squashed before creating a PR, or optionally you can use the squishing merging feature on Github. 

## Commit message structure

The commit comment should take the format of story number, story title, a brief description and any other relevant points.

### Example

```

#PCS-1234 - Add search functionality to the homepage. 

 - This only affects the homepage and has introduced a dependency on Redis to power the search.
 - Added call to search endpoint
 - Used dependency xyz for call
 - Plugged into existing Redis instance

```

## Further reading

 - [How to write a Git commit message](https://chris.beams.io/posts/git-commit/)
 - [Squash your commits](https://github.blog/2016-04-01-squash-your-commits/) 
