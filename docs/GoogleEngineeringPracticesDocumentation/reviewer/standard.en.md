---
comments: true
---

# Code Review Standards

The primary purpose of code review is to make sure that the overall code health
of Google's codebase is improving over time. All of the tools and processes of
code review are designed to this end.

To accomplish this, we need to balance a few competing concerns:

First, developers must be able to make progress on their tasks. If you never
submit improvements to the codebase, the codebase never improves. If you block
all changes, then developers can't make progress.

On the other hand, the reviewer is responsible for ensuring the codebase's
quality doesn't decrease, which is actually quite difficult. Any change will
introduce some risk of decreasing code quality, and the reviewer is responsible
for catching and preventing that. And code quality tends to degrade over time
if we're not diligent about preventing it, especially when teams are working
under time pressure and they feel like they have to take shortcuts to meet
their deadlines.

However, the reviewer is responsible for the code they review, so they want to
ensure that each CL is improving the codebase's overall health, even if the
improvement is small.

Based on this, we get the following standard for code review:

**In general, reviewers should favor approving a CL once it is in a state where
it definitely improves the overall code health of the system being worked on,
even if the CL isn't perfect.**

This is the *primary* standard that all other code review guidelines are based
on.

There are some limitations to this. For example, if a CL adds a feature that
the reviewer doesn't want in their system, then the reviewer can reject it
even if the code is well-designed.

The key point is that there's no such thing as "perfect" code—only *better*
code. The reviewer's job is to push the change toward better rather than
perfect. A CL that improves the maintainability, readability, and
understandability of the system should not be delayed for days or weeks
because it isn't "perfect."

Reviewers should *always* leave comments asking for improvements that they
think would be nice to have, but if those improvements aren't important
enough to block submission, they should prefix their comment with "Nit:" to
let the author know that it's optional.

Note: Nothing in this document justifies checking in CLs that definitely make
the system's code health worse. You can only do this in [emergencies](../emergencies.md).

## Mentoring {#mentoring}

Code review has an important function in teaching developers something about
the language, framework, or general software design principles. It's always
OK to leave comments that help a developer learn something new. Sharing
knowledge is part of improving the codebase's long-term health.

However, if your comment is purely educational and isn't critical to meeting
the standards described in this document, prefix it with "Nit:" so the author
knows it's not blocking submission.

## Principles {#principles}

- **Technical facts and data overrule opinions and personal preferences.**
- On matters of style, the [style guide](http://google.github.io/styleguide/)
    is the absolute authority. Any purely stylistic point (whitespace, etc.)
    that isn't covered by the style guide is a matter of personal preference.
    The style should be consistent with what's already there. If there's no
    previous style, accept the author's.
- **Aspects of software design are almost never purely a matter of style or
    personal preference.** They are based on principles and should be weighed
    on those principles, not personal opinions. Sometimes there are several
    valid options. If the author can demonstrate (either through data or
    based on solid engineering principles) that several approaches are equally
    valid, then the reviewer should accept the preference of the author.
    Otherwise the choice is dictated by standard principles of software design.
- If no other rule applies, the reviewer may ask the author to be consistent
    with what's already in the codebase, as long as that doesn't worsen the
    codebase's overall health.

## Resolving Conflicts {#conflicts}

When you run into conflicts in code review, the first step should always be
for the developer and reviewer to try to come to consensus based on the
content of the [CL Author's Guide](../developer/) and [Reviewer Guide](index.md)
and the other documents in this series.

When it's difficult to come to consensus, it's time for a face-to-face meeting
or a design review. Don't let code review discussions go on for too long.
After one or two round-trips, if consensus hasn't been reached, the
escalation process should begin. This usually involves a team lead, a
maintainer, or a meeting with the team. **Don't let CLs sit around for days
waiting for the developer and reviewer to come to agreement.**

Next: [What to Look For In a Code Review](looking-for.md)
