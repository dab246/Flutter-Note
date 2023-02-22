# Bug-Note
Note the ways to handle common bug

### 1. `✗ Unable to find bundled Java version.` while upgrade version flutter

#### Way 1:

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

#### Way 2:

- Command run in terminal:

```
cd /Applications/Android\ Studio.app/Contents/jre
ln -s ../jre jdk
ln -s "/Library/Internet Plug-Ins/JavaAppletPlugin.plugin" jdk
flutter doctor -v
```
