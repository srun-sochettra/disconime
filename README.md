# Disconime

**An anime discovery app for finding your next watch and keeping favourites close.**

Built with Flutter and Dart, Disconime brings rankings, seasonal releases, weekly schedules and character profiles into one app. Anime data comes from Jikan v4, an unofficial MyAnimeList API.

![Disconime app showcase](https://github.com/user-attachments/assets/90af3ba1-6642-4597-b75f-404ec36d5c5e)

## Explore, discover, save

- **Browse beyond search.** Explore top-ranked titles, seasonal releases and genres.
- **Follow the week.** Browse anime broadcast schedules.
- **Look closer.** Open anime details and character profiles, including voice-actor information where supplied by the API.
- **Keep a personal collection.** Save favourites locally and explore statistics derived from that collection.
- **Pick up a search.** Revisit locally saved search history.
- **Make it yours.** Switch between light and dark themes and share anime through the platform share sheet.
- **Revisit cached data.** Previously fetched responses can be reused when offline or when requests fail. Uncached content still needs a connection.

The statistics screen summarises saved favourites. It is not evidence of watch-history tracking, episode progress or MyAnimeList account synchronisation.

## Built with

| Layer | Implementation |
| --- | --- |
| Interface | Flutter, Material widgets, Google Fonts |
| State | Provider and ChangeNotifier |
| Navigation | GoRouter |
| API requests | HTTP client with request queuing, throttling and retry handling |
| Local storage | SharedPreferences for favourites, search history, theme and response caching |
| Images | CachedNetworkImage |
| Connectivity | connectivity_plus and internet_connection_checker_plus |
| Sharing | share_plus |

## Run locally

Use a Flutter SDK that includes Dart **3.10.4 or a compatible later 3.x version**, matching the `^3.10.4` constraint in `pubspec.yaml`. Set up the toolchain for your intended target.

From the repository root:

```bash
flutter pub get
```

Create a root `.env` file containing:

```dotenv
JIKAN_API_URL=https://api.jikan.moe/v4
```

The API service has the same URL as its fallback, but `.env` is also declared in Flutter's asset list. Create the file before building rather than relying on the runtime missing-file handler. This is client-bundled configuration, not a place for secrets.

Then launch on a connected device or emulator:

```bash
flutter run
```

The repository includes Android, iOS, web, Windows, macOS and Linux platform folders. Their presence does not establish that every target has been tested or released. Binary assets are not included in the Repomix text export; use the original repository with its assets, not that export alone.

## Checks

```bash
flutter analyze
flutter test
```

The supplied source contains model, provider, API/cache service and widget tests. These commands are the local verification path, not a claim that they passed during this documentation refresh.

## Inside the project

```text
lib/
  main.dart       App startup and provider registration
  models/         Anime, character, schedule and filter models
  providers/      Discovery, favourites, history, theme and connectivity state
  router/         Routes and navigation transitions
  screens/        Discovery, details, favourites and statistics views
  services/       API access, response cache and connectivity
  theme/          Colours and light/dark themes
  utils/          Shared helpers
  widgets/        Reusable UI and feedback components
test/             Model, provider, service and widget tests
```

For implementation details and limitations, see [implementation notes](docs/implementation-notes.md). See [contributing](CONTRIBUTING.md) before making changes and [security guidance](SECURITY.md) before sharing configuration or diagnostics.

## Data and limitations

Listings, scores, schedules, images and character information depend on the upstream API and linked image hosts. Requests may fail, be rate-limited or return incomplete information. Cached responses may be stale; offline access is limited to data already stored on the device.

Anime metadata and artwork remain third-party material. The source-code licence does not grant rights to that content. This project does not claim affiliation with MyAnimeList or Jikan.

## Credits and licence

Developed by **Srun Sochettra**. The existing licence credits **Disconime Team**.

Source code is available under the [MIT License](LICENSE).
