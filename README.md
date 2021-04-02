# Streamdeck Twitch Streamer Plugin

## Overview

This streamdeck plugin provides a single button, the Streamer Status button. It is categorized under the Twitch Streamer category

This button will automatically download the streamer's icon, and light up when they go live.

Pressing the button will open their twitch stream in your browser

## Setup

### Global Settings

There are 2 global settings:

- AppId
- AppSecret

These are used to authenticate to the twitch API.

You can obtain them by following twitch.tv's [developer guide](https://dev.twitch.tv/docs/authentication/#registration)

Set the oauth redirect to `https://localhost` and then copy the application id and secret

### Button Settings

There is 1 button setting:

- Stream ID

This should be the the id of the twitch streamer the button should represent

## Other Information

### API Usage

Twitch will rate limit at 800 API calls per minute. This application will make 1 API call per minute per active button.

For a Streamdeck XL, this is at most 32 calls per minute. So it should be well below the threshold.

### Icons

Icons are loaded once on plugin startup. Loading will retry 3x in the first 3 minutes. If unsuccessful the default icon will be used until the plugin is restarted (close and restart the streamdeck application)