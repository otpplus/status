# Securify & OTP+ Status

<!--start: description-->
Public status page for the Securify and OTP+ Shopify apps: **https://status.securification.ai**
<!--end: description-->

## [📈 Live Status](https://status.securification.ai): <!--live status--> **🟩 All systems operational**

<!--start: status pages-->
<!--end: status pages-->

<!--start: docs-->
## How this works

- Built on [Upptime](https://github.com/upptime/upptime). GitHub Actions checks every service every 5 minutes and commits the results to this repository.
- When a check fails, a GitHub issue opens automatically and the status page shows an incident until the service recovers.
- The status page (GitHub Pages, branch `gh-pages`) reads this repository's data live from the GitHub API.

## Operating it

- **Planned maintenance:** open an issue with the `maintenance` label and an HTML comment with `start:` and `end:` ISO times in the body (optionally `expectedDown: <slugs>`), as described in the [Upptime docs](https://upptime.js.org/docs/scheduled-maintenance). It shows on the status page before it starts.
- **Incident update:** comment on the open incident issue; comments appear on the status page.
- **Add or change a check:** edit `.upptimerc.yml`. A URL that names our infrastructure goes in a repository secret (listed under `secrets:` and in `SECRETS_CONTEXT` of `uptime.yml` and `response-time.yml`), never in plain text.
- The workflows are maintained by hand (see the header of `.upptimerc.yml`); the template's self-update workflows are not used.

Tracked in Jira as SEC-1222.
<!--end: docs-->
