# Mac Bootstrap for Demand Chain

This script will provision a new machine running a fresh install of [macOS Big Sur (11.15)][bigsur].

The [`bootstrap`][bootstrap] script is very specific to the Mac platform.

## Prerequisites

1. Make sure your software is up to date:

   `sudo softwareupdate -i -a --restart`

2. Install Apple's command line tools:

   `xcode-select --install`

3. Reboot, check for additional updates, then reinstall and reboot as needed.

## Installation

To install with a one-liner, run this:

```sh
curl --remote-name https://bitbucket.org/jsaterdalen/mac-bootstrap/raw/de43f43492f967c3521de36b15d716e3d033027c/bootstrap && sh bootstrap 2>&1 | tee ~/bootstrap.log
```

WARNING: This script will ask for your password multiple times. You'll need to babysit it for a while. 😉

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
