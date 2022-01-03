# Mac Bootstrap for Demand Chain

This script will provision a new machine running a fresh install of [macOS Big Sur (11.15)][bigsur].

This is a simplified version of my personal [bootstrap script][bootstrap-josh].

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

To install with a one-liner, run this:

```sh
curl --remote-name https://bitbucket.org/jsaterdalen/mac-bootstrap/raw/e3080bdc9c088bb71e3b2c513c8007184f81bc33/bootstrap && sh bootstrap 2>&1 | tee ~/bootstrap.log
```

## What does it do?

When you invoke `bootstrap`, here's what it does:

- Step 1: Run an adaptation of thoughtbot's [Laptop script][laptop].
- set mac defaults
- install brew stuff

## Post-install Tasks

After running `bootstrap` there are still a few things that need to be done.

- Restart your machine in order for some changes to take effect
- open Terminal and run `brew bundle install`
- While that's running:
    - create admin account
    - enable filevault disk encryption
    - install kaspersky anti-virus

[asdf]: https://asdf-vm.com/
[bootstrap]: https://bitbucket.org/jsaterdalen/mac-bootstrap/src/master/
[bootstrap-josh]: https://github.com/JSaterdalen/mac-bootstrap/
[brew-bundle]: https://github.com/Homebrew/homebrew-bundle#usage
[bigsur]: https://www.apple.com/macos/big-sur/
[jsaterdalen]: https://github.com/JSaterdalen
