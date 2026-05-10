# Zlunix - Flutter Enterprise Application

[![Flutter](https://img.shields.io/badge/Flutter-%2302569B.svg?style=for-the-badge&logo=Flutter&logoColor=white)](https://flutter.dev)
[![Dart](https://img.shields.io/badge/dart-%230175C2.svg?style=for-the-badge&logo=dart&logoColor=white)](https://dart.dev)
[![Architecture](https://img.shields.io/badge/Architecture-Clean%20MVI-green?style=for-the-badge)](https://blog.cleancoder.com/uncle-bob/2012/08/13/the-clean-architecture.html)

A premium, high-performance Flutter application designed for a CPA (Cost Per Action) platform. This project serves as the user-facing website where users can discover offers, earn rewards, track their progress, and manage their profile. Built with scalability, maintainability, and visual excellence in mind.

---

## 🚀 Project Overview

The **Zlunix** is a modern rewards platform that bridges the gap between advertisers and users. It provides a seamless experience for users to engage with various offerwalls (Tapjoy, Farly, etc.), complete tasks, and earn points that can be cashed out. The application is optimized for both Web and Mobile, ensuring a consistent and premium experience across all devices.

### Key Highlights:
- **Scalable Architecture**: Built using Clean Architecture and the MVI pattern.
- **Cross-Platform**: Supports Web, Android, and iOS.
- **Real-time Rewards**: Integrated with major offerwall SDKs for instant reward tracking.
- **Premium UI**: Custom-designed dark theme with glassmorphic elements and responsive layouts.

---

## 🛠 Tech Stack

| Category | Technologies |
| :--- | :--- |
| **Framework** | Flutter (SDK ^3.10.0) |
| **State Management** | Flutter BLoC / Cubit (MVI Pattern) |
| **Networking** | Dio, Retrofit |
| **Dependency Injection** | Get_it, Injectable |
| **Navigation** | GoRouter |
| **UI & Styling** | Flutter ScreenUtil, Svg, Toastification |
| **Persistence** | Secure Storage |
| **Analytics & Ads** | Google Mobile Ads, Tapjoy, Farly SDK |
| **Localization** | Flutter Intl (ARB files) |

---

## 🏗 Architecture

This project follows a strict **Clean Architecture** approach combined with the **MVI (Model-View-Intent)** pattern for state management. This ensures a clear separation of concerns and makes the codebase highly testable and maintainable.

### Layers:
1.  **Domain Layer**: Contains pure Dart code (Entities, Repository Interfaces, and Use Cases). It has zero external dependencies.
2.  **Data Layer**: Responsible for repository implementations and data management logic. It coordinates between the API layer and local storage.
3.  **API Layer**: Handles remote infrastructure. Includes Retrofit clients, API Models (DTOs), and API-specific mappers.
4.  **Presentation Layer**: The UI and logic layer. Contains Screens, Widgets, and ViewModels (Cubits).
5.  **Core Layer**: Shared utilities, constants, themes, and dependency injection configuration.

### MVI Implementation Rules:
- **ViewModel**: The only public method is `doIntent(Event)`. All business logic is private.
- **State**: Immutable state classes using `Equatable` and `copyWith`.
- **Events**: Sealed classes representing user intents.

---

## ✨ Features

- 📱 **Onboarding**: A smooth introduction to the platform for new users.
- 🔐 **Authentication**: Secure login with Social Sign-In (Google) and standard authentication.
- 📊 **Dashboard**: A comprehensive overview of user earnings, progress, and featured offers.
- 💰 **Earn Rewards**: Integrated Offerwalls (Tapjoy, Farly) for earning points through various tasks.
- 🏆 **Ranking System**: Competitive leaderboard to see top earners in the community.
- 💳 **Cashout System**: Multiple redemption options for converting points into rewards.
- 🔔 **Notifications**: Real-time updates on offer completion and platform news.
- 🛠 **Profile Management**: Personalized settings and account management.
- 📄 **Legal & Policies**: Integrated Privacy Policy and Terms of Service.

---

## 📁 Folder Structure

```text
lib/
├── api/                # Retrofit Clients, DTOs, API Mappers
├── core/               # DI, Extensions, Themes, Constants, Utils
├── data/               # Repository Implementations, Local DataSources
├── domain/             # Entities, UseCases, Repository Interfaces
├── presentation/       # UI Layers (Screens, Widgets, ViewModels)
│   ├── auth/
│   ├── home/
│   ├── earn_page/
│   └── ... (features)
├── generated/          # Auto-generated code (Intl, etc.)
├── l10n/               # Localization ARB files
└── main.dart           # Application entry point
```

---

## 🏁 How to Run

### 1. Prerequisites
- [Flutter SDK](https://docs.flutter.dev/get-started/install) (version ^3.10.0)
- [Dart SDK](https://dart.dev/get-started/sdk)
- A code editor (VS Code or Android Studio)

### 2. Setup
Clone the repository:
```bash
git clone https://github.com/youssefmdev22/cpa_user_website.git
cd cpa_user_website
```

Install dependencies:
```bash
flutter pub get
```

Generate code (Retrofit, Injectable, etc.):
```bash
flutter pub run build_runner build --delete-conflicting-outputs
```

### 3. Run
Launch the application:
```bash
flutter run -d chrome # For Web
flutter run # For Mobile
```

---

## 📸 Screenshots

### 📱 Mobile View

| Onboarding | Login | Register | Forgot Password |
| :---: | :---: | :---: | :---: |
| ![Onboarding](screenshots/mobile/onboarding.png) | ![Login](screenshots/mobile/login.png) | ![Register](screenshots/mobile/register.png) | ![Forgot Password](screenshots/mobile/forget.png) |

| Earn | Offerwall | Ranking | Cashout |
| :---: | :---: | :---: | :---: |
| ![Earn](screenshots/mobile/earn.gif) | ![Offerwall](screenshots/mobile/offerwall.png) | ![Ranking](screenshots/mobile/ranking.png) | ![Cashout](screenshots/mobile/cashout.png) |

| Profile | Notifications | Profile Settings | Policies |
| :---: | :---: | :---: | :---: |
| ![Profile](screenshots/mobile/profile.gif) | ![Notifications](screenshots/mobile/notifications.png) | ![Profile Settings](screenshots/mobile/profile_settings.png) | ![Policies](screenshots/mobile/policies.png) |

| Cashout Dialog | Users Profile |
| :---: | :---: |
| ![Cashout Dialog](screenshots/mobile/cashout_dialog.png) | ![Users Profile](screenshots/mobile/users_profile.png) |

---

### 💻 Web View

| Login | Register | Forgot Password | Earn |
| :---: | :---: | :---: | :---: |
| ![Login](screenshots/web/login.png) | ![Register](screenshots/web/register.png) | ![Forgot Password](screenshots/web/forget.png) | ![Earn](screenshots/web/earn.gif) |

| Offerwall | Ranking | Cashout | Cashout Dialog |
| :---: | :---: | :---: | :---: |
| ![Offerwall](screenshots/web/offerwall.png) | ![Ranking](screenshots/web/ranking.png) | ![Cashout](screenshots/web/cashout.png) | ![Cashout Dialog](screenshots/web/cashout_dialog.png) |

| Profile | Profile Settings | Policies | Users Profile |
| :---: | :---: | :---: | :---: |
| ![Profile](screenshots/web/profile.png) | ![Profile Settings](screenshots/web/profile_settings.png) | ![Policies](screenshots/web/policies.png) | ![Users Profile](screenshots/web/users_profile.png) |

---

## 🤝 Contributors

- [Youssef Mohamed](https://github.com/youssefmdev22)
- [Moaz Osama](https://github.com/moazosama1)
- [Mohamed Hossam El-Bably](https://github.com/Bablu521)

---
<p align="center">Built with ❤️ by the Flutter.</p>
