# 🌱 Habit Tracking IOS

A modern iOS habit tracking application that helps users build and maintain daily habits using Firebase Authentication and Firebase Realtime Database.

## ✨ Features

- User authentication with email and password
- Real-time habit tracking using Combine
- Add daily habits
- Mark habits as completed for the day
- Secure user data with Firebase authentication
- Responsive and intuitive SwiftUI design

## 🏗️ Technical Architecture

### Architecture Overview

The application follows Clean Architecture principles with MVVM pattern, ensuring:

- Clear separation of concerns
- High testability
- Scalable and maintainable codebase
- Unidirectional data flow with Combine

### Key Technical Decisions

#### UI Layer

- **SwiftUI**: Modern declarative UI framework
- **Navigation Stack**: Type-safe iOS navigation
- **Combine Framework**: Reactive programming
- **MVVM Pattern**: Separation of UI logic and data
- **@Published and @State**: Reactive state management

#### Domain Layer

- **Use Cases**: Encapsulated business logic
- **Protocols**: Modular and testable code design

## 🔄 Trade-offs & Decisions

1. **Authentication Strategy**

   - Chose email/password authentication for simplicity
   - Implemented robust validation and error handling using Combine

2. **Data Persistence**

   - Leveraged Firebase Realtime Database for instant updates
   - Implemented strict security rules for user data privacy

3. **UI Implementation**
   - Used SwiftUI for declarative and reactive UI components
   - Implemented responsive design for various iOS device sizes

## 🔜 Future Improvements

1. **Technical**

   - Implement more authentication methods (Apple Sign-In, Google)
   - Add comprehensive unit and integration tests
   - Implement habit streaks and progress tracking with Core Data

2. **User Experience**
   - Implement habit reminders using UserNotifications
   - Add detailed habit analytics
   - Create custom habit categories

## 🛠️ Setup & Installation

1. Clone the repository
2. Set up Firebase project
   - Create Firebase project
   - Add GoogleService-Info.plist to the project
3. Configure Firebase Realtime Database security rules
4. Build and run the project

### Firebase Realtime Database Rules

```json
{
  "rules": {
    "habits": {
      "$uid": {
        ".read": "auth !== null && auth.uid === $uid",
        ".write": "auth !== null && auth.uid === $uid"
      }
    }
  }
}
```
