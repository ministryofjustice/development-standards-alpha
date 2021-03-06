---
category: Code Standards
---
# Branching Strategies

We suggest using a feature branching strategy where you work on one story or task per branch.

A common prefix can be useful for categorising branches, and working with tools
for continuous integration. Naming branches such as `feature/foo`,
`feature/bar`, and `bug/fix-column-migration` can help other people in the team
understand whether it's a feature (new behaviour) or a fixing a bug. Having a
common prefix can also work well with continuous integration tools such as
[Travis][travis], which might be
[instructed to only do certain actions on branches](https://docs.travis-ci.com/user/customizing-the-build/#Using-regular-expressions)
named `feature/*` versus the `master` branch.

Other approaches:

* `feature/{JIRA-issue}-{description}` – this change is for the Jira issue
  LM-6, and also has a human-readable description to give people more context.
  Also, one or more people might be working on this branch (pairing, or
  separately)
* `jabley/thing` – this branch contains work that developer known as jabley is
  doing. Other people might not want to rely on this branch, since it might be
  force-pushed (but nicely please!)

## Commit locally regularly

This can help to get to the point where you have a working version, and then
want to try adding a new thing. Try to aim for each [commit](https://www.git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository)
to be an atomic unit that delivers a non-broken version of the code-base. As
you make more changes, consider whether it should be separate commit, or an
amendment to the last one. You can always
[interactively rebase your changes](https://git-scm.com/book/en/v2/Git-Tools-Rewriting-History)
to edit the commit history to a logical changeset.

## Push your changes regularly

This protects you from local hardware failure, and
[ensures you don't lose your changes](https://www.git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes#_pushing_remotes).

## Common problems with feature branching

One of the main issues with branching strategies is that it can prevent code being regularly integrated:

- Spending days in isolation can make integration testing complicated
- Extensive code reviews can be laborious
- Significant new features can be complicated to role out
- A merged feature that is in testing could prevent things like hotfixes being applied to production
- Merge conflicts

## Mitigating the problems with feature branching

Using in-code strategies such as **feature toggles**, **UI last**, **splitting features into multiple deployments** and **reversible deployments** can help mitigate some of the problems with feature branching.

### Feature toggles

Using in code configuration to turn features on and off

### Splitting features into multiple deployments
Where possible, deploy things in multiple stages so that if stuff breaks you can quickly identify the problem and fix it.

This way you can integrate stuff into the master branch quicker and get feedback on your work earlier.

If a branch becomes difficult to review because of a large number of commits, consider whether any of that work can be deployed in isolation. If so, then you can [cherry-pick](https://git-scm.com/docs/git-cherry-pick) changes into new, smaller feature branches.

### UI last
With significant changes to API endpoints, you could create a new endpoint instead of editing the existing one; same could be applied to a UI change where you could copy a page, make your changes and tie it all together at the end when you're ready to release the change to users.

### Make deployments reversable
You should be able to safely rollback any deployment.

This can be tricky when data is involved. For example, if you drop a column in your database as part of a larger code change, then the previous version of the code won't work properly, so your deploy will require downtime, and you won't be able to roll back if the build doesn't work.

The safest way to make these kind of changes is in stages, e.g.
- https://www.brunton-spall.co.uk/post/2014/05/06/database-migrations-done-right/
- https://stripe.com/gb/blog/online-migrations
- https://samsaffron.com/archive/2018/03/22/managing-db-schema-changes-without-downtime
