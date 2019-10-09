---
category: Code Standards
---
# Code Commits

## Commit best practice

General guidance on commit messages can be found in the (GDS way commit messages section)[https://gds-way.cloudapps.digital/standards/git.html#commit-messages] and how to style commit messages.
Typically commit messages should:
- A commit should only be for one story
- The first line should have the story number and a title for the change
- Separate subject from the body with a blank line
- Use the body to explain the what and why of the change along with any relevant detail.

### Example

```

#PCS-1234 - Add search functionality to the homepage.

 - This only affects the homepage and has introduced a dependency on Redis to power the search.
 - Added call to search endpoint
 - Used dependency xyz for call
 - Plugged into existing Redis instance

```

## Squishing your commits

Commits should also be squashed before creating a PR, or optionally you can use the squishing merging feature on Github.
