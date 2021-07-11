# Conventional Commit Messages

## Table of Contents

- [Conventional Commit Messages](#conventional-commit-messages)
  - [Table of Contents](#table-of-contents)
  - [Summary](#summary)
  - [Commit Format](#commit-format)
  - [Example](#example)
  - [Specifications](#specifications)
    - [Types](#types)
    - [Scopes](#scopes)
    - [Description](#description)
    - [Body](#body)
    - [Issue id](#issue-id)
    - [Breaking change](#breaking-change)
  - [References](#references)

## Summary

The Conventional Commit Messages specification is a lightweight convention on top of commit messages. It provides an easy set of rules for creating an explicit commit history. This convention dovetails with [SemVer](https://semver.org/), by describing the features, fixes, and breaking changes made in commit messages.

## Commit Format

```bash
<type>[optional <scope>]: <description>

[optional <body>]

[optional <issue reference>: <issue id>]

[optional <breaking change>]
```

## Example

A simple commit utilising only the core components of the conventional commit format:

```bash
feat: add profile page dropdown menu on navbar
```

A more descriptive commit:

```bash
feat(view): add profile page dropdown menu

Add dropdown menu to navbar, to display user profile picture, profile link and logout button

Closes: #0234
```

A full example, utilising every part of the conventional commit format:

```bash
feat!(view): add profile page dropdown menu

Add dropdown menu to navbar, to display user profile picture, profile link and logout button

Add one new dependency, `font-awesome`, use `npm install` to update packages

Closes: #0234

BREAKING CHANGE:

Function navDropdown() change to navDropdownMenu(), so that it is consistent with the naming convention

To migrate, change all navDropdown() function calls to navDropdownMenu()
```

## Specifications

### Types

The `type` spceifies what kind of changes were made in the commit.

- `feat` adds a new feature
- `fix` fixes a bug
- `refactor` rewrite/restructure code, however does not change any behaviour
- `perf` rewrite code to improve performance, but does not change behavior
- `style` white-space/formatting/missing semi-colons/typo changes
- `remove` a previosus feat or segment of code was removed
- `test` add missing tests or correcting existing tests
- `docs` add or fix documentation
- `build` affect build components like build tool, ci pipeline, dependencies, project version
- `ops` affect operational components like infrastructure, deployment, backup, recovery
- `chore` updating grunt tasks, no production code change

### Scopes

The `scope` provides additional contextual information to the commit massage.

- is **optional**
- allowed scopes depend on the specific project
- **don't** use issue identifiers as scopes

### Description

The `description` contains a succinct description of the change.

- use the imperative, present tense: "**change**" not "*changed*" nor "*changes*"
- don't capitalize the first letter
- no dot `.` at the end

### Body

The `body` should include the motivation for the change and contrast this with previous behavior.

- is **optional**
- use the imperative, present tense

### Issue id

The `issue id` is the place to **reference Issues** that this commit refers to

- is **optional**
- start with the issue reference: either `Issue:`, `Closes:` or `Fixes:`, based on the issue type
- reference an issue by its `id`

### Breaking change

The `breaking change` should contain any information about **Breaking Changes**

- is **mandatory** if breaking change is present
- if a breaking change is present you should identify it with a `!` after the `type`
- **Breaking Changes** should start with the word `BREAKING CHANGES:` followed by a new line, the rest of the commit massage is used to specify the breaking change
- use the imperative, present tense

## References

- [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/)
- [Angular Contribution guide](https://github.com/angular/angular/blob/master/CONTRIBUTING.md#-commit-message-format)
