# FinSphere# FinSphere

**Where Every Rand Has a Purpose.**

A fully-featured personal budget tracking Android application built with Kotlin and Room DB for the Open Source Coding module, 2026.

---

## Demo Video

Watch the full feature demonstration here:
https://youtu.be/_Pfa8FhzgZI
My youtube video was removed on youtube hence i have added the video in my project files called Video Presentation.


---

## Features

- User registration and secure login with SHA-256 password hashing
- Create budget categories with custom colour coding
- Add expense entries with date, start time, end time, amount, and description
- Take and store a photo per expense entry using the device camera
- View a list of all expense entries filtered by a user-selectable period
- Access the stored photo of any entry directly from the list
- View total spending per category for a user-selectable period
- Set minimum and maximum spending goals per category
- Goal status indicator showing whether spending is within, below, or above target
- All data stored locally using Room DB (SQLite) with full offline capability
- Input validation throughout — the app handles invalid inputs without crashing
- Logging throughout all activities using android.util.Log

---

## Tech Stack

- Language: Kotlin
- IDE: Android Studio
- Database: Room DB (SQLite) — offline-first local storage
- UI: Material Design 3, RecyclerView, ViewBinding
- Photo storage: Camera Intent with FileProvider
- Security: SHA-256 password hashing — no plain-text credentials stored in the database
- CI/CD: GitHub Actions — automated build and unit tests on every push

---

## Getting Started

### Prerequisites

- Android Studio Hedgehog or later
- Android SDK API 26 or higher
- JDK 17

### Installation

1. Clone this repository:

   git clone https://github.com/YOUR_USERNAME/FinSphere.git

2. Open Android Studio
3. Click Open and select the FinSphere project folder
4. Wait for Gradle sync to complete
5. Run on an emulator or physical device running API 26 or higher

### Running Unit Tests

   ./gradlew test

---

## Project Structure

   app/src/main/java/com/varsity/finsphere/
   |
   |-- data/
   |   |-- AppDatabase.kt
   |   |-- dao/
   |   |   |-- UserDao.kt
   |   |   |-- CategoryDao.kt
   |   |   |-- ExpenseEntryDao.kt
   |   |   |-- GoalDao.kt
   |   |
   |   |-- entities/
   |       |-- User.kt
   |       |-- Category.kt
   |       |-- ExpenseEntry.kt
   |       |-- Goal.kt
   |
   |-- ui/
   |   |-- categories/
   |   |   |-- CategoriesActivity.kt
   |   |   |-- CategoryAdapter.kt
   |   |   |-- AddCategoryActivity.kt
   |   |
   |   |-- expenses/
   |   |   |-- AddExpenseActivity.kt
   |   |   |-- ExpenseAdapter.kt
   |   |   |-- ExpenseListActivity.kt
   |   |   |-- ExpenseDetailActivity.kt
   |   |
   |   |-- goals/
   |   |   |-- GoalsActivity.kt
   |   |   |-- GoalAdapter.kt
   |   |
   |   |-- reports/
   |       |-- CategoryTotalsActivity.kt
   |       |-- CategoryTotalsAdapter.kt
   |
   |-- utils/
   |   |-- SessionManager.kt
   |   |-- HashUtils.kt
   |   |-- DateUtils.kt
   |
   |-- LoginActivity.kt
   |-- RegisterActivity.kt
   |-- MainActivity.kt

---

## Security

- Passwords are never stored in plain text
- SHA-256 hashing is applied to every password before it is saved to the database
- User sessions are managed via SharedPreferences and cleared on logout
- No third-party advertising or analytics SDKs are included

---

## Automated Testing

Unit tests are located in:

   app/src/test/java/com/varsity/finsphere/FinSphereUnitTest.kt

Tests cover:

- Password hashing consistency — same input always produces the same hash
- Password hashing security — different inputs always produce different hashes
- SHA-256 output length validation
- Date range start and end of day calculations
- Period filtering logic — start of month is always before end of today
- Calendar epoch conversion correctness

Instrumented database tests are located in:

   app/src/androidTest/java/com/varsity/finsphere/FinSphereDatabaseTest.kt

These use an in-memory Room database to test all DAOs in isolation.

GitHub Actions automatically runs all tests and builds the debug APK on every push to main.
The workflow file is located at .github/workflows/build.yml.

---

## References

Android Developer Documentation. Available at: https://developer.android.com (Accessed: 27 April 2026).

Room Database Guide. Available at: https://developer.android.com/training/data-storage/room (Accessed: 27 April 2026).

Material Design 3 Guidelines. Available at: https://m3.material.io (Accessed: 27 April 2026).

Kotlin Programming Language. Available at: https://kotlinlang.org (Accessed: 27 April 2026).

Glide Image Loading Library. Available at: https://github.com/bumptech/glide (Accessed: 27 April 2026).

GitHub Actions for Android. Available at: https://github.com/marketplace/actions/automated-build-android-app-with-github-action (Accessed: 27 April 2026).

GitHub Actions Android Workflow Example. Available at: https://github.com/IMAD5112/Github-actions/blob/main/.github/workflows/build.yml (Accessed: 27 April 2026).

Gemini AI (Google, 2026) was used to assist with debugging errors in Android Studio and generating file structure. All generated code has been reviewed and understood by the author.

Google (2026) Gemini [Large language model]. Available at: https://gemini.google.com (Accessed: 27 April 2026).

Google (2026) Gemini response to prompt: 'Fix Visual Studio errors' [Large language model output]. Available at: https://gemini.google.com (Accessed: 27 April 2026).


---

FinSphere — Open Source Coding Module, 2026
