### CODE TIPS

1. To update the dependencies in `pubspec.yaml`

- A specific dependency:

```
flutter pub upgrade package_name
```

- All the dependencies:

```
flutter pub upgrade
```

2. Disable CORS in chrome Mac

- Way 1: Open Chrome with `--disable-web-security`

```
open -n -a /Applications/Google\ Chrome.app/Contents/MacOS/Google\ Chrome --args --user-data-dir="/tmp/chrome_dev_test" --disable-web-security
```

- Web 2: Add run args `--web-browser-flag "--disable-web-security"`

![Screenshot 2024-01-29 at 00 15 41](https://github.com/dab246/Flutter-Note/assets/80730648/f4befc44-676c-4b0e-b1f1-1ec483805965)

3. Run flutter Web on mobile chrome from IDE

Using a little `bash/expect` script

```
#!/usr/bin/expect -f

set timeout -1


spawn sh -i -c {
    flutter run -d web-server --web-port 49403
}

set run_id $spawn_id

expect "For a more detailed help message, press \"h\". To quit, press \"q\"."
spawn sh -c {
    adb reverse tcp:49403 tcp:49403
    adb shell am start -a android.intent.action.VIEW -d http://localhost:49403
}

interact -i $run_id
```

Related: https://stackoverflow.com/a/68771002
