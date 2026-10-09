# Hormuz website

Publication repository for the Hormuz project website at
[usehormuz.github.io](https://usehormuz.github.io/).

The authoritative website source, product development, releases, and issue
tracker remain in [Xpounder-com/hormuz](https://github.com/Xpounder-com/hormuz).
This repository contains only the reviewed source pin and website publication
configuration. It does not duplicate or transfer the product repository.

## Updates and verification

1. Review the source change and its exact commit's checks in the product repository.
2. Open a pull request updating `site-source.json` to that full 40-character commit.
3. Review the pin and publication changes; require passing `Website checks` and
   resolved review conversations before merging through branch protection.
4. Confirm the Pages deployment and the read-only `Verify live website` job pass.
5. Check the live demo, contact-draft flow, mobile navigation, and buyer downloads
   when the corresponding content or interactions change.

The build installs locked website dependencies and checks routes, privacy,
recordings, claims, types, links, metadata, and downloads. The public
`/site-source.json` identifies the source commit included in the deployed
artifact. Post-deploy verification checks that pin and the live static site;
it is not a substitute for interactive or document-layout QA.

## Publication boundaries

Only `main` may deploy to GitHub Pages. Source builds and public-site verification
use read-only repository permissions. Only the isolated deployment job receives
Pages and OIDC write permissions. No cross-repository write token, paid hosting
plan, analytics service, form backend, or product-release publication is needed.

Source changes do not automatically republish this site: updates use reviewed
pins. Roll back by restoring a previously verified pin through a normal pull
request, then verify the resulting deployment. Never force-push or bypass branch
protection for a website update.

Google Search Console ownership files live in `verification/` as publication
configuration. The build copies the verification file to the site root, and the
live check verifies its contents after deployment. Keep the file published after
verification succeeds so ownership remains valid.

The matching workflow and helper templates live in
[`website/deployment`](https://github.com/Xpounder-com/hormuz/tree/main/website/deployment)
in the product repository. See its
[`website/README.md`](https://github.com/Xpounder-com/hormuz/blob/main/website/README.md)
for compatibility redirects and the initial two-phase migration.
This publication repository deliberately adds its existing Search Console
ownership file, the corresponding live check, and publication-specific regression
tests to those general templates. Keep these additions when refreshing a template;
they do not change the pinned product source.

## Workspace entry point

The `/workspace/` page links to the authenticated Render dashboard when the
public repository variable `HORMUZ_DASHBOARD_ORIGIN` is configured. Set only the
canonical HTTPS backend origin after its customer sign-in and exact OIDC
callback have been verified. This variable is public and must contain no
credential, path, query, or fragment. Leave it unset while preparing signup;
the page then reports that sign-in is being prepared.

GitHub Pages hosts the static entry page. Customer cookies, account state, and
custom-domain connections remain on the Render backend. See the product's
`WORKSPACE_ADDRESSES.md` for configuration, migration, and acceptance details.

Maintainer: Mehrdad Zaker. Licensed under the existing Apache-2.0 license.

## AI Work entry and mechanics evidence

The static `/work/` entry uses the same reviewed public
`HORMUZ_DASHBOARD_ORIGIN` variable to open the authenticated gateway `/work`
page. Leave the variable unset until that deployment is qualified. Public
campaign labels cross this boundary only after optional consent and a separate
authenticated confirmation. No task or credential belongs in this variable.

The publication check verifies sixteen canonical routes, five buyer downloads,
the actual work recording on `/demo/`, and the executed receipt on `/evidence/`.
When a gateway origin is configured it checks the published destination without
contacting the private backend. Source fingerprints and declared synthetic
conditions remain part of the product build checks. Synthetic provider, billing,
and signed workflow fixtures do not prove paid-provider savings, live payment,
customer results, or deployment qualification.
