# flutter-install-macos
Easy instruction for Flutter install on Mac OS.
## Install Brew on Mac OS
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
Add brew in path, if brew is asking for it. Example:
```bash
echo >> /Users/<user_name>/.zprofile
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> /Users/<user_name>/.zprofile
eval "$(/opt/homebrew/bin/brew shellenv)"
```

## Install XCode
Install XCode from App Store or from official Apple Web-site.

## Install XCode CLI
After installing Xcode, if you installed XCode at first and Homebrew after that - brew would install XCode CLI automatically
```bash
xcode-select --install
```

Now it is required to accept license
```bash
sudo xcodebuild -license accept
```

## Install actual ruby for MacOS
```bash
brew install ruby
```

And after install next step is to set up new Ruby as default to system:
```bash
echo 'export PATH="/opt/homebrew/opt/ruby/bin:$PATH"' >> ~/.zshrc
source ~/.zshrc 
```

For check, after addind new ruby path to zhrc restart console and use this command:
```bash
ruby -v    # It shoud show version 3.3.x
which ruby # Should be /opt/homebrew/opt/ruby/bin/ruby
```

## CocoaPods install
Classic cocoapds instalation with gem is pretty slow and can get several instalation errors, 
nowaday we can install cocoapods via brew, it would take much less time.
```bash
brew install cocoapods
pod setup
```

Check:
```bash
pod --version
```

## Install Rosetta2
```bash
sudo softwareupdate --install-rosetta --agree-to-license
```

## Flutter SDK install
### Download & install Flutter SDK directly
Download package from officiala web-site and create folder for it
```bash
mkdir -p ~/development
cd ~/development
unzip ~/Downloads/flutter_macos_3.29.3-stable.zip
```
Adding Flutter to PATH
```bash
echo 'export PATH="$PATH:$HOME/development/flutter/bin"' >> ~/.zshrc
source ~/.zshrc
```
Check up result of installation
```bash
which flutter
flutter --version
```
These two commands would show path of Flutter SDK and version of Flutter

## Flutter Doctor
After install easiest way to understand what to do further - is to use command flutter doctor
```bash
flutter doctor
```
It would show something like this:
```bash
Doctor summary (to see all details, run flutter doctor -v):
[✓] Flutter (Channel stable, 3.29.3, on macOS 15.5 24F74 darwin-arm64 (Rosetta),
    locale en-US)
[✗] Android toolchain - develop for Android devices
    ✗ Unable to locate Android SDK.
      Install Android Studio from:
      https://developer.android.com/studio/index.html
      On first launch it will assist you in installing the Android SDK
      components.
      (or visit https://flutter.dev/to/macos-android-setup for detailed
      instructions).
      If the Android SDK has been installed to a custom location, please use
      `flutter config --android-sdk` to update to that location.

[!] Xcode - develop for iOS and macOS       
    ✗ Xcode installation is incomplete; a full installation is necessary for iOS
      and macOS development.
      Download at: https://developer.apple.com/xcode/
      Or install Xcode via the App Store.
      Once installed, run:
        sudo xcode-select --switch /Applications/Xcode.app/Contents/Developer
        sudo xcodebuild -runFirstLaunch
[✓] Chrome - develop for the web
[!] Android Studio (not installed)
[✓] Connected device (2 available)            
[✓] Network resources

! Doctor found issues in 3 categories.
```

As displayed can see
1. Doctor asks to install Android Studio, it's not extra required, but it would make installation much easier
2. Xcode need initiation
3. Android toolchain is unable - it can be done only after android install.


After this two commands flutter became ready to work with iOS and XCode
```bash
sudo xcode-select --switch /Applications/Xcode.app/Contents/Developer
sudo xcodebuild -runFirstLaunch
```

Now we are installing Android Studio(for example 2024.3.2)

After installation we need to accept all requirements and install components

On start page of Android Studio we need to go to "More Actions" and chose SDK Manager

Then on way going to SDK tools tab on top and searching for Android SDK Command Line Tools

Installing it, and after that we can run flutter doctor again.

Using command provided by Flutter Doctor:
```bash

```

And again check flutter doctor:
```bash

```

Result should look like that:



