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
- **Restarting terminal** - Some terminal clients require you to open a new tab/window/instance to load in the SSH key
- Change into the directory you want the code to be stored in e.g. `cd ~/Projects`
- Clone the repository via `git clone git@github.com:OwenMelbz/forged-ui.git`

> *Help!* If you get a message like "Make sure you have correct access rights" this means the SSH key is not loading. You should confirm it has loaded with `ssh-add -L` or if not try cloning using the following command (replace paths where needed) `bash -c 'ssh-add ~/.ssh/forged-ui.key; git clone git@github.com:OwenMelbz/forged-ui.git'`

## Compiling

Forged UI is built using [electron-react-boilerplate](https://github.com/electron-react-boilerplate/electron-react-boilerplate) which which makes it straight forward to get going.

> ERB (Electron React Boilerplate) Uses `yarn` as its package manager of choice, although `npm` should work just as well! For these examples we'll use `yarn` as it follows the ERB documentation. If you need to install `yarn` first you can find out how on their [website](https://classic.yarnpkg.com/en/docs/install/) for homebrew users you can use `brew install yarn`

Firstly install the project via `yarn` then package it.

- `yarn install` - Will install all the dependencies
- `yarn package` - Will compile for your current platform

You can read the `package.json` for various other commands which allow compiling for other environments e.g.

- `yarn package-mac`
- `yarn package-win`
- `yarn package-linux`
- `yarn package-all`

You will end up with a `/releases` directory which will contain your built application!

For macOS we recommend moving this to the `~/Applications` directory to prevent any strange side-effects.

## Deployment Hooks

If you would like to use the deployment hooks feature, we'll need to establish a connection with [Pusher](https://dashboard.pusher.com/accounts/sign_up). This is free and only takes a couple of minutes! 

> If you do not want to use deployment notifications then this whole step is optional and can be ignored within the UI.

We connect to Pusher if you want and can listen for Forges deployment hooks. You can download the script needed to pass on these deployment notifications to Pusher on our [forge-ui/webhook](https://github.com/forged-ui/webhook) repo.

Effecitvely it's a PHP script powered by composer packages which takes the JSON payload from Forge, and passes it on to Pusher, which the Forged UI listens for - Full instructions are provided within the [forge-ui/webhook](https://github.com/forged-ui/webhook) repo.

## Customising

To customise the application, you can do so simply by modifying the source-code!

Everything you need to edit should be within the `/app` directory - you can start watching the files and live-reloading by using `yarn dev` 

Once you're happy, you can `yarn package` again to distribute to your team.

Please be aware the more you modify the code - the tricker merging upstream changes will be! So keep an eye on things.

## Known Issues

- **Windows 10 Notifications** - These do not currently work due to a bug in Electron -> https://www.electronjs.org/docs/tutorial/notifications#windows will be continuing to try and resolve this.
- **SSL Generation** - Uses a different format to forge also creates an exception when cancelled.

## Anything Else?

If you think we've missed something, then contact us on `hello@forged-ui.com` or open an issue on GitHub.

