# Core Developer Guide

Welcome, new core developer!  The core team appreciate the quality of
your work, and enjoy working with you; we have therefore invited you
to join us.  Thank you for your numerous contributions to the project
so far.

You can see a list of all the current core developers on our
[@zarr-developers/core-devs](https://github.com/orgs/zarr-developers/teams/core-devs)
GitHub team. You should now be on that list too.

This document offers guidelines for your new role.
As a core team member, you gain the responsibility of shepherding
other contributors through the review process; here are some
guidelines for how to do that.

## All Contributors Are Treated The Same

As a core developer, you gain the ability to approve and merge
other contributors' pull requests.  Much like nuclear launch keys, it
is a shared power: see [Reviewing](#reviewing) and especially
[Merge Only Changes You Understand](#merge-only-changes-you-understand) below.
It should also be considered best practice to leave a reasonable (24hr) time window
after approval before merge to ensure that other core developers have a reasonable
chance to weigh in.

You may of course also continue to make your own pull requests as before and in accordance
with the [general contributor guide](https://github.com/zarr-developers/.github/blob/main/CONTRIBUTING.md).
These pull requests require the approval of another core developer before they can be merged.

We are also an international community, with contributors from many different time zones,
some of whom will only contribute during their working hours, others who might only be able
to contribute during nights and weekends. It is important to be respectful of other peoples
schedules and working habits, even if it slows the project down slightly - we are in this
for the long run. In the same vein you also shouldn't feel pressured to be constantly
available or online, and users or contributors who are overly demanding and unreasonable
to the point of harassment will be directed to our
[Code of Conduct](https://github.com/zarr-developers/.github/blob/main/CODE_OF_CONDUCT.md).
We value sustainable development practices over mad rushes.

When merging, use GitHub's
[Squash and Merge](https://help.github.com/articles/merging-a-pull-request/#merging-a-pull-request-on-github)
to ensure a clean git history.

## Reviewing

### How to Conduct A Good Review

*Always* be kind to contributors. Contributors are often doing
volunteer work, for which we are tremendously grateful. Provide
constructive criticism on ideas and implementations, and remind
yourself of how it felt when your own work was being evaluated as a
novice.

`Zarr` strongly values mentorship in code review.  New users
often need more hand-holding, having little to no git
experience. Repeat yourself liberally, and, if you don't recognize a
contributor, point them to our development guide, or other GitHub
workflow tutorials around the web. Do not assume that they know how
GitHub works (many don't realize that adding a commit
automatically updates a pull request, for example). Gentle, polite, kind
encouragement can make the difference between a new core developer and
an abandoned pull request.

When reviewing, focus on the following:

1. **Usability and generality:** `Zarr` is a library that strives to be accessible
to both coding and non-coding users, and new features should ultimately be
accessible to everyone using the app. `Zarr` targets the scientific user
community broadly, and core features should be domain-agnostic and general purpose.
Custom functionality is meant to be provided through our plugin ecosystem.

2. **Performance and benchmarks:** As `Zarr` targets scientific applications that often involve
large multidimensional datasets, high performance is a key value of `Zarr`. While
every new feature won't scale equally to all sizes of data, keeping in mind performance
during a review may be important, and you may
need to ask for benchmarks to be run and reported or new benchmarks to be added.

3. **APIs and stability:** Coding users and plugin developers will make
extensive use of our APIs. The foundation of a healthy ecosystem will be
a fully capable and stable set of APIs, so it is important 
important to ensure our APIs are stable.

4. **Documentation and tutorials:** All new methods should have appropriate doc
strings following [PEP257](https://www.python.org/dev/peps/pep-0257/) and the
[NumPy documentation guide](https://docs.scipy.org/doc/numpy/docs/howto_document.html).
For any major new features, accompanying changes should be made to our
[tutorials repository](https://github.com/zarr-developers/zarr-developers-tutorials), that not only
illustrates the new feature, but explains it.

5. **Implementations and algorithms:** You should understand the code being modified
or added before approving it.  (See [Merge Only Changes You Understand](#merge-only-changes-you-understand)
below.) Implementations should do what they claim and be simple, readable, and efficient
in that order.

6. **Tests:** All contributions *must* be tested, and each added line of code
should be covered by at least one test. Good tests not only execute the code,
but explore corner cases.  It can be tempting not to review tests, but please
do so.

Other changes may be *nitpicky*: spelling mistakes, formatting,
etc. Do not insist contributors make these changes, but instead you should offer
to make these changes by [pushing to their branch](https://help.github.com/articles/committing-changes-to-a-pull-request-branch-created-from-a-fork/), or using GitHub’s [suggestion](https://help.github.com/articles/commenting-on-a-pull-request/)
[feature](https://help.github.com/articles/incorporating-feedback-in-your-pull-request/), and
be prepared to make them yourself if needed. Using the suggestion feature is preferred because
it gives the contributor a choice in whether to accept the changes.

Unless you know that a contributor is experienced with git, don’t
ask for a rebase when merge conflicts arise. Instead, rebase the
branch yourself, force-push to their branch, and advise the contributor to force-pull.  If the contributor is
no longer active, you may take over their branch by submitting a new pull
request and closing the original, including a reference to the original pull
request. In doing so, ensure you communicate that you are not throwing the
contributor's work away!

### Merge Only Changes You Understand

*Long-term maintainability* is an important concern.  Code doesn't
merely have to *work*, but should be *understood* by multiple core
developers.  Changes will have to be made in the future, and the
original contributor may have moved on.

Therefore, *do not merge a code change unless you understand it*. Ask
for help freely: we can consult community members, or even external developers,
for added insight where needed, and see this as a great learning opportunity.

While we collectively "own" any patches (and bugs!) that become part
of the code base, you are vouching for changes you merge.  Please take
that responsibility seriously.

## Further resources

As a core member, you should be familiar with community and developer
resources such as:

-  Our [contributor guide](https://github.com/zarr-developers/.github/blob/main/CONTRIBUTING.md).
-  Our [code of conduct](https://github.com/zarr-developers/.github/blob/main/CODE_OF_CONDUCT.md).
-  Our [governance](GOVERNANCE.md).
-  [PEP8](https://www.python.org/dev/peps/pep-0008/) for Python style.
-  [PEP257](https://www.python.org/dev/peps/pep-0257/) and the
   [NumPy documentation guide](https://docs.scipy.org/doc/numpy/docs/howto_document.html)
   for docstring conventions.
-  [`pre-commit`](https://pre-commit.com) hooks for autoformatting.
-  [`black`](https://github.com/psf/black) autoformatting.
-  [`flake8`](https://github.com/PyCQA/flake8) linting.
-  [#zarr_dev](https://twitter.com/search?q=%23zarr_dev&f=live) on twitter.

You are not required to monitor the social resources.

Where possible we prefer to point people towards asynchronous forms of communication
like forum posts and github issues instead of realtime chat options as they are easier
for a global community to consume.

We also make use of private messages via the GitHub team (@zarr-developers/core-devs)
sparingly for discussions that are required to be private, such as voting on new core members.

## Inviting New Core Members

Any core member may nominate other contributors to join the core team.
While there is no hard-and-fast rule about who can be nominated, ideally,
they should have: been part of the project for at least two months, contributed
significant changes of their own, contributed to the discussion and
review of others' work, and collaborated in a way befitting our
community values. After nomination voting will happen on a private mailing list.
While it is expected that most votes will be unanimous, a two-thirds majority of
the cast votes is enough.

Core developers can choose to become emeritus core developers and suspend
their approval and voting rights until they become active again.

## Contribute To This Guide!

This guide reflects the experience of the current core developers.  We
may well have missed things that, by now, have become second
nature—things that you, as a new team member, will spot more easily.
Please ask the other core developers if you have any questions, and
submit a pull request with insights gained.

## Conclusion

We are excited to have you on board!  We look forward to your
contributions to the code base and the community.  Thank you in
advance!
