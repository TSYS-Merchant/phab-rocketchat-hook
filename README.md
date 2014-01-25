# Git HipChat Hook

A simple GIT `post-receive` hook script for notifying a room in HipChat. Adds additional support for Phabricator installs.

## Installation

Clone this repository somewhere in your GIT repository host server.
For example:

```sh
cd /home/git
git clone git://github.com/imobile3/git-hipchat-hook.git
```

Clone [hipchat-cli](https://github.com/hipchat/hipchat-cli) somewhere in your GIT repository host server.

```sh
git clone git://github.com/hipchat/hipchat-cli.git
```

Go to the `hooks` directory in a repository you want to setup the hooks for and add a `post-receive` script like this one and make sure it's executable.

You can lookup the HipChat room id from the [rooms/list](https://www.hipchat.com/docs/api/method/rooms/list) API or use the HipChat room name (remember to urlencode it)

```sh
#!/bin/sh

HIPCHAT_SCRIPT="/path/to/hipchat_room_message"

. /path/to/hipchat-post-receive
```

And you're done!

For Phabricator, GitWeb, CGit, Gitorious and Redmine integrations (optional) add the following configuration to the `post-receive` hook before the `hipchat-post-receive` source line.

Note that Phabricator, CGit and GitWeb, and Redmine and JIRA, are mutually exclusive.

```sh
CGIT="git.example.com/cgit"
GITWEB="gitweb.example.com"
PHAB="phab.example.com"
JIRA="jira.example.com"
REDMINE="redmine.example.com"
GITORIOUS="gitorious.example.com"
```

## Contributions

* [graffic](http://github.com/graffic) for the sed RegEx to link to Redmine issues.
* [jparise](http://github.com/jparise) for CGit and JIRA integrations.
* [perl2ruby](http://github.com/perl2ruby) for Bash extensions.
