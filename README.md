# 📚 StudyFlow

> A production-ready, offline-first study productivity app — built with Flutter.

[![Build & Release](https://github.com/YOUR_USERNAME/studyflow/actions/workflows/release.yml/badge.svg)](https://github.com/YOUR_USERNAME/studyflow/actions/workflows/release.yml)
[![Flutter](https://img.shields.io/badge/Flutter-3.22+-02569B?logo=flutter)](https://flutter.dev)
[![Platform](https://img.shields.io/badge/Platform-Android%20%7C%20Windows%20%7C%20macOS-blueviolet)](https://github.com/YOUR_USERNAME/studyflow/releases)

---

## 📥 Download

| Platform | Download | Requirements |
|----------|----------|--------------| 
| 🤖 Android | [Download APK](https://github.com/YOUR_USERNAME/studyflow/releases/latest) | Android 6.0+ |
| 🍎 macOS | [Download DMG](https://github.com/YOUR_USERNAME/studyflow/releases/latest) | macOS 12 Monterey+ |
| 🪟 Windows | [Download Installer](https://github.com/YOUR_USERNAME/studyflow/releases/latest) | Windows 10/11 (64-bit) |

---

## ✨ Features

### 📅 Weekly Planner (Fully Revamped)
- **10 ways to create entries:**
  - Tap any empty time cell → instant task modal
  - Floating `+ Add Task` FAB
  - **Drag across cells** → auto-popup with start/end pre-filled
  - **"Create Timetable" Wizard** (4-step: wake/sleep → add tasks → review → generate)
  - **5 starter templates** (School Week, Exam Week, Holiday, Tuition, Blank)
  - **Copy Last Week** button
  - **Spreadsheet Mode** (tap cells to fill like Excel)
  - Week navigation (back/forward)
  - Empty state with illustrated CTA buttons
  - **Autosave** with debounce — never lose data
- Task editor fields: Title, Subject, Day, Start/End time, Color, Priority, Notes, Reminder, Repeat weekly
- **Drag-to-create** gestures
- **Long press** → task options (Edit, Duplicate, Delete)
- Current time indicator on today's column
- Day headers with dates
- **First-time tutorial banner** (tap/drag/long press hints)

### 🍅 Pomodoro Timer
Customizable focus sessions with completion notifications

### 🃏 Flashcards  
SM-2 spaced repetition algorithm

### 📊 Analytics
Track hours, subject breakdown, study streaks

### 📝 Homework Tracker
Manage assignments and tuition sessions

### 🔐 Security
AES-256 encrypted storage, PBKDF2 password hashing

### 🌙 Theme
Full light / dark / system theme support — 100% offline

---

## 🚀 Build & Run

### Prerequisites
- Flutter SDK 3.22+
- Android Studio / VS Code with Flutter plugin

```bash
# Install dependencies
flutter pub get

# Run on device/emulator
flutter run

# Build Android APK
flutter build apk --release --split-per-abi

# Build macOS (on Mac only)
flutter build macos --release

# Build Windows (on Windows only)
flutter build windows --release
```

---

## 🏗️ Architecture

```
lib/
├── core/
│   ├── db/            # SQLite database helper
│   ├── notifications/ # Local push notifications
│   ├── routing/       # GoRouter navigation + bottom nav shell
│   └── theme/         # Material 3 theme + Riverpod theme provider
└── features/
    ├── dashboard/     # Home screen with quick access cards
    ├── timer/         # Pomodoro timer
    ├── flashcards/    # SM-2 flashcard decks
    ├── schedule/
    │   ├── data/      # TimetableRepository (SQLite)
    │   ├── domain/    # TimetableEntry model + enums
    │   └── presentation/
    │       ├── weekly_plan/   # ⭐ Full timetable grid with all 10 input methods
    │       └── daily_plan/    # Hour-by-hour daily view
    ├── analytics/     # Charts and statistics
    ├── tuition_homework/ # Homework tracker
    └── settings/      # Theme, backup/restore
```

---

## 📦 CI/CD Release Pipeline

Every GitHub release tag (`v*.*.*`) automatically builds:
1. Android APK (ARM64 + ARMv7 + Universal)
2. Windows installer (.exe)
3. macOS disk image (.dmg)

**Setup:**
1. Copy `.github/workflows/release.yml` → your repo's `.github/workflows/`
2. Copy `android/app/build.gradle.kts` → replace in your project
3. Push a tag `v1.0.0` → builds happen automatically

See `HOW_TO_PUBLISH.md` for the complete beginner-friendly guide.

---

## 📄 License

MIT — free to use, modify, and distribute.

*Made with ❤️ using Flutter*
