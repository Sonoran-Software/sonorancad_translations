# Sonoran CAD Translation Files
This repository contains community sourced i18n translation files for [Sonoran CAD](https://docs.sonoransoftware.com/cad).

Communities who wish to add or improve translations for the CMS software in their native language can use [translate.sonoransoftware.com](https://translate.sonoransoftware.com) or submit a manual PR.
Translations are updated with additional app releases.

## Tolgee sync

The `staging` branch syncs with Tolgee through GitHub Actions:

1. Push `en-US.json` changes to `staging`.
2. The Tolgee Sync workflow pushes source strings to the Tolgee `staging` branch.
3. The workflow polls Tolgee for translated JSON files and commits any updates back to `staging`.
4. The `sc2_quasar` promote-staging workflow fast-forwards this repo's `master` branch from `staging`.

Required GitHub secrets:

- `TOLGEE_API_KEY`
- `TOLGEE_PROJECT_ID`

Optional GitHub variable:

- `TOLGEE_API_URL` for self-hosted Tolgee instances.
