# Computer Setup

## Atom-Config
Download [Atom](https://github.com/atom/atom/releases/tag/v1.50.0) first from its GitHub website.

### Install Packages

1. platformio-ide-terminal (Before installing please pre-install visual studio)
2. atom-beautify
3. tabs-to-spaces
4. git-plus
5. color-picker
6. autocomplete

### Config Settings

In `file` > `Config`, please add the followings, 
```
"*":
  core:
    telemetryConsent: "no"
  editor:
    fontSize: 22
    invisibles: {}
    showInvisibles: true
  "exception-reporting":
    userId: "6baad082-b933-4f93-acf5-fea77bb41230"
  "line-ending-selector":
    defaultLineEnding: "LF"
  "platformio-ide-terminal":
    core:
      autoRunCommand: "D:\\cmder\\atom.bat && conda activate nlp && clear"
      shell: "C:\\Windows\\System32\\cmd.exe"
  "tabs-to-spaces":
    onSave: "untabify"
```

### Integrate Cmder

1. Install `platformio-ide-terminal`.
2. Create `atom.bat` in cmder root folder.
```
@echo off 
SET CMDER_ROOT=C:\Path\To\cmder
%CMDER_ROOT%\vendor\init.bat
```
3. Settings in `platformio-ide-terminal`.
- Auto Run Command: `C:\Path\To\cmder\atom.bat && clear`
- Shell Override: `C:\Windows\System32\cmd.exe`
4. (Optional) If you want to set up conda environment, please go to this [tutorial](https://github.com/penguinwang96825/Set-Up-Conda-Environment). After you build conda environment, set command in `Auto Run Command` to `C:\Path\To\cmder\atom.bat && conda activate env_name && clear`.

## GitHub Config

### GitHub SSH Public Key
Reference from https://git-scm.com/book/en/v2/Git-on-the-Server-Generating-Your-SSH-Public-Key

```
ssh-keygen -o
cat ~/.ssh/id_rsa.pub
```

## Office Config

### MathType

1. Install MathType from [here]().
2. Unlock with product key: `MTWE691-011084-r0xyl`
3. Copy `MathPage.wll` from `C:\Program Files (x86)\MathType\MathPage\64` folder.
4. Copy `MathType Commands 6 For Word 2013.dotm` from `C:\Program Files (x86)\MathType\Office Support\64` folder.
5. Paste these two file to `C:\Program Files\Microsoft Office\root\Office16\STARTUP` folder.

## MAC-Iterm-Config

### Install Xcode
Download Xcode from Mac App Store.

### Install Brew
Open terminal and type `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"`.

### Install Iterm2
1. Open terminal and type `brew tap homebrew/cask`
2. In terminal type `brew cask instal iterm2`
3. Open iterm2 and go to `Preferences > Profiles > Terminal > Report Terminal Type`, and select `xterm-256color`.
4. Download [color scheme](https://github.com/mbadolato/iTerm2-Color-Schemes), and set up theme from `Preferences > Profiles > Colors > Color Presets`. Import `Tomorrow Night Eighties` from import button.

### Install Powerlines
1. Open iterm and type `brew tap homebrew/cask-fonts`
2. Download font from [nerd-fonts](https://github.com/ryanoasis/nerd-fonts/releases/download/v2.1.0/SourceCodePro.zip)
3. Set up iterm font: `Preferences > Profiles > Text > Change Font` and select `Sauce Code Pro Nerd Font Complete`.

### Install zsh
1. `brew install zsh`
2. Set up default shell.
```
sudo sh -c "echo $(which zsh) >> /etc/shells" 
chsh -s $(which zsh)
```
3. Install oh-my-zsh.
```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```
4. Modify `~/.zshrc`.
```
open ~/.zshrc
```
5. Change font and other settings.
```
ZSH_THEME="agnoster"
POWERLEVEL9K_LEFT_PROMPT_ELEMENTS=(context dir dir_writable vcs vi_mode)
POWERLEVEL9K_RIGHT_PROMPT_ELEMENTS=(status background_jobs history ram load time)
DEFAULT_USER="xxx"
POWERLEVEL9K_MODE='nerdfont-complete'
```
6. Execute command.
```
exec $SHELL
```

