# Video Conference App (myp)

Lightweight Flutter video-conference and meeting-management app built with Firebase and Jitsi.

## Summary

This project is a Flutter application that implements user authentication, meeting creation/joining, and meeting history persistence. It uses Firebase (Auth & Firestore) for backend services and `jitsi_meet_wrapper` for embedded video conferences.

## Main features

- Email/password sign up and sign in.
- Create a new Jitsi meeting (random room id) and join meetings.
- Store meeting metadata in Firestore for history.
- Simple, focused mobile-first UI with reusable widgets.

## Project structure (important files)

- `lib/main.dart` — app entry and routing.
- `lib/firebase_options.dart` — generated Firebase configuration helper.
- `lib/resources/auth_methods.dart` — authentication helpers.
- `lib/screens/` — UI pages: `signin`, `login`, `home_screen`, `meeting_screen`, `history_meeting_screen`, `video_call_screen`, etc.
- `lib/widgets/` — reusable UI widgets like `custom_button` and `home_meeting_button`.
- `lib/utils/` — colors and utility helpers.

## Platform notes and limitations

- Android & iOS: recommended target platforms. Project contains `google-services.json` and `GoogleService-Info.plist` placeholders; replace with your Firebase project's files.
- Windows (desktop): building may fail due to native Firebase C++ plugin incompatibilities on some environments. If you need desktop support, consider removing Firebase desktop plugins or using alternative web-based flows.
- Web: some packages used in this project (native desktop/firebase or older `web` packages) can cause web build issues; the project is primarily tested for mobile.

## Setup & run (quick)

1. Install Flutter SDK (stable channel) and required platform toolchains.
2. Create a Firebase project and enable Authentication and Firestore.
3. Add platform config files:
   - Android: place your `google-services.json` into `android/app/`.
   - iOS/macOS: place your `GoogleService-Info.plist` into `ios/Runner/` (and/or `macos/Runner`).
4. Ensure `lib/firebase_options.dart` reflects your Firebase project (run `flutterfire configure` if needed).
5. Fetch packages:

```bash
flutter pub get
```

6. Run on an Android device or emulator (recommended):

```bash
flutter run -d android
```

Notes: If you encounter platform-specific native build failures (Windows or Web), try running on Android/iOS first. See the "Platform notes and limitations" section above for guidance.

## How this project differs from a default Flutter starter

- Uses Firebase authentication and Firestore for persistent user and meeting data (not present in a default starter).
- Integrates `jitsi_meet_wrapper` to provide real-time video conferencing UI (beyond the typical template UI).
- Includes meeting history and simple meeting-management flows (create/join/store metadata).
- Custom widgets and theming geared specifically for video conference flows.

## Next steps you may want

- Replace the placeholder Firebase config with your project files and run `flutter pub get`.
- Test on Android/iOS first to avoid native desktop plugin issues.
- If you want desktop support, I can help remove or replace incompatible native Firebase plugins.

## License

This repository does not include an explicit license. Add one if you intend to publish or share.

---

If you'd like, I can now try running the app on an Android emulator or continue fixing desktop/web build issues — tell me which you prefer.
# Video-Conference-App-Flutter-
