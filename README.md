<div align="center">

<h1>🚀 KotDart — Kotlin × Dart / Flutter Learning App</h1>

<img src="https://img.shields.io/badge/Platform-Android-green.svg" alt="Android" />
<img src="https://img.shields.io/badge/UI-Jetpack%20Compose-blue.svg" alt="Jetpack Compose" />
<img src="https://img.shields.io/badge/Language-Kotlin-purple.svg" alt="Kotlin" />
<img src="https://img.shields.io/badge/CrossPlatform-Flutter%20%2F%20Dart-cyan.svg" alt="Flutter & Dart" />
<img src="https://img.shields.io/badge/License-MIT-yellow.svg" alt="License: MIT" />
<img src="https://img.shields.io/badge/Privacy-100%25%20Offline%20First-success.svg" alt="Offline First" />

<br /><br />

**KotDart** is a modern, offline-first Android learning companion built for mobile developers mastering both **Native Android (Kotlin / Jetpack Compose)** and **Cross-Platform Flutter (Dart)**. It bridges the gap between ecosystems by pairing theoretical intuition with direct side-by-side code implementations.


</div>

---

## 🤖 Google Play Console Reviewer Notes
This repository hosts the official open-source code for **KotDart**. 
* **Privacy Compliance:** The application operates strictly **offline-first**. It features zero background tracking, zero web server synchronization, and requests **no Android runtime permissions** (no location, no contacts, no network state checks needed).
* **Data Transparency:** All structural architecture layout code (`ui/screens/`) and data parsing routines (`data/LessonJsonLoader.kt`) can be openly audited within this codebase to verify compliance with Google Play Data Safety policies.
* **Privacy Policy:** The live policy can be read directly in the [PRIVACY_POLICY.md](./PRIVACY_POLICY.md) file of this repository.

---


## 📱 What is KotDart?

Whether you are an Android developer exploring Flutter or a Flutter developer learning Kotlin and Jetpack Compose, **KotDart** provides a structured, multi-stage curriculum that translates equivalent concepts across both frameworks instantly.

---

## ✨ Key Features

### 1. 🗺️ Multi-Stage Lesson Journeys (`LessonDetailScreen`)
Every lesson in KotDart guides you through 7 progressive learning stages:
- **Story**: Relatable everyday analogies connecting real-world concepts to software architecture.
- **Concept**: Architectural breakdown (**What**, **Why**, **How**) and mental blueprint data flows.
- **Visual**: Interactive sandbox simulations and component behavior previews.
- **Code**: Side-by-side implementation comparison between Kotlin/Compose and Dart/Flutter with syntax highlighting and copy-to-clipboard support.
- **Try**: Hands-on coding challenges with success criteria, hints, and solution starter templates.
- **Deep Dive**: Technical under-the-hood systems analysis and performance considerations.
- **Recall**: Active recall testing and mastery checks.

### 2. 🔀 Framework Comparison Hub (`CompareScreen`)
- Instantly compare any curriculum concept side-by-side or via tabbed views, contrasting Android and Flutter syntax, state handling, and layout paradigms.

### 3. 🛠️ Practice Lab & Quizzes (`PracticeScreen`)
- **Challenges**: Guided build challenges (Counter, Login Form, Todo List, Weather State UI) with success tracking.
- **Glossary**: Searchable terminology reference mapping Compose composables to Flutter widgets.
- **Commands**: Handy CLI and build tool reference for Android and Flutter development.
- **Quiz Engine**: Randomized test sessions with explanation reviews and score tracking.

### 4. 📈 Learning Dashboard & Trend Graph (`ProgressScreen`)
- **Course Progress**: Overall completion progress bar and lesson counters.
- **Learning Trend Graph**: 7-day active frequency trend chart tracking daily practice habits.
- **Streak & Goals**: Daily learning target selector (1–5 lessons/day) and streak counter.
- **Topic Mastery**: Skill gap analysis and recall mastery estimators.

### 5. ⏰ Learning Schedule & Smart Alarms (`SettingsScreen`)
- **Customizable Alarms**: Set a dedicated study time with flexible frequency modes: **Daily**, **Weekly** (with custom Sun-Sat day selection chips), and **Weekend**.
- **Session Durations**: Choose target session lengths (5, 10, 15, or 30 minutes).
- **Tactile & Audio Alerts**: 10-second vibration pattern and default notification sound reminders.
- **Interactive Actions**: Direct notification buttons for **Learn Now**, **Okay**, and **Dismiss**.
- **Smart Auto-Clearing**: Automatically cancels reminders for today if you open the app or complete a lesson early.

