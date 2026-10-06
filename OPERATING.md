# Operating the status page

Public status page for the Securify and OTP+ Shopify apps:
**https://status.securification.ai** (SEC-1222). `README.md` is rewritten by
the Upptime bot on every summary run, so the notes live here.

## How it works

- Built on [Upptime](https://github.com/upptime/upptime). GitHub Actions checks
  every service every 5 minutes and commits status changes to this repository.
- When a check fails, an issue opens automatically and the status page shows an
  incident until the service recovers.
- The page itself (GitHub Pages, branch `gh-pages`, custom domain
  `status.securification.ai` via a DNS-only CNAME in Cloudflare, HTTPS
  enforced) reads this repository's data live from the GitHub API.

## Planned maintenance

Open an issue with the `maintenance` label and this HTML comment in the body
([Upptime docs](https://upptime.js.org/docs/scheduled-maintenance)):

```
<!--
start: 2026-10-20T13:00:00+00:00
end: 2026-10-20T14:00:00+00:00
expectedDown: securify-app, securify-protection
-->
```

The page shows it before it starts; checks of the listed slugs do not open
incidents while it runs.

## Incident updates

Comment on the open incident issue. Comments appear on the status page.

## Adding or changing a check

Edit `.upptimerc.yml`. Any URL other than a public marketing site goes in a
repository secret (`gh secret set NAME -R otpplus/status`), is referenced as
`$NAME`, and is named in `SECRETS_CONTEXT` of `uptime.yml` and
`response-time.yml` (passing `toJson(secrets)` whole leaves those runs in
`action_required` with no jobs). That way no internal hostname, health route or version string reaches the
page, the README, the issues or the Actions logs. The page shows only the
service name and whether it is up.

## Workflows

Maintained by hand from Upptime v1.44.1. The organisation keeps `GITHUB_TOKEN`
read-only by default, so each workflow grants itself the write scopes it needs;
the template's self-update workflows (setup, update-template, updates) are not
used because `GITHUB_TOKEN` cannot rewrite workflow files.
