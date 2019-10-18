---
category: Code Standards
---
# Branching Strategies

We suggest using a feature branching strategy where you work on one story or task per branch, the structure of the feature branch should consist of a story or task id and short title, for example: 

```
feature/T918-Some-short-title
```

## Some problems with feature branching

One of the main issues with branching strategies is that it can prevent code being regularly integrated: 

- Spending days in isolation can make integration testing complicated
- Extensive code reviews can be laborious
- Significant new features can be complicated to role out
- A merged feature that is in testing could prevent things like hotfixes being applied to production
- Marge conflicts

## Mitigating the problems with feature branching 

Using in-code strategies such as **feature toggles** and **UI last** can help mitigate some of the problems with feature branching.

### Feature toggles

Using in code configuration to turn features on and off 

### UI last

With significant changes to API endpoints, you could create a new endpoint instead of editing the existing one; same could be applied to a UI change where you could copy a page, make your changes and tie it all together at the end when you're ready to deploy.