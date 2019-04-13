---
feature: nixpkgs-workflow
start-date: (fill me in with today's date, YYYY-MM-DD)
author: Matthias Beyer (@matthiasbeyer)
co-authors: (find a buddy later to help our with the RFC)
related-issues: (will contain links to implementation PRs)
---

# Summary
[summary]: #summary

Establish a new workflow for changes to the nixpkgs repository. This workflow is
expected to scale horizontally (more people working with the repository) as well
as vertically (more "domains" are being worked on / more levels of
responsibility).

The workflow proposed in this document is inspired by the linux kernel workflow.


# Motivation
[motivation]: #motivation

Pushing to the master branch of a software development project is not a good
practice in more-than-one-contributor environments.
Security vulnerabilities, breaking changes which are not tested and regressions
are easily introduced this way. which could've been prevented by a proper
workflow.
<!-- TODO: Expand -->

In the last year (as of 2019-04-13), we had

* 17758 commits on the master branch in nixpkgs
* of which 8551 were merges
* of which 9207 where non-merge commits

(use: `git log --oneline --since="1 year ago" --first-parent [--[no-]merges]`)

This means 48.15% of the commits to master where merges and 51.85% were commits
which were done directly to the master branch and thus could potentially
introduce bugs, security vulnerabilities and other changes we do not want in
nixpkgs.

By changing our branching workflow to a no-push-to-master workflow, we can
achieve more security, stability and even more important better scalability.
<!-- TODO: Expand -->


# Detailed design
[design]: #detailed-design

<!-- TODO -->


# Drawbacks
[drawbacks]: #drawbacks

Why should we *not* do this?
<!-- TODO -->

* People are using the right to commit to master, which is their privilege right
  now and they may not like to give that away.


# Alternatives
[alternatives]: #alternatives

What other designs have been considered? What is the impact of not doing this?
<!-- TODO -->

## Impact of not doing this

We already hit 1.700 pull requests at least once. People are overloaded already.
This will get worse, which will result in our progress slowing down eventually.


# Unresolved questions
[unresolved]: #unresolved-questions

What parts of the design are still TBD or unknowns?
<!-- TODO -->


# Future work
[future]: #future-work

What future work, if any, would be implied or impacted by this feature
without being directly part of the work?

