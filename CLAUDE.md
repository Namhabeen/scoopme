# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project overview

SCOOPME is a photo-based color collection Flutter app. The project is currently at the very early
scaffold stage: `lib/main.dart` still contains the default Flutter counter-app template, and
`lib/firebase_options.dart` is the FlutterFire-generated config. Firebase (`firebase_core`) is wired
in as the only non-default dependency so far.

Note: `README.md` currently has an unresolved git merge conflict (`<<<<<<< HEAD` / `=======` /
`>>>>>>>` markers) between the default Flutter template text and the "SCOOPME - Photo-based color
collection app" description — resolve this before relying on it.

## 기술 스택
- FE: Flutter (Dart)
- 상태관리: Riverpod (예정)
- 라우팅: go_router (예정)
- DB: Firebase Firestore (예정)
- Storage: Firebase Storage (예정)
- 인증: Firebase Auth (예정)
- 외부 API: Google Cloud Vision API (색상 분석)

## 개발 규칙
- 브랜치: habing/이슈번호-기능명 형식
- 커밋: Conventional Commits (feat:, fix:, refactor: 등)
- 주석: 핵심 로직에 충분히 작성 (Flutter 입문 단계)
- 코드에 이모티콘 절대 금지

## 프로젝트 구조 (예정)
```
lib/
├── core/ (constants, errors, theme, utils)
├── data/ (models, repositories, services)
├── presentation/ (pages, widgets, providers)
└── main.dart
```

## Commands

Standard Flutter CLI workflow (no custom scripts/Makefiles exist in this repo):

```bash
flutter pub get                 # install dependencies
flutter run                     # run on a connected device/emulator/simulator
flutter analyze                 # static analysis (uses analysis_options.yaml / flutter_lints)
flutter test                    # run all tests
flutter test test/widget_test.dart   # run a single test file
flutter test --plain-name "<test name>"  # run a single test by name
flutter build apk                # Android build
flutter build ios                # iOS build (macOS/Xcode required)
flutter build web                # Web build
```

## Firebase

The app is registered with Firebase project `scoopme-ec6eb` (configured via FlutterFire CLI).

- `lib/firebase_options.dart` — generated platform config (Android/iOS app IDs), used by
  `Firebase.initializeApp(options: DefaultFirebaseOptions.currentPlatform)`.
- `android/app/google-services.json` — Android Firebase config (currently untracked in git).
- `firebase.json` — FlutterFire CLI project/platform mapping.

If Firebase options are regenerated, use `flutterfire configure` rather than hand-editing
`firebase_options.dart`.

## Architecture notes

The project uses the standard Flutter multi-platform layout (`android/`, `ios/`, `web/`, `linux/`,
`macos/`, `windows/` platform runners alongside a single Dart entrypoint in `lib/`). The
`core/`/`data/`/`presentation/` folder structure above is planned but not yet implemented — as
features are added, check `lib/` for the current organization rather than assuming it's already
in place.
