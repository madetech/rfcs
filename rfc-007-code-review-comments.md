# Code Review Comment Keywords

## Summary

Introduce specific keywords to use in code review comments to help convey intention and foster discussion.

## Problem

When leaving code review comments, the default is to only comment in situations where the code _must_ change, meaning some useful and valid comments are not added to the pull request (though will likely be discussed).
The proposed keywords allow reviewers to leave comments with more descriptive intention, and allows engineers to easily interpret the sentiment of the comment.

## Proposal

In keeping with the [RFC2119-style](https://www.ietf.org/rfc/rfc2119.txt), reviewers MUST use one and only one of the following keywords as part of the review comment:

- SUGGEST : Denotes that the reviewer would prefer this change, or feels the comment describes a preferable way of writing a particular code item, but making the change is not integral to functionality or maintainability.

Example: 'Suggest changing text of this exception from _abc_ to _xyz_ as it may be more useful to the end user'
- SHOULD : Denotes a change the reviewer would like to see, as they feel it is beneficial to the codebase but is open to discussion if the author feels there is a justifiable reason not to implement the change, or there are external factors to be considered.

Example: 'This function is now getting long and implementing behaviour outside of intended scope, _foobar_ should be split into _foo_ and _bar_.'
- MUST : Denotes a comment highlighting a change critical to the program's operation or maintainability, which must be implemented before the review can be approved without proper justification of why not.

Example: 'This test does not cover a common case where _xyz_, must implement a test case covering this.'

Final note - All reviews and comments are written in good faith and all comments are already implemented with thought and respectful, insightful discussion. This does not need to change, the keywords are simply to help facilitate discussion and clarify language we already use, with the main goal being to empower reviewers to leave comments they feel are helpful in a way that does not drag out the review process.
