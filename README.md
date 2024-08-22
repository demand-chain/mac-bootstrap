# Mac Bootstrap for Demand Chain

This script will provision a new machine running a fresh install of [macOS Monterey][macos]. It configures the shell, installs Rosetta, and installs useful applications.

This is a simplified version of my personal [bootstrap script][bootstrap-josh].

## What does it do?

- installs Rosetta 2
- installs [Homebrew][homebrew]
- installs/sets shell to ZSH
- sets some system defaults
    - computer name/host name
    - enables trackpad tap-to-click 
- installs command line tools, with Homebrew
    - git
    - sqlite
    - wget
    - zsh
- installs apps
    - 1Password
    - Firefox
    - Google Chrome
    - Microsoft Office
    - Microsoft Teams
    - Slack
    - Visual Studio Code
    - Zoom

## Prerequisites

1. Make sure your software is up to date:

   ```sh
   sudo softwareupdate -i -a --restart
   ```

2. Install Apple's command line tools:

   ```sh
   xcode-select --install
   ```

3. Reboot, check for additional updates, then reinstall and reboot as needed.

## Installation

To install with a one-liner, run this in the Terminal:

```sh
curl --remote-name https://raw.githubusercontent.com/demand-chain/mac-bootstrap/main/bootstrap && sh bootstrap 2>&1 | tee ~/bootstrap.log
```
## Post-install Tasks

After running `bootstrap` and restarting, there are still a few things that need to be done.

### Automatic app install

- open Terminal and run `brew bundle install`
- while this is running, do the manual steps below

### Manual steps

    - create admin account
    - enable filevault disk encryption

[bootstrap]: https://github.com/demand-chain/mac-bootstrap
[bootstrap-josh]: https://github.com/JSaterdalen/mac-bootstrap/
[brew-bundle]: https://github.com/Homebrew/homebrew-bundle#usage
[macos]: https://www.apple.com/macos/monterey/
[homebrew]: https://brew.sh/
