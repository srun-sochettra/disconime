# Repository refresh

## Recommended identity

- Repository slug: keep `disconime`.
- Display name: **Disconime**.
- Suggested description: **Flutter anime discovery app with seasonal browsing, weekly schedules, character profiles, local favourites and cached API responses.**
- Suggested topics: `flutter`, `dart`, `anime`, `jikan-api`, `provider`, `go-router`, `mobile-app`.

Disconime is already distinctive and matches the in-app title. A generic technology-prefixed rename would add little. Keep the internal Dart package name `anime_discovery`; this overlay does not change imports or platform identifiers.

## Apply the overlay

Extract the ZIP into the existing repository root, replacing README.md and adding CONTRIBUTING.md, SECURITY.md and the two files under docs/. This is a documentation overlay, not a complete repository replacement. Preserve all source, assets, platform folders, configuration, licence and Git history.

No remote repository rename, description update, topic change, commit or push was performed.

## Editorial changes

The README leads with the app's purpose and existing showcase, then explains discovery features, architecture, setup and limitations. It replaces ambiguous viewing-statistics wording with collection-derived statistics and avoids implying account synchronisation or comprehensive offline support.

Setup now explicitly creates `.env` because it is declared as an asset. It distinguishes client configuration from secrets and states the actual Dart constraint. Platform scaffolding and existing test files are not presented as successful platform builds or passing tests.

The existing screenshot URL and MIT licence are retained. No metrics, download links, release claims, team biographies or test results were invented.

## Verification

The supplied source paths cited by these documents and the local documentation links were checked. The ZIP was reopened and its member bytes checked against the authored text. Flutter analysis, tests, builds, device behaviour, external links and live API responses were not executed or verified.
