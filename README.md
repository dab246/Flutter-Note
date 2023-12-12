# Bug-Note
Note the ways to handle common bug

### 1. `✗ Unable to find bundled Java version.` while upgrade version flutter

#### - Evidence
```
[!] Android Studio (version 2022.1)
    • Android Studio at C:\Program Files\Android Studio\Android Studio 2022.1.1.13
    • Flutter plugin can be installed from:
       https://plugins.jetbrains.com/plugin/9212-flutter
    • Dart plugin can be installed from:
       https://plugins.jetbrains.com/plugin/6351-dart
    X Unable to find bundled Java version.
    • Try updating or re-installing Android Studio.
```

#### - Solution

##### Way 1:

- Step 1: Command run in terminal

```
cd /Applications/Android\ Studio.app/Contents/jbr
ln -s ../jbr jdk
ln -s "/Library/Internet Plug-Ins/JavaAppletPlugin.plugin" jdk
```

- Step 2: Go to finder and find Android studio:

```
1. Right click and show package contents
2. At `Contents` then create new folder called jre
3. Copy contents of the jbr folder and paste into jre folder
```

- Step 3: Run again `flutter doctor -v`

##### Way 2:

- Command run in terminal:

```
cd /Applications/Android\ Studio.app/Contents/jre
ln -s ../jre jdk
ln -s "/Library/Internet Plug-Ins/JavaAppletPlugin.plugin" jdk
flutter doctor -v
```

### 2. Flutter Doctor warns about different paths after upgrading from 3.0.1 to 3.7.4

#### - Evidence

```
flutter doctor -v

[!] Flutter (Channel stable, 3.7.4, on macOS 13.1 22C65 darwin-arm64, locale en-VN)
    • Flutter version 3.7.4 on channel stable at /Users/dab.dev/FlutterDev/flutter
    ! Warning: `dart` on your path resolves to /opt/homebrew/Cellar/dart/2.18.0/libexec/bin/dart, which is not inside your current Flutter SDK checkout at
      /Users/dab.dev/FlutterDev/flutter. Consider adding /Users/dab.dev/FlutterDev/flutter/bin to the front of your path.
    • Upstream repository https://github.com/flutter/flutter.git
    • Framework revision b4bce91dd0 (30 hours ago), 2023-02-21 09:50:50 +0800
    • Engine revision 248290d6d5
    • Dart version 2.19.2
    • DevTools version 2.20.1
    • If those were intentional, you can disregard the above warnings; however it is recommended to use "git" directly to perform update checks and upgrades.
```

#### - Solution

Type in `nano ~/.zshrc:`

```export PATH="/Users/development/flutter/bin:$PATH"```

### 3. Ignoring ffi-1.13.1 because its extensions are not built. Try: gem pristine ffi --version 1.13.1

#### - Solution
 
 Run `brew install cocoapods`

 - For mac M1: `$ sudo gem install cocoapods`

### 4. CocoaPods could not find compatible versions for pod "XXX"

#### - Evidence

```
[!] CocoaPods could not find compatible versions for pod "AppAuth":
  In snapshot (Podfile.lock):
    AppAuth (= 1.4.0)

  In Podfile:
    flutter_appauth (from `.symlinks/plugins/flutter_appauth/ios`) was resolved to 0.0.1, which depends on
      AppAuth (= 1.6.0)


You have either:
 * out-of-date source repos which you can update with `pod repo update` or with `pod install --repo-update`.
 * changed the constraints of dependency `AppAuth` inside your development pod `flutter_appauth`.
   You should run `pod update AppAuth` to apply changes you've made.
```

#### - Solution

- Delete `Podfile.lock`
- Run `pod install`

Or

- Run `pod update AppAuth`

### 5. LoadError - `dlopen(/Library/Ruby/Gems/2.6.0/gems/ffi-1.15.0/lib/ffi_c.bundle, 0x0009): missing compatible arch in /Library/Ruby/Gems/2.6.0/gems/ffi-1.15.0/lib/ffi_c.bundle - /Library/Ruby/Gems/2.6.0/gems/ffi-1.15.0/lib/ffi_c.bundle`

- Run `sudo arch -x86_64 gem install ffi`
- Then run `arch -x86_64 pod update Firebase/Auth`

### 6. Downgrade flutter version

- Run command:
```
flutter downgrade <version>
```
- This command will use a specific version number. You can have the list of the available version numbers using flutter downgrade or [here](https://github.com/flutter/flutter/tags)
- Refer: https://stackoverflow.com/a/56127174

### 7. Fix iOS compile issues

- https://www.wafrat.com/fixing-ios-compile-issues-in-flutter/
