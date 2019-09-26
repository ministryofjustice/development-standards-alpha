---
category: Code Standards
---
# Code Commits

Commits should be squashed prior to creating a PR, commits must have an associated
story, ideally a story should be represented in only a single commit. The commit should also include full test coverage.

The commit comment should take the format of story number, story title, a brief description and any other relevant points.

**Example:**

 #PCS-1234
 Add search functionality to homepage. This only affects the homepage and has introduced a dependency on Redis to power the search.
 - Added call to search endpoint
 - Used dependency xyz for call
 - Plugged into existing Redis instance
