

References
----------

This contribution is part of the [FC-0012 project](https://openedx.atlassian.net/l/cp/XGS0iCcQ) which is sparked by the [Translation Infrastructure update OEP-58](https://open-edx-proposals.readthedocs.io/en/latest/architectural-decisions/oep-0058-arch-translations-management.html#specification).

Up-to-date project overview and details are available in the [Approach Memo and Technical Discovery: Translations Infrastructure Implementation](https://docs.google.com/document/d/11dFBCnbdHiCEdZp3pZeHdeH8m7Glla-XbIin7cnIOzU/edit#) document.

Join the conversation on [Open edX Slack #translations-project-fc-0012](https://openedx.slack.com/archives/C04R6TUJB7T).

Check the links above for full information about the overall project.

Internalization is being re-architected in Open edX Python, XBlock, Micro-frontend, and other projects. There are a number of immediately visible changes:
 - Remove source and language translations from the repositories, hence no `.json`, `.po` or `.mo` files will be committed into the repos.
 - Add standardized `make extract_translations` in all repositories
 - Push user-facing messages strings into [openedx/openedx-translations](https://github.com/openedx/openedx-translations/).
 - Integrate root repositories with [openedx/openedx-atlas](https://github.com/openedx/openedx-atlas/) to pull translations on build/deploy time

Breaking Changes
----------------

One of the primary goals of the project is to **avoid breaking changes**. If you noticed any suspicious code, please raise your concern. But before that, please know the strategy we're following to avoid breaking changes

**For XBlocks:**
 - The standard translation path must be `conf/locale`. Therefore, we are creating a link from `conf/locale` to `translations` so Atlas can find the path without disrupting the current way of having translations locally within the XBlocks
 - [openedx-translations](https://github.com/openedx/openedx-translations) will have a related PR that adds the XBlock to the pipeline. This will not affect the current way of managing/updating translations
 - At the end of the project, a clear change log will be added and all translations will be handled by Atlas. Thus, the local translation will be removed from the repo within the version bump
 - A notification for the community will be published to ensure that everyone knows why translations directories are removed from all repos
