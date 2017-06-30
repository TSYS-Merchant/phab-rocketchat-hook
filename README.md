# Git HipChat Hook for Phabricator

A simple Git `post-receive` hook script for notifying a room in HipChat of Phabricator repository changes.

## Installation

1. Clone this repository somewhere on your repository host server.
2. Clone [hipchat-cli](https://github.com/hipchat/hipchat-cli) somewhere on your repository host server.
3. Go to the `hooks` directory in a repository you want to set up the hooks for and add a `post-receive` script like this one and make sure it's executable.

You can lookup the HipChat room ID from the [rooms/list](https://www.hipchat.com/docs/api/method/rooms/list) API or use the HipChat room name (remember to URL-encode it)

```sh
#!/bin/sh

HIPCHAT_SCRIPT="/path/to/hipchat_room_message"

. /path/to/hipchat-post-receive
```

And you're done!

For Phabricator, add the following configuration to the `post-receive` hook before the `hipchat-post-receive` source line.

```sh
export PHAB="phab.example.com"
export REPO="RepoName"
```

Optionally, set a callsign if it differs from your repository name.

```sh
export CALLSIGN="REPO"
```
