# Rick and Morty Wiki

This is a test assesment for wowzi technical assesments.

## Prerequisites

- [Node.js > 14](https://nodejs.org) and npm (Recommended: Use [nvm](https://github.com/nvm-sh/nvm))
- [Watchman](https://facebook.github.io/watchman)
- [JDK 11](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)
- [Android Studio and Android SDK](https://developer.android.com/studio)
- [Xcode 12](https://developer.apple.com/xcode)
- [Cocoapods 1.10.1](https://cocoapods.org)

For more details and troubleshooting: [Setting up the development environment](https://reactnative.dev/docs/environment-setup)

## Base dependencies

- [axios](https://github.com/axios/axios) for networking.
- [react-navigation](https://reactnavigation.org/) navigation library.
- [jest](https://facebook.github.io/jest/) and [react-native-testing-library](https://callstack.github.io/react-native-testing-library/) for testing.

## Folder structure

This template follows a very simple project structure:

- `src`: This folder is the main container of all the code inside the application.
  - `api`: Folder to store all methods to fetch data from api.
  - `components`: Folder to store all the components that you see in the application
    - `common`: Folder to store any common component that you use throughout the app (such as a generic button)
    - `Screen`: Folder to store components specific to that `Screen`.
  - `constants`: Folder to store any kind of constant.
  - `navigations`: Folder to store the navigators.
  - `screens`: Folder that contains all the application screens.
    - `Screen`: Each screen is stored inside its folder as an `index` file.
  - `utils`: Folder that contains utility services.
  - `types.ts`: Stores all the types used in the project.
- `App.js`: Main component that starts the whole app.
- `index.js`: Entry point of the application as per React-Native standards.

## Setup environments

### Available Scripts

#### `npm start`

Runs the app in development mode.

To reset or clear the React Native packager's cache, you can pass the `--reset-cache` flag to the start script:

```cmd
npm start -- --reset-cache
```

or

```cmd
yarn start -- --reset-cache
```

#### `yarn test`

Runs the [jest](https://github.com/facebook/jest) test runner on the tests.

#### `yarn run ios`

Like `npm start`, but also attempts to open the app in the iOS Simulator if you're on a Mac and have it installed.

#### `yarn run android`

Like `yarn start`, but also attempts to open the app on a connected Android device or emulator. Requires an installation of Android build tools (see [React Native docs](https://facebook.github.io/react-native/docs/getting-started.html) for detailed setup).

## Generate production version

These are the steps to generate `.apk`, `.aab` and `.ipa` files

### Android

1. Generate an upload key
2. Setting up gradle variables
3. Go to the android folder
4. Execute `./gradlew assemble[Env][BuildType]`

Note: You have three options to execute the project
`assemble:` Generates an apk that you can share with others.
`install:` When you want to test a release build on a connected device.
`bundle:` When you are uploading the app to the Play Store.

For more info please go [here](https://reactnative.dev/docs/signed-apk-android).

### iOS

1. Go to the Xcode
2. Select the schema
3. Select 'Any iOS device' as target
4. Product -> Archive

For more info please go [here](https://reactnative.dev/docs/publishing-to-app-store).

ensure you use the following commands when encounting arror due to debuging 

1. Update babel-jest to version 29.0.0 or higher: You can try updating the babel-jest package in your project to at least version 29.0.0 to meet the requirement of ts-jest@29.0.1. You can do this with the following command:

npm install babel-jest@^29.0.0

2. Use the --force flag: You can try using the --force flag when running the installation command to accept the potentially broken dependency resolution. This may not be the best option, but it might work if you're in a hurry or have no other choice:

npm install ts-jest@29.0.1 --force

3. Use the --legacy-peer-deps flag: You can also use the --legacy-peer-deps flag when running the installation command, which will make npm use an older, less strict algorithm for handling peer dependencies. This might help resolve the conflict:


npm install ts-jest@29.0.1 --legacy-peer-deps