# Git Rocket.Chat Hook for Phabricator

A simple Git `post-receive` hook script for notifying a channel in Rocket.Chat of Phabricator repository changes.

## Installation

1. Clone this repository somewhere on your repository host server.
2. Go to the `hooks` directory in a repository you want to set up the hooks for and add a `post-receive` script like this one and make sure it's executable.

```sh
#!/bin/sh

export ROCKETCHAT_WEBHOOK_URL="https://your.chat/webhook"
export ROCKETCHAT_CHANNEL="#channel"

export PHAB="phab.example.com"
export REPO="RepoName"
export CALLSIGN="REPO"

. /path/to/rocketchat-post-receive
```

and you're done!
