🌟 HabitFlow - Android Habit Tracker App
HabitFlow is a modern, offline-first Android habit tracker built with Kotlin, Jetpack Compose (Material 3), and Room Database. It empowers users to build lasting routines, maintain continuous streaks, visualize consistency through an interactive heatmap calendar, and receive daily local reminders.
✨ Features
•
🎯 Daily Focus Dashboard:
◦
Today's habit list with one-tap completion toggle and satisfying bounce animations.
◦
Interactive Circular Progress Ring showing completion rate and motivational feedback.
◦
Quick filtering by categories (Health, Fitness, Mindfulness, Productivity, Learning, Finance, Lifestyle).
•
🔥 Streak & History Tracking:
◦
Live streak counter with flame badge (🔥 5d) and best streak record (🏆 14d).
◦
Robust streak logic accounting for habit schedules (Daily, Weekdays, Custom days).
◦
30-day consistency score calculated automatically.
•
📅 Interactive Heatmap Calendar:
◦
Monthly calendar view on habit detail screens.
◦
Completed days highlighted with the habit's theme color.
◦
Retroactive Logging: Tap past days in the month to log or adjust completions anytime.
•
⏰ Smart Local Reminders:
◦
Custom daily reminder alerts powered by Android's AlarmManager.
◦
Rich notifications with a direct "Mark as Done" action button to complete habits without opening the app.
◦
Zero background battery drain or third-party servers required.
•
📊 Insights & Analytics:
◦
Overall habit consistency score across all tracked habits.
◦
Category distribution breakdown.
◦
Streak leaderboard showcasing top-performing habits.
•
🎨 Modern Material 3 Design:
◦
Light and Dark Mode support with midnight dark surfaces.
◦
Custom color palette picker (8 vibrant colors) and icon selector (16+ icons).
◦
Clean edge-to-edge layout following modern Android design guidelines.
•
🔒 100% Private & Offline-First:
◦
Uses SQLite & Room Database locally on device. No accounts, tracking, or network permissions required.
🏗️ Architecture & Tech Stack
Layer
Technology
Language
Kotlin 2.0.21
UI Toolkit
Jetpack Compose (Material 3)
Architecture
MVVM (Model-View-ViewModel) + Clean Architecture
Persistence
Room Database (SQLite) + Kotlin Flow
Navigation
AndroidX Navigation Compose
Asynchronous
Coroutines & StateFlow
Notifications
AlarmManager & BroadcastReceiver with NotificationCompat
Minimum SDK
API 26 (Android 8.0 Oreo)
Target SDK
API 35 (Android 15)
📁 Project Structure
HabitFlow/
├── app/
│   ├── build.gradle.kts                   # App module build configuration
│   ├── proguard-rules.pro
│   └── src/
│       ├── main/
│       │   ├── AndroidManifest.xml        # Permissions and receivers
│       │   ├── java/com/habitflow/app/
│       │   │   ├── MainActivity.kt        # Single activity host
│       │   │   ├── HabitApplication.kt   # Room database & channel setup
│       │   │   ├── domain/                # Habit, Frequency, Category, Color models
│       │   │   │   ├── Habit.kt
│       │   │   │   ├── HabitCategory.kt
│       │   │   │   ├── HabitColor.kt
│       │   │   │   └── Frequency.kt
│       │   │   ├── data/                  # Room Entities, DAO, Repository
│       │   │   │   ├── HabitEntity.kt
│       │   │   │   ├── HabitCompletionEntity.kt
│       │   │   │   ├── HabitWithCompletions.kt
│       │   │   │   ├── HabitDao.kt
│       │   │   │   ├── AppDatabase.kt
│       │   │   │   └── HabitRepository.kt
│       │   │   ├── receiver/              # Alarms and notifications
│       │   │   │   ├── NotificationHelper.kt
│       │   │   │   └── HabitReminderReceiver.kt
│       │   │   └── ui/
│       │   │       ├── theme/             # Material3 theme, Colors, Typography
│       │   │       ├── navigation/        # Compose Navigation Graph & Bottom Bar
│       │   │       ├── components/        # HabitCard, ProgressRing, HeatmapCalendar
│       │   │       ├── screens/           # Dashboard, Detail, AddEdit, Analytics, Settings
│       │   │       └── viewmodel/         # HabitViewModel
│       │   └── res/                       # Drawables, icons, and themes
│       └── test/                          # Unit tests
├── gradle/
│   ├── libs.versions.toml                 # Version catalog
│   └── wrapper/
│       ├── gradle-wrapper.jar
│       └── gradle-wrapper.properties
├── build.gradle.kts                       # Root build configuration
├── settings.gradle.kts
└── local.properties
🚀 How to Run the App
Option A: In Android Studio (Recommended)
1.
Open Android Studio.
2.
Select File -> Open... and choose this project folder: c:\Users\OMEN\Downloads\New folder
3.
Wait for Gradle Sync to complete.
4.
Connect an Android device (or start an Android Virtual Device / Emulator).
5.
Click the green Run (▶) button or press Shift + F10.
Option B: Build via Command Line
Run the included Gradle wrapper from the project root:
# Build the debug APK
.\gradlew.bat assembleDebug

# Install directly to a connected device
.\gradlew.bat installDebug
The compiled APK will be located at: app/build/outputs/apk/debug/app-debug.apk
🧪 Running Tests
To run unit tests:
.\gradlew.bat test
