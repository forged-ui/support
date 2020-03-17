# Support

If you need help, please just create a new github issue with your request.

## Introduction

As the concept of Forged UI is that you can change it and is powered by GIT, we don't publically provide single compiled versions to download online or via any fancy updater system.

This does mean you'll clone the repository, and use a pre-build macOS version or compile it on your own OS.

## Downloading

Once you've made your purchase via [gitstore.app](https://enjoy.gitstore.app/repositories/OwenMelbz/forged-ui) you'll be provided with a private SSH key.

This SSH key is unique to your team and allows you read-only accesss to the repo which is `git@github.com:OwenMelbz/forged-ui.git`

The following instructions are an example for a macOS environment, adjust to your toolset! As long as you git pull and git clone using this SSH key, how you get there is a-okay!

- Download the **Private SSH** Key from [gitstore](https://enjoy.gitstore.app/subscriptions)
- Save it into your SSH folder e.g. `~/.ssh/forged-ui.key`
- Make sure the permissions on it are correct e.g. `chmod 600 ~/.ssh/forged-ui.key`
- Load it into your SSH agent/Peagant e.g. `ssh-add ~/.ssh/forged-ui.key`
- Confirm it has loaded with `ssh-add -L`
- Clone the repository via `git clone git@github.com:OwenMelbz/forged-ui.git`

## Compiling


