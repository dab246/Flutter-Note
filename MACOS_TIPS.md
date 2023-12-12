# MACOS TIPS

### 1. Error `zsh: command not found:`

RUN in terminal
```
$ PATH=/bin:/usr/bin:/usr/local/bin:/sbin:${PATH}
$ export PATH
```
### 2. Setup GitHub CLI manual

#### 2.1 Installation

- Install `Homebrew`

```
$ /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

- Install `gh`

```
$ brew install gh
```

- Check `gh` version

```
$ gh --version
```

#### 2.2 Configuration

- Run `$ gh auth login` to authenticate with your GitHub account

#### 2.3 Docs

- [GitHub CLI manual](https://cli.github.com/manual/)

## 3. Config FVM on Android Studio to be use multiple flutter sdk version

#### Docs

- https://fvm.app/docs/getting_started/configuration/

#### Steps config

- Install `Homebrew`

```
$ /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

- Install `fvm`

```
$ brew tap leoafarias/fvm
$ brew install fvm
```

- Install flutter versions

```
$ fvm install FLUTTER_VERSION
```

- Can list the versions which had been installed with command below:

```
$ fvm list             
Cache Directory:  /Users/xxx/fvm/versions

FLUTTER_VERSION
```

- Use fvm to change new version with command below:

```
$ cd project
$ fvm use FLUTTER_VERSION -f
```

- You can check the version by using

```
fvm flutter --version
```

You can select the version from Perferences. Search Flutter settings. You must have install Flutter plugin, so change the setting Flutter SDK path to your version like this: `xxx/project/.fvm/flutter_sdk`

Your project have the folder `.fvm` after execute the command `fvm use FLUTTER_VERSION -f` before. Specify the sdk path to your project `.fvm/flutter_sdk` absolute path.
