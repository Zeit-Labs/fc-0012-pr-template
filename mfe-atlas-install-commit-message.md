feat: tutor-mfe compatiblilty for `atlas pull` | FC-0012

Similar to https://github.com/openedx/frontend-app-learning/pull/1279.
## Changes

 - install atlas
 - remove `--filter` to pull all languages by default
 - use ATLAS_OPTIONS to allow custom `--filter`
 - include frontend-platform in `atlas pull`

## Refs
This pull request is part of the [FC-0012 project](https://openedx.atlassian.net/l/cp/XGS0iCcQ) which implements the [Translation Infrastructure update OEP-58](https://docs.openedx.org/en/latest/developers/concepts/oep58.html).
