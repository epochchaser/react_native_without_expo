# React native setting without expo.

#### 1. Install react-native-cli

```bash
yarn global add react-native-cli
```

#### 2. Initialize react-native app

```bash
react-native init [PROJECT_NAME_HERE]
```

#### 3. Java Development Kit

React Native requires a recent version of the Java SE Development Kit (JDK). [Download and install Oracle JDK 8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) if needed. You can also use [OpenJDK 8](http://openjdk.java.net/install/) as an alternative.

#### 4. Install Android Studio

Setting up your development environment can be somewhat tedious if you're new to Android development. If you're already familiar with Android development, there are a few things you may need to configure. In either case, please make sure to carefully follow the next few steps.

1. Install Android Studio
   [Download and install Android Studio](https://developer.android.com/studio/). Choose a "Custom" setup when prompted to select an installation type. Make sure the boxes next to all of the following are checked:

   - Android SDK
   - Android SDK Platform
   - Performance (Intel ® HAXM)
   - Android Virtual Device
     Then, click "Next" to install all of these components.
     <br>

     > If the checkboxes are grayed out, you will have a chance to install these components later on.
     > <br>

     Once setup has finalized and you're presented with the Welcome screen, proceed to the next step.

2. Install the Android SDK
   Android Studio installs the latest Android SDK by default. Building a React Native app with native code, however, requires the Android 8.1 (Oreo) SDK in particular. Additional Android SDKs can be installed through the SDK Manager in Android Studio.

   The SDK Manager can be accessed from the "Welcome to Android Studio" screen. Click on "Configure", then select "SDK Manager".
   <br>

   > The SDK Manager can also be found within the Android Studio "Preferences" dialog, under Appearance & Behavior → System Settings → Android SDK.
   > <br>

   Select the "SDK Platforms" tab from within the SDK Manager, then check the box next to "Show Package Details" in the bottom right corner. Look for and expand the Android 8.1 (Oreo) entry, then make sure the following items are checked:

   - Android SDK Platform 27
   - Intel x86 Atom_64 System Image or Google APIs Intel x86 Atom System Image

   Next, select the "SDK Tools" tab and check the box next to "Show Package Details" here as well. Look for and expand the "Android SDK Build-Tools" entry, then make sure that 27.0.3 is selected.
   <br>

   Finally, click "Apply" to download and install the Android SDK and related build tools.
   <br>

3. Configure the ANDROID_HOME environment variable
   ```bash
   export ANDROID_HOME=$HOME/Library/Android/sdk
   export PATH=$PATH:$ANDROID_HOME/emulator
   export PATH=$PATH:$ANDROID_HOME/tools
   export PATH=$PATH:$ANDROID_HOME/tools/bin
   export PATH=$PATH:$ANDROID_HOME/platform-tools
   ```

#### 5. Creating a new application

```bash
react-native init [PROJECT_NAME_HERE]
```

#### 6. Running your React Native application

```bash
cd [PROJECT_NAME_HERE]
react-native run-android
```
#### 7. Release Settings

create [keystore and configuration](https://facebook.github.io/react-native/docs/signed-apk-android.html)

```bash
cd android && ./gradlew assembleRelease
```
