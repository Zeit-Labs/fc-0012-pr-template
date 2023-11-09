## Breaking change!

This change breaks the Jenkins transifex integration which has been deprecated in favor of the new GitHub Transifex App integration as part of [OEP-58](https://open-edx-proposals.readthedocs.io/en/latest/architectural-decisions/oep-0058-arch-translations-management.html#specification).

## Changes

 - Removes all direct use of `tx pull` and `tx push` commands from the micro-frontend in favor
of the [`atlas pull`](https://github.com/openedx/openedx-atlas/) command.
 - Remove source and language translations from the repositories, hence no `.json` files will be committed into the repos. 
 - `src/i18n/index.js` should export and empty array so the `make pull_translations` override it with the dynamic list of languages.
 - Remove the experimental `OPENEDX_ATLAS_PULL` flag to make `atlas pull` the default. 
 - Remove all Transifex related `Makefile` targets and other files.

Test results
------------

 - [ ] Verify that `make pull_translations` works as expected.

<details><summary>make pull_translations test results</summary>

```
# I've run the following commands:
$ make requirements
$ make pull_translations
$ git diff

# Output of the commmands:

<PASTE YOUR OUTPUT HERE>

```

</details> 


Merge timeline
-----------------------

This should only be merged after [Translation Infrastructure update OEP-58](https://open-edx-proposals.readthedocs.io/en/latest/architectural-decisions/oep-0058-arch-translations-management.html#specification) is fully implemented.

The timing announcement will be shared by @brian-smith-tcril on [#translations-project-fc-0012](https://openedx.slack.com/archives/C04R6TUJB7T) Open edX Slack channel.

Keep this pull request as a draft to prevent accidental merge.

### Pre-merge checklist


 - [ ] Wait for approval on https://github.com/openedx/wg-translations/issues/20

References
----------

This pull request is part of the [FC-0012 project](https://openedx.atlassian.net/l/cp/XGS0iCcQ) which implements the [Translation Infrastructure update OEP-58](https://docs.openedx.org/en/latest/developers/concepts/oep58.html).

Up-to-date project overview and details are available in the [Approach Memo and Technical Discovery: Translations Infrastructure Implementation](https://docs.google.com/document/d/11dFBCnbdHiCEdZp3pZeHdeH8m7Glla-XbIin7cnIOzU/edit#) document.

Join the conversation on [Open edX Slack #translations-project-fc-0012](https://openedx.slack.com/archives/C04R6TUJB7T).

Check the links above for full information about the overall project.
