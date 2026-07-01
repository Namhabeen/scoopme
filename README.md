# SCOOPME

> 당신의 취향을 스쿱하세요!

사진 한 장으로 일상 속 색깔을 수집하는 라이프스타일 앱입니다.
물건을 촬영하면 자동으로 색상을 분석해 나만의 색상 컬렉션 도감을 수집할 수 있어요.
컬렉션의 누끼를 따서 SNS에 공유하기 좋은 이미지 카드도 생성해드린답니다!

---

## What is SCOOPME?

SCOOPME is a lifestyle app that lets you collect colors from your everyday life.
Simply take a photo of anything around you — the app automatically analyzes the dominant color and adds it to your personal color collection.
You can also create shareable image cards with your collected items, perfect for Instagram stories.

**Core features (MVP)**
- Photo capture & automatic color analysis (Google Vision API)
- Personal color collection with completion tracking
- Background removal for scoop-style sharing cards
- Badges, missions, and streaks to keep collecting fun

---

## Tech Stack

- Flutter (Dart)
- Firebase (Firestore, Auth, Storage)
- Google Cloud Vision API
- Riverpod (state management)
- go_router (routing)

---

## Project Structure

\```
lib/
├── core/
├── data/
├── presentation/
└── main.dart
\```

---

## Development

\```bash
flutter pub get
flutter run
flutter analyze
\```

---

## License

Private repository — all rights reserved.