This is a follow-up to #??? because it should have included the changes but apparently [OEP-58](https://open-edx-proposals.readthedocs.io/en/latest/architectural-decisions/oep-0058-arch-translations-management.html#specification) needs more publicity.

Testing
--------

I've ran the following:

```
$ OPENEDX_ATLAS_PULL=yes make pull_translations
$ cat src/i18n/index.js
```

Generates the following code, which seems to be good:

```js
```

References
----------

This pull request is part of the [FC-0012 project](https://openedx.atlassian.net/l/cp/XGS0iCcQ) which is sparked by the [Translation Infrastructure update OEP-58](https://open-edx-proposals.readthedocs.io/en/latest/architectural-decisions/oep-0058-arch-translations-management.html#specification).

Up-to-date project overview and details are available in the [Approach Memo and Technical Discovery: Translations Infrastructure Implementation](https://docs.google.com/document/d/11dFBCnbdHiCEdZp3pZeHdeH8m7Glla-XbIin7cnIOzU/edit#) document.

Join the conversation on [Open edX Slack #translations-project-fc-0012](https://openedx.slack.com/archives/C04R6TUJB7T).

Check the links above for full information about the overall project.

Internalization is being rearchitected in Open edX Python, XBlock, Micro-frontend, and other projects. There are a number of immediately visible changes:
 - Remove source and language translations from the repositories, hence no `.json`, `.po` or `.mo` files will be committed into the repos.
 - Add standardized `make extract_translations` in all repositories
 - Push user-facing messages strings into [openedx/openedx-translations](https://github.com/openedx/openedx-translations/).
 - Integrate root repositories with [openedx/openedx-atlas](https://github.com/openedx/openedx-atlas/) to pull translations on build/deploy time
