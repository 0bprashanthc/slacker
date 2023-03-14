# Slack status updater

A simple shell script to update your status in slack from the command line, based on presets you provide in a configuration file.

## Installation

Copy `slacker.sh` to somewhere in your path.

## Setup

Before you can use this, you need to add the status updater as a new slack app. To do this:

* Go to <https://api.slack.com/apps/new> to create a new app
* Choose a name for the new app: Slack status updater
* Select your workspace from the "Development Slack Workspace" dropdown
* This will bring you to the app configuration section, choose "OAuth and Permissions"  from the sidebar on the left under the "Features" section.
* Scroll down until you see "User token scopes" and click "Add an OAuth scope"
* Type in `users.profile:write` and select it from the menu.
* Scroll back to the top and click the "Install App to Workspace" button.
* You will be brought to a screen asking you to allow the app access. Click "Allow"
* You will be taken back to a screen containing an access token starting with `xoxp-`. Click the "Copy" button to copy this to the clipboard.

Once you have the token, run `slacker.sh setup` and follow the prompts.
This will create a configuration file for you.

If you wish, edit the config file to add additional presets.

## Usage

* `slacker.sh PRESET` - updates your slack status to the preset
* `slacker.sh none` - resets your slack status to be blank
* `slacker.sh PRESET ADDITIONAL TEXT` - any additional text you type will
  be added to the end of your slack status.

Example:

```
$ slacker.sh test
Updating status to: :check: Testing status updater
$ slacker.sh none
Updating status to:
$ slacker.sh vacation
Updating status to: :hotel: On vacation
$ slacker.sh vacation until June 15
Updating status to: :hotel: On vacation until June 15
```
