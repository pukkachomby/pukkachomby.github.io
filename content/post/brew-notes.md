---
title: "Homebrew Commands and Optimization"
date: 2025-11-28
tags:
  - "Homebrew"
  - "Apple Ecosystem"
  - "Development"
categories:
  - "Tech"
---

This guide details various Homebrew upgrade commands and flags. It also provides a script to make Homebrew faster on MacOS by optimizing its configuration.

<!--more-->

## Brew Commands and Flags
Require all casks to have a checksum. Enabled by default if $HOMEBREW_CASK_OPTS_REQUIRE_SHA is set.
```sh
brew upgrade --require-sha
```
Package has auto-updates which makes brew ignore upgrading it
```sh
brew upgrade --greedy PACKAGE_NAME
```
Quick update, upgrade, partial cleanup. If HOMEBREW_NO_INSTALL_CLEANUP is set, then no cleanup. Best for daily/weekly upgrades.
```sh
brew upgrade
```
Aka: `brew up -f && brew upgrade && brew cleanup -s`. Complete update, upgrade, clean. Best for monthly upgrades.
```sh
brew update --force && brew upgrade && brew cleanup --scrub
```
Not really for upgrading. More for scripts where you want to do a quick update check before installing a package
```sh
brew update-if-needed
```

## Make Homebrew Faster on MacOS
* Run the below then reload ZSH with `exec zsh`
```sh
#!/usr/bin/env bash

set -euo pipefail

# Disable auto update and analytics
echo 'export HOMEBREW_NO_AUTO_UPDATE=1' >> ~/.zshrc
echo 'export HOMEBREW_NO_ANALYTICS=1' >> ~/.zshrc

# Force bottles over source builds
echo 'export HOMEBREW_FORCE_BOTTLE=1' >> ~/.zshrc

# Shallow clone taps
brew tap homebrew/core --force-auto-update --shallow
brew tap homebrew/cask --force-auto-update --shallow

# Use faster git remotes (GitHub mirror via fast clone)
git -C "$(brew --repo)" remote set-url origin https://github.com/Homebrew/brew
git -C "$(brew --repo homebrew/core)" remote set-url origin https://github.com/Homebrew/homebrew-core
git -C "$(brew --repo homebrew/cask)" remote set-url origin https://github.com/Homebrew/homebrew-cask

# Cleanup old versions
brew cleanup -s
````
