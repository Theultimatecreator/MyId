
# Apay | Android Application

This document provides a comprehensive overview of the Apay Android application, including its architecture, features, and setup instructions. It is intended for developers who will be contributing to or maintaining the project.

## 1. Project Overview

Apay is a native Android application that provides a mobile payment solution for both businesses and individual clients. The application is divided into two main flavors: **Apay Business** and **Apay Client**.

*   **Apay Business:** This flavor is designed for merchants and businesses to accept payments, manage invoices, and track transactions.
*   **Apay Client:** This flavor is designed for individual users to make payments, manage their cards, and view their transaction history.

## 2. Features

### Apay Business

*   Accept payments from Apay clients.
*   Create and manage invoices.
*   Track transaction history.
*   Manage employees and agents.
*   Withdraw funds to a bank account.

### Apay Client

*   Make payments to Apay businesses.
*   Add and manage credit/debit cards.
*   View transaction history.
*   NFC card reading for quick payments.
*   Deep linking for a seamless user experience.

## 3. Technical Stack

The Apay application is built with a modern tech stack that emphasizes code quality, maintainability, and performance.

### Core Technologies

*   **Programming Language:** 100% [Kotlin](https://kotlinlang.org/)
*   **UI Toolkit:** [Jetpack Compose](https://developer.android.com/jetpack/compose)
*   **Asynchronous Programming:** [Kotlin Coroutines](https://kotlinlang.org/docs/reference/coroutines-overview.html) and [Flow](https://kotlin.github.io/kotlinx.coroutines/kotlinx-coroutines-core/kotlinx.coroutines.flow/)
*   **Dependency Injection:** [Hilt](https://developer.android.com/training/dependency-injection/hilt-android)
*   **Networking:** [Ktor](https://ktor.io/)
*   **Local Storage:** [Room](https://developer.android.com/training/data-storage/room)
*   **Navigation:** [Jetpack Navigation Compose](https://developer.android.com/jetpack/compose/navigation)

### Libraries

*   **Accompanist:** A collection of extension libraries for Jetpack Compose.
*   **Coil:** An image loading library for Android.
*   **Lottie:** A library for parsing Adobe After Effects animations exported as json.
*   **Firebase:** A suite of tools for building, improving, and growing your app.
    *   **Firebase Messaging:** For push notifications.
    *   **Firebase Dynamic Links:** For deep linking.
*   **Adjust:** A mobile measurement partner for attribution and analytics.
*   **Yandex MapKit:** A library for displaying maps and handling location-based services.

## 4. Clean Architecture

The Apay application follows the principles of Clean Architecture, which separates the codebase into three main layers: **Data**, **Domain**, and **Presentation**.

### Data Layer

The data layer is responsible for providing data to the application. It includes the following components:

*   **Remote Data Sources:** These are responsible for fetching data from the network (e.g., REST APIs).
*   **Local Data Sources:** These are responsible for caching data on the device (e.g., Room database).
*   **Repositories:** These are responsible for coordinating data from different data sources.

### Domain Layer

The domain layer contains the business logic of the application. It includes the following components:

*   **Use Cases:** These are responsible for encapsulating a single business rule.
*   **Entities:** These are the plain data classes that represent the core data of the application.

### Presentation Layer

The presentation layer is responsible for displaying the UI to the user. It includes the following components:

*   **Views (Jetpack Compose):** These are the UI components that are displayed to the user.
*   **ViewModels:** These are responsible for preparing and managing the data for the UI.

## 5. Project Directory Structure

The Apay application is organized into a multi-module project. Each module represents a specific feature or layer of the application.

```
.
├── apay-business
├── apay-client
├── common
│   ├── core
│   ├── core-ui
│   ├── auth
│   ├── ...
├── business
│   ├── registration
│   ├── settings
│   ├── ...
└── client
    ├── client-registration
    ├── client-profile
    └── ...
```

## 6. Getting Started

### Prerequisites

*   Android Studio Iguana | 2023.2.1 or later
*   Android SDK 34 or later
*   Java 17 or later

### Installation

1.  Clone the repository: `git clone https://github.com/your-username/apay-android.git`
2.  Open the project in Android Studio.

### Build and Run

1.  Select the desired build variant (`apay-business` or `apay-client`).
2.  Run the application on an emulator or a physical device.

## 7. Configuration

### Firebase

1.  Create a new Firebase project.
2.  Add an Android app to the project.
3.  Download the `google-services.json` file and place it in the `app` directory of the `apay-business` and `apay-client` modules.

### Keystore

1.  Create a new keystore file.
2.  Configure the `keystore.properties` file with the keystore path, alias, and password.

### SDK Path

1.  Make sure the `local.properties` file contains the correct path to the Android SDK.

## 8. Testing

The Apay application uses a combination of unit tests and instrumentation tests to ensure the quality of the code.

### Unit Tests

Unit tests are located in the `test` directory of each module. They are written with JUnit and Mockito.

To run the unit tests, execute the following command:

```
./gradlew test
```

### Instrumentation Tests

Instrumentation tests are located in the `androidTest` directory of each module. They are written with Espresso and UI Automator.

To run the instrumentation tests, execute the following command:

```
./gradlew connectedAndroidTest
```

## 9. Code Quality Tools

The Apay application uses the following code quality tools to ensure a high-quality codebase:

*   **Detekt:** A static code analysis tool for Kotlin.
*   **ktlint:** A linter for Kotlin.

To run the code quality checks, execute the following command:

```
./gradlew detekt
```

## 10. Contributing Guidelines

Please read our [contributing guidelines](CONTRIBUTING.md) before submitting a pull request.

## 11. License and Roadmap

The Apay application is licensed under the [MIT License](LICENSE).

For information about the future roadmap of the project, please see our [roadmap](ROADMAP.md).
