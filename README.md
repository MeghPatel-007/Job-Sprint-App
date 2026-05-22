# Jobsprint

A Flutter application. This README only documents files and folders that are actually present in this repository.

## What is in this repo

- Flutter project root files: `pubspec.yaml`, `pubspec.lock`, `analysis_options.yaml`, `devtools_options.yaml`
- Platform folders present: `android/`, `ios/`, `web/`, `linux/`, `macos/`, `windows/`
- Main app entry: `lib/main.dart`
- App source tree: `lib/src/` (contains `assets/` and `features/` including `authentication`)
- Tests: `test/` folder

## Quick start (local)

1. Install Flutter and ensure `flutter` is on your PATH.

2. Get dependencies:

```bash
flutter pub get
```

3. Run on a connected device or emulator:

```bash
flutter run
```

4. Run tests:

```bash
flutter test
```

5. Build a release APK (Android):

```bash
flutter build apk --release
```

Build and run commands for other platforms follow the standard Flutter CLI (e.g. `flutter build web`, `flutter build macos`).

## Project structure (relevant)

- `lib/main.dart` — application entrypoint
- `lib/src/` — app source (assets and feature modules)
- `android/`, `ios/`, `web/`, `linux/`, `macos/`, `windows/` — platform projects
- `test/` — unit / widget tests
- `pubspec.yaml` — dependencies and metadata

## Notes

- This README intentionally lists only items that exist in the repository. If you want, I can expand sections with:
  - dependency highlights from `pubspec.yaml`
  - a simple development checklist for running on each platform
  - CI or release notes based on your preferences.

---

Updated to reflect actual project contents.