### 6. ⚙️ Profile & Customization (`SettingsScreen`)
- **Personalized Greeting**: Dynamic "Welcome" or "Welcome back" greeting featuring your custom name and avatar emoji.
- **Theme Modes**: Support for Light, Dark, System, and Night Light (warm Sepia / espresso) themes.
- **Font Scale Presets**: Adjustable UI text scaling (Small, Medium, Large).
- **Developer Pro Mode**: Toggle to skip beginner stories and immediately display high-density architecture blueprint nodes.
- **Replay Onboarding**: Option in Settings to replay the interactive app tour anytime.
- **In-App Support & Feedback**: Built-in dialogs for contacting support (`support.kotdart.dev@gmail.com`) and developers (`feedback.kotdart.dev@gmail.com`) with pre-filled message handoff.
- **Play Store Rating**: Direct link to rate KotDart on the Google Play Store.

---

## 🔒 Privacy & Offline-First Design (For Google Play & Users)

KotDart is engineered with strict privacy guarantees:
- **100% Offline-First**: All lesson content is bundled locally within the app assets.
- **Local-Only Storage**: All learner progress, bookmarks, notes, and profile settings are stored securely on your device via local device storage (`SharedPreferences`).
- **Zero Cloud Tracking**: No remote servers or user databases are operated. Your learning data never leaves your device.
- **Zero Runtime Permissions**: Requires no sensitive device permissions (no camera, location, or storage permissions needed).

---

## 📁 Project Architecture

```
com.kotdart.learning/
├── data/                    # Data layer & local persistence
│   ├── model/               # Data classes (Lesson, Challenge, QuizQuestion, etc.)
│   ├── repository/          # LessonRepository & LearningContent catalog
│   ├── LessonJsonLoader.kt  # Offline JSON asset parser & validator
│   ├── ProgressStore.kt     # SharedPreferences storage manager
│   ├── QuizEngine.kt        # Quiz session generator & grader
│   ├── RevisionEngine.kt    # Spaced repetition & review engine
│   ├── ReminderScheduler.kt # AlarmManager study reminder engine
│   ├── LearningReminderReceiver.kt # Notification broadcast receiver (Learn Now, Okay, Dismiss)
│   └── BootReceiver.kt      # Device reboot alarm restorer
├── ui/                      # Presentation layer (Jetpack Compose)
│   ├── components/          # Reusable UI widgets (CodeBlock, InteractivePreview, FlowDiagram)
│   ├── screens/             # App screens (Home, LessonDetail, Practice, Compare, Quiz, Settings, Progress, Onboarding)
│   └── theme/               # Material 3 Color scheme, Typography, and UI tokens
└── MainActivity.kt          # Root Activity & Navigation orchestration
```

---

## 🔐 Permissions Required & System Compliance

KotDart is designed to respect user privacy and operates with minimal system permissions:
- **`POST_NOTIFICATIONS`** (Android 13+ / API 33+): Required to display study reminder notifications and learning streak alerts.
- **`RECEIVE_BOOT_COMPLETED`**: Automatically restores active learning schedule alarms if the device restarts.
- **`VIBRATE`**: Powers the tactile 10-second vibration alert for study alarms.
- *Note:* Requires **zero** dangerous runtime permissions (no location, camera, microphone, or external storage access required).

---

## 🏛️ Project Architecture & Data Safety Proof

KotDart follows a clean, modular Model-View-ViewModel (MVVM) and Unidirectional Data Flow (UDF) architecture built with Jetpack Compose:
- **Data Layer (`data/`)**: Manages local persistence (`ProgressStore`), offline JSON asset loading (`LessonJsonLoader`), quiz generation (`QuizEngine`), spaced repetition (`RevisionEngine`), and alarm scheduling (`ReminderScheduler`).
- **Presentation Layer (`ui/`)**: Composable screens and modular components driven by reactive Jetpack Compose state.
- **Data Safety Guarantee**: All data resides strictly in local device storage. No user data, analytics, or telemetry are transmitted externally.

---

## 🚀 Getting Started & Local Development

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/kotdart.git
   ```
2. Open the project in **Android Studio**.
3. Ensure you have **JDK 17** installed.
4. Sync Gradle files and run the `app` configuration on an emulator or physical device.

### Gradle Build Commands
- Build Debug APK: `./gradlew assembleDebug`
- Run Unit Tests: `./gradlew testDebugUnit`
- Build Release App Bundle (`.aab`): `./gradlew bundleRelease`

---

## 📄 License

KotDart is open-source software licensed under the [MIT License](LICENSE).
