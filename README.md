
References
----------

This pull request is part of the [FC-0012 project](https://openedx.atlassian.net/l/cp/XGS0iCcQ) which is sparked by the [Translation Infrastructure update OEP-58](https://open-edx-proposals.readthedocs.io/en/latest/architectural-decisions/oep-0058-arch-translations-management.html#specification).

Check the links above for full information about the overall project.


Internalization is being rearchitectured in Open edX Python, XBlock, Micro-frontend and other projects. There's a number of immediate visible changes:
 - Remove source and language translations from the repositories, hence no `.json`, `.po` or `.mo` files will be committed into the repos.
 - Add standarized `make extract_translations` in all repositories
 - Push user-facing messages strings into [openedx/openedx-translations](https://github.com/openedx/openedx-translations/).
 - Integrate root repositories with [openedx/openedx-atlas](https://github.com/openedx/openedx-atlas/) to pull translations on build/deploy time

