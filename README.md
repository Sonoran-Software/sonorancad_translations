# Sonoran CAD Translation Files
This repository contains community sourced i18n translation files for [Sonoran CAD](https://docs.sonoransoftware.com/cad).

Communities who wish to add or improve translations for the CMS software in their native language can use [translate.sonoransoftware.com](https://translate.sonoransoftware.com) or submit a manual PR.
Translations are updated with additional app releases.

## Tolgee sync

The `staging` branch syncs with Tolgee through GitHub Actions:

1. Push `en.json` source changes to `staging`.
2. The Tolgee Sync workflow pushes only `en.json` to Tolgee.
3. The workflow pulls translated JSON files from Tolgee and commits any updates back to `staging`.
4. The `sc2_quasar` promote-staging workflow fast-forwards this repo's `master` branch from `staging`.

Add new target languages in Tolgee. The next workflow run will pull them into this repo as `{languageTag}.json`.

Required GitHub secrets:

- `TOLGEE_API_KEY`
- `TOLGEE_PROJECT_ID`

Optional GitHub variable:

- `TOLGEE_API_URL` for self-hosted Tolgee instances.
