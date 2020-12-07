# Atom-Config
Download [Atom](https://github.com/atom/atom/releases/tag/v1.50.0) first from its GitHub website.

## Install Packages

1. platformio-ide-terminal (Before installing please pre-install visual studio)
2. atom-beautify
3. tabs-to-spaces
4. git-plus
5. color-picker
6. autocomplete

## Config Settings

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

## Integrate Cmder

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
