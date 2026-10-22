# Contributing

Keep changes focused on a reproducible problem or a clearly described user benefit.

## Local workflow

1. Follow the setup in [README.md](README.md), including the root `.env` file and original binary assets.
2. Inspect the relevant screen, provider and service before changing behaviour.
3. Add or update a focused regression test when changing non-trivial logic.
4. Run `flutter analyze` and `flutter test`. Report actual results and any unavailable checks.
5. Exercise affected screens on the target you intend to support.

For UI changes, include screenshots and check loading, empty, failure, offline and long-content states where relevant. Preserve favourites, search history and theme preferences unless a deliberate migration is part of the change.

Keep API tests isolated from live upstream services where practical. Do not use a passing mocked test as proof of live API behaviour. Do not add secrets, personal diagnostics or generated build output to a contribution.

A useful change description states the problem, files changed, verification performed and remaining limitations. Do not rename the Dart package or platform identifiers merely to match a repository slug.
