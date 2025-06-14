# flutter-install-macos
Easy instruction for Flutter install on Mac OS.
## Install Brew on Mac OS
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

## Install XCode
Install XCode from App Store or from official Apple Web-site.

## Install XCode CLI
After installing Xcode, it is obligator to install Xcode CLI tools
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
echo 'export PATH="/opt/homebrew/opt/ruby/bin:$PATH"' >> ~/.zprofile
source ~/.zprofile
```

Check:
```bash
ruby -v    # Должен показывать версию из brew, например 3.3.x
which ruby # Должен быть /opt/homebrew/opt/ruby/bin/ruby
```

## CocoaPods install
Classic cocoapds instalation is pretty slow and can get several instalation errors
```bash
brew install cocoapods
pod setup
```

Check:
```bash
pod --version
```

## Flutter SDK install
