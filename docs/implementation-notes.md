# Implementation notes

## Scope

These notes describe selected implementation paths inspected in the supplied Repomix export. They are not a whole-repository audit or a runtime test report.

## Startup and state

`lib/main.dart` initialises Flutter, attempts to load `.env`, initialises connectivity, and loads persisted theme, favourites and search history before registering providers. The app uses `MaterialApp.router` with GoRouter and light/dark themes. A global error boundary wraps the routed child.

The Dart package name remains `anime_discovery`. Keeping the public project name Disconime does not require changing package imports, platform identifiers or generated files.

## API and cache

`lib/services/api_service.dart` reads `JIKAN_API_URL` and falls back to `https://api.jikan.moe/v4`. It accepts an HTTP client, queues requests within the service instance, and includes throttling and retry logic. This is not proof that upstream rate limits can never be exceeded.

`lib/services/cache_service.dart` stores JSON responses and timestamps through SharedPreferences. API paths use endpoint-specific cache lifetimes; stale fallback reads use a longer lifetime. Cache availability depends on prior successful fetches and retained local storage. It is not a full offline catalogue or a background synchronisation system.

## Personal collection

Favourites and search history have dedicated providers. The statistics screen reads favourites and derives collection summaries such as score, genre, type and status breakdowns. Do not describe these as measured viewing behaviour or episode-completion tracking.

## Configuration and assets

`pubspec.yaml` declares `.env`, the app logo and three team images as assets. `main.dart` catches dotenv load failures, but that does not remove the asset declaration from the build configuration. The README therefore asks developers to create `.env` explicitly.

Treat the environment file as public client configuration. Do not place credentials in it. Binary asset contents were not available in the text export and were not inspected.

## Verification boundary

Documentation was checked against the supplied manifest, startup, router, API/cache, favourites and statistics source, existing README and licence. Test-file paths were inventoried. No Flutter dependency installation, analyser run, test execution, build, device session or live API request was performed.

Platform folders are scaffolding evidence, not cross-platform compatibility certification. No production-readiness, accessibility-conformance, security or performance guarantee is made.
