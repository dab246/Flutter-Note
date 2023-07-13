# MACOS TIPS

### 1. Error `zsh: command not found:`

RUN in terminal
```
PATH=/bin:/usr/bin:/usr/local/bin:/sbin:${PATH}
export PATH
```
### 2. Setup GitHub CLI manual

#### 2.1 Installation

- Install `Homebrew`

```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

- Install `gh`

```
brew install gh
```

- Check `gh` version

```
gh --version
```

#### 2.2 Configuration

- Run `gh auth login` to authenticate with your GitHub account

#### 2.3 Docs

- [GitHub CLI manual](https://cli.github.com/manual/)
