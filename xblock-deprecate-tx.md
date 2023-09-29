## Breaking change!

This change breaks the Jenkins transifex integration which has been deprecated in favor of the new GitHub Transifex App integration as part of [OEP-58](https://open-edx-proposals.readthedocs.io/en/latest/architectural-decisions/oep-0058-arch-translations-management.html#specification).

## Changes

 - Removes direct use of `tx pull` and `tx push` commands from the [XBlock to let Open edX manage it](https://github.com/openedx/edx-platform/pull/33166).
 - Remove source and language translations from the repositories, hence no `.po` or `.mo` files will be committed into the repos. 
 - Remove Transifex related `Makefile` targets and configuration files.

Merge timeline
-----------------------

This should only be merged after [Translation Infrastructure update OEP-58](https://open-edx-proposals.readthedocs.io/en/latest/architectural-decisions/oep-0058-arch-translations-management.html#specification) is fully implemented.

The timing announcement will be shared by @brian-smith-tcril on [#translations-project-fc-0012](https://openedx.slack.com/archives/C04R6TUJB7T) Open edX Slack channel.

Keep this pull request as a draft to prevent accidental merge.

### Pre-merge checklist


 - [ ] Wait for approval on https://github.com/openedx/wg-translations/issues/20

References
----------

This contribution is part of the [FC-0012 project](https://openedx.atlassian.net/l/cp/XGS0iCcQ) which is sparked by the [Translation Infrastructure update OEP-58](https://open-edx-proposals.readthedocs.io/en/latest/architectural-decisions/oep-0058-arch-translations-management.html#specification).

Up-to-date project overview and details are available in the [Approach Memo and Technical Discovery: Translations Infrastructure Implementation](https://docs.google.com/document/d/11dFBCnbdHiCEdZp3pZeHdeH8m7Glla-XbIin7cnIOzU/edit#) document.

Join the conversation on [Open edX Slack #translations-project-fc-0012](https://openedx.slack.com/archives/C04R6TUJB7T).

Check the links above for full information about the overall project.
