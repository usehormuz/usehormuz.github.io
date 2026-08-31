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

The matching workflow and helper templates live in
[`website/deployment`](https://github.com/Xpounder-com/hormuz/tree/main/website/deployment)
in the product repository. See its
[`website/README.md`](https://github.com/Xpounder-com/hormuz/blob/main/website/README.md)
for compatibility redirects and the initial two-phase migration.

Maintainer: Mehrdad Zaker. Licensed under the existing Apache-2.0 license.
