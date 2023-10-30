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

```
open -n -a /Applications/Google\ Chrome.app/Contents/MacOS/Google\ Chrome --args --user-data-dir="/tmp/chrome_dev_test" --disable-web-security
```
