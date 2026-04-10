# Sanjay Vaishya App

A modern Android WebView application that provides a native wrapper for a web-based application with enhanced user experience and native Android features.

## Overview

Sanjay Vaishya App is an Android application that wraps a web application (hosted at `https://app-sanjay.indiacybercafe.com/`) in a native Android WebView. The app provides a seamless browsing experience with splash screen animation, file upload support, and intelligent back button navigation.

## Features

- **WebView Integration**: Displays web content with optimized performance settings
- **Splash Screen**: Custom splash screen with 500ms animation before main activity
- **File Upload Support**: Native file chooser for uploading files through the web interface
- **Progress Indicator**: Visual feedback showing page loading progress
- **Back Button Navigation**: Intuitive back button handling for web navigation
- **Error Handling**: Graceful error handling for resource loading failures
- **Full Screen Support**: Fullscreen display with status bar integration
- **JavaScript Support**: Enabled JavaScript for interactive web content

## Project Structure

```
Sanjay_Vaishya_App/
├── app/                           # Main application module
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/
│   │   │   │   └── com/sanjayvaishya/app/
│   │   │   │       ├── MainActivity.java       # Main WebView activity
│   │   │   │       └── SplashActivity.java     # Splash screen activity
│   │   │   ├── res/
│   │   │   │   ├── layout/
│   │   │   │   │   ├── activity_main.xml       # Main activity layout
│   │   │   │   │   └── activity_splash.xml     # Splash activity layout
│   │   │   │   ├── drawable/                   # Drawable resources
│   │   │   │   ├── values/                     # String, color, and style resources
│   │   │   │   └── xml/
│   │   │   └── AndroidManifest.xml
│   │   ├── androidTest/                        # Android instrumented tests
│   │   └── test/                               # Unit tests
│   ├── build.gradle
│   └── proguard-rules.pro
├── build.gradle                   # Root build configuration
├── gradle.properties
├── settings.gradle
└── README.md                      # This file
```

## Requirements

- **Android SDK**: Minimum API 23 (Android 6.0), Target API 36 (Android 15)
- **Java**: Version 11 or higher
- **Gradle**: 8.0 or higher
- **Android Studio**: 2022.1 or later (recommended)

## Dependencies

Key dependencies used in this project:

- `androidx.appcompat:appcompat` - AppCompat library for backward compatibility
- `com.google.android.material:material` - Material Design components
- `androidx.activity:activity` - Activity support library
- `androidx.constraintlayout:constraintlayout` - Constraint layout for UI design
- `androidx.core:core-splashscreen:1.0.0` - Splash screen compatibility
- `androidx.test.runner:runner` - Android testing support

See `gradle/libs.versions.toml` for the complete dependency list.

## Installation & Setup

### 1. Clone the Repository
```bash
git clone <repository-url>
cd Sanjay_Vaishya_App
```

### 2. Configure Local Environment
- Ensure `JAVA_HOME` environment variable is set to Java 11+
- The `local.properties` file will be automatically created by Android Studio with your Android SDK path

### 3. Build the Project
Using Gradle wrapper:
```bash
./gradlew build
```

Or using Android Studio:
- Open the project in Android Studio
- Click **Build** → **Make Project**

### 4. Run the Application
```bash
./gradlew installDebug
```

Or use Android Studio to run on an emulator or connected device.

## Configuration

### Web URL
The application loads content from:
```
https://app-sanjay.indiacybercafe.com/
```

To change the URL, edit `WEBSITE_URL` constant in [MainActivity.java](app/src/main/java/com/sanjayvaishya/app/MainActivity.java):
```java
private static final String WEBSITE_URL = "https://your-url.com/";
```

### Build Configuration
- **App ID**: `com.sanjayvaishya.app`
- **Version Code**: 1
- **Version Name**: 1.0
- **Min SDK**: 23
- **Target SDK**: 36

## Key Features Implementation

### MainActivity.java
- Initializes WebView with optimized settings
- Handles JavaScript evaluation callback
- Implements custom WebViewClient for error handling and page tracking
- Implements custom WebChromeClient for file uploads and progress updates
- Manages back button navigation for web history
- Handles activity state save/restore

### SplashActivity.java
- Displays splash screen for 500ms
- Automatically transitions to MainActivity
- Uses fullscreen display mode

## Permissions

The application requires the following Android permissions:

```xml
<uses-permission android:name="android.permission.INTERNET" />
```

This permission allows the application to access the internet and load web content.

## Building for Release

To build a release APK:

```bash
./gradlew assembleRelease
```

The signed APK can be created using Android Studio's build signing configuration. The app includes ProGuard configuration for code obfuscation in release builds.

Release artifacts are located in `app/release/` directory.

## ProGuard Configuration

ProGuard rules are defined in [proguard-rules.pro](app/proguard-rules.pro) for code optimization and obfuscation in release builds.

## Testing

### Unit Tests
Located in `app/src/test/java/`
```bash
./gradlew testDebugUnitTest
```

### Instrumented Tests
Located in `app/src/androidTest/java/`
```bash
./gradlew connectedAndroidTest
```

## Troubleshooting

### BuildConfig Issues
If you encounter BuildConfig errors, ensure:
- Android Gradle Plugin is up to date
- Sync Gradle files with Project (File → Sync Now)

### WebView Loading Issues
- Check internet connectivity
- Verify the website URL is accessible
- Enable JavaScript in WebView settings

### Permission Denied Errors
- Ensure `INTERNET` permission is declared in AndroidManifest.xml
- Check device network settings

## API Level Compatibility

- **API 23-30**: Uses baseline profile `baselineProfiles/1/app-release.dm`
- **API 31+**: Uses baseline profile `baselineProfiles/0/app-release.dm`

Baseline profiles are used for runtime performance optimization.

## Contributing

Contributions are welcome! Please follow these guidelines:
1. Maintain code style consistency
2. Test changes thoroughly on multiple API levels
3. Update documentation as needed
4. Create meaningful commit messages

## License

This project is proprietary software. Unauthorized copying or distribution is prohibited.

## Author

**Sanjay Vaishya**  
Developer | Assistance | Help & Support

## Contact & Support

For issues, questions, or support, please contact:
- Email: [Your contact email]
- Website: https://app-sanjay.indiacybercafe.com/

---

**Last Updated**: April 2026  
**App Version**: 1.0  
**Target Android Version**: 15 (API 36)
