# FlutterFire: Seamless Integration of Your Flutter App with Firebase


## Requirements:

To ensure a seamless integration between your Flutter application and Firebase, please follow these steps:

### 1. Install NodeJS:
- You can obtain NodeJS from the official website by visiting [this link](https://nodejs.org/en).
---
### 2. Install Firebase CLI:
- Using npm, execute the following command to globally install the Firebase Command Line Interface (CLI):
```bash
npm install -g firebase-tools
```
- After installation, you need to authenticate your account. Run the following command:
```bash
firebase login
```
This will establish a connection between your local machine and Firebase, providing access to your Firebase projects. If you're on a remote machine without localhost access, use the command with the `--no-localhost` flag.
- To confirm proper CLI installation and account access, list your Firebase projects:
```bash
firebase projects:list
```
---
### 3. Install FlutterFire CLI:
- Install the FlutterFire Command Line Interface (CLI) by executing the following command using Dart's package manager, `pub`:
```dart
dart pub global activate flutterfire_cli
```

While `Firebase.initializeApp` initializes FlutterFire across all platforms using Dart, platform-specific options can vary.The FlutterFire CLI assists in this by generating a configuration file (default name: `firebase_options.dart`) used during initialization.

- To generate the configuration file, run the following command at your application's root
```
flutterfire configure
```
The configuration process includes the following steps:

1. Selecting a Firebase project (from the .firebaserc file or Firebase Console).
2. Identifying platforms requiring configuration (e.g., Android, iOS, macOS, & web).
3. Determining Firebase applications within chosen platforms for configuration extraction. The CLI attempts to match Firebase apps based on project configuration.
4. Creating a firebase_options.dart file within your project.

- The command supports the following option arguments:
  
|           Argument          |   Alias  | Description |
| :--------------------------:| :------: |    :----:   |
| --project                   |    -p    | Sets the Firebase Project ID to use. By default, the CLI will attempt to fetch the project defined in the `.firebaserc` file, or prompt you to select the project from the Firebase Console. |
| --account                   |    -e    | Sets the email address which should be used to authenticate with Firebase against. By default, this will use the primary account defined on the Firebase CLI. |
| --out                       |    -o    | Specifies the path & file name for the generated file. Defaults to "lib/firebase_options.dart". |
| --ios-bundle-id             |    -i    | The bundle identifier of your iOS app, e.g. "com.example.app". If no identifier is provided, an attempt will be made to automatically detect it from your "ios" folder (if it exists). |
| --macos-bundle-id           |    -m    | The bundle identifier of your macOS app, e.g. "com.example.app". If no identifier is provided, an attempt will be made to automatically detect it from your "macos" folder (if it exists). |
| --android-package-name      |    -a    | The package name of your Android app, e.g. "com.example.app". If no package name is provided, an attempt will be made to automatically detect it from your "android" folder (if it exists). |
| --[no-]apply-gradle-plugin  |    -g    | Whether to add the Firebase Gradle plugin to your Android app's build.gradle files and create the google-services.json file in your ./android/app folder. (defaults to on) |


- To view the current version of the FlutterFire CLI, run:
```
flutterfire --version
```

By following these instructions, you'll seamlessly integrate Firebase into your Flutter application using the FlutterFire plugins.
  
