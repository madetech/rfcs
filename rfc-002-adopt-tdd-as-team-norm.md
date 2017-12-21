# Adopt TDD as a Team Norm

## Summary

Adopt the discipline of TDD (Test Driven Development) as a [team norm](https://github.com/madetech/handbook#team-norms).

## Problem

Ensuring a codebase has test coverage ensures that a codebase is evolvable and maintainable.

We want to ensure the software we write is flexible to the changing needs of our customers.

There is a general acceptance that TDD, or test first development, is a positive trait of a mature delivery team.
Currently, there is no explicit promise (a "team norm") that stipulates that we must practice Test Driven Development.

Also, we want to be explicit about the definition of TDD (and stand it apart from Test First Development).

## Proposal

Members of a Delivery Team MUST practice Test Driven Development, unless explicitly agreed by AT LEAST one other Made Tech Engineer. 

Agreements to not practice Test Driven Development MUST only be made in extenuating circumstances.

Test Driven Development is defined as a discipline with three rules:

1. You MUST write a failing test before you write any production code.
2. You MUST not write more of a test than is sufficient to fail, or fail to compile.
3. You MUST not write more production code than is sufficient to make the currently failing test pass.

TDD relies on quick feedback cycles, therefore Delivery Teams SHOULD make it possible to run individual test suites within the ecosystem of an application in under 30 seconds. Furthermore, it SHOULD be possible to run the test suites of an entire application in under 5 minutes. If this time limit is exceeded, Delivery Teams SHOULD plan in effort to reduce test suite run times. 

Any code that cannot be automatically tested i.e. code that applies visual styles to a UI, SHOULD NOT be tested or TDD'ed.

You MAY choose to not TDD any code which does not get more generic as you write more specific tests e.g. application configuration, state machines, etc. This code MUST still be tested for regression purposes.

Server-side rendered UI MUST be covered by automated regression tests, but you MAY choose to not TDD this code.
