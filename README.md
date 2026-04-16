# Abacus

## Overview

Abacus is a mobile expense management application built with Flutter for the course `CT312H: MOBILE PROGRAMMING`. This is a group project developed to support personal finance tracking through a clean mobile interface and practical budgeting features.

The application focuses on helping users record transactions, organize income and expense categories, monitor savings goals, manage account information, and receive local notifications. The project uses `PocketBase` for authentication and remote data handling, while `sqflite` is used for local data persistence on the device.

## Course And Team Information

This repository contains a group project for the course `CT312H: MOBILE PROGRAMMING`.

Semester 1, Academic year: 2025-2026

**Student ID 1**: Huỳnh Tấn Đạt

**Student Name 1**: B2203438

**Student ID 2**: Nguyễn Minh Nhựt

**Student Name 2**: B2205896

**Class Number**: M01

## Installation

### Prerequisites

Before running the project, make sure the following tools are installed:

- `Flutter SDK` compatible with the project's Dart SDK requirement in `pubspec.yaml`
- `Android Studio` or another IDE with Flutter support
- An `Android emulator` or a physical Android device
- A running `PocketBase` server

You can verify your Flutter environment with:

```powershell
flutter doctor
```

### 1. Clone the repository

```powershell
git clone <your-repository-url>
cd D:\File_Nick\Workspace\Abacus
```

### 2. Install dependencies

Run the following command in the project root:

```powershell
flutter pub get
```

### 3. Create the environment file

This project loads environment variables from a `.env` file at startup. Create a file named `.env` in the project root with the following content:

```env
POCKETBASE_URL=http://10.0.2.2:8090
```

Why this value is important:

- `10.0.2.2` is the special address that lets an Android emulator talk to the host machine.
- If you use a physical device, replace it with your computer's local IP address, for example: `http://192.168.1.10:8090`
- If you use another backend host, update `POCKETBASE_URL` accordingly

### 4. Start PocketBase

Make sure your PocketBase server is running before launching the Flutter app. If PocketBase is not running, features such as sign up, login, and profile synchronization will not work correctly.

Example:

```powershell
.\pocketbase.exe serve --http 0.0.0.0:8090
```

### 5. Run the Flutter application

List available devices:

```powershell
flutter devices
```

Run the application:

```powershell
flutter run
```

If you want to run on a specific device, use:

```powershell
flutter run -d <device-id>
```

## Usage

After the application starts, the typical flow is:

1. Launch the app and wait for the splash screen to finish.
2. Create an account or log in with an existing account.
3. Add income and expense transactions.
4. Create and manage spending categories.
5. Track savings goals and monitor monthly summaries.
6. Open the account screen to update profile information and app settings.

Main functional areas included in the current codebase:

- Authentication with sign up, login, session restore, and logout
- Home dashboard with balance, income and expense summaries, monthly reports, and recent transactions
- Transaction management with add, edit, and grouped transaction views
- Category management for both expense and income categories
- Savings goal tracking
- Account profile management
- Theme switching and local notification support

## Important Notes

- The project is a Flutter mobile application and is currently structured primarily for mobile platforms.
- The file `.env` is required because the app calls `dotenv.load()` during startup.
- If `PocketBase` is unavailable, authentication-related features may fail even if the app launches successfully.
- The Android emulator default backend URL is `http://10.0.2.2:8090`.
- Local data is stored with `sqflite`, which means some information is persisted on the device.
- The existing `test/widget_test.dart` file is still the default Flutter sample test and does not reflect the actual application flow.
