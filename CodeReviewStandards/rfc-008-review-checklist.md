# Pull Request Standards

## Summary

A checklist designed to help facilitate code reviews by outlining a pre-review checklist to follow for the raiser of the pull request, and a reviewer checklist.

## Problem

Pull requests follow no set format and vary between projects, which in turn causes reviews to take longer and require more context switching. Code review and commentary often happens 'offline', which results in reduced context and fewer points of reference when reviewing changes later.

## Proposal

Before raising a pull request, the pull request SHOULD meet the following criteria:
 - [ ] Pull request description outlines _what has changed_
 - [ ] Pull request description outlines _why the change was made_
 - [ ] Linting is correct - linter reports no issues
 - [ ] Code follows language specific conventions
 - [ ] Code follows project specific conventions
 - [ ] Code has been refactored with quality and readability in mind
 - [ ] Testing is complete in coverage
 - [ ] Testing strategy meets all requirements
 - [ ] Tests have been refactored for quality
 - [ ] Tests all pass and the change satisfies the goal of _why the change was made_

When reviewing a pull request, reviewer SHOULD consider at least the following questions:

 - [ ] Does the code achieve the goal outlined in _why the change was made_?
 - [ ] Could the change have been implemented using a different strategy that would be a credible alternative? If so, why would the alternative be better?
 - [ ] Does the code follow all of the testing and standards requirements in the pre-review checklist?
 - [ ] Is the code readable?
 - [ ] Is the code maintainable?
 - [ ] Are there any gaps or potential issues to be found in the testing strategy? Are the tests _sane_?

Universal Pull Request Checklist - all pull requests MUST meet the following criteria

- [ ] Before merging, summarise any offline discussion of review comments (why a change may or may not be implemented) to aid future reference
- [ ] SHOULD avoid branching from branches, branch from origin/master where possible
- [ ] SUGGEST commit history can be rebased into a single commit
- [ ] SUGGEST if commit history is too large to rebase into a single commit, multiple pull requests may be desirable
- [ ] Commit messages are descriptive, accurate and spell-checked
- [ ] It is the author of the pull requests responsibility to merge the pull request
- [ ] Pull requests MUST have approval of at least one reviewer before merging
- [ ] After merging, delete the branch