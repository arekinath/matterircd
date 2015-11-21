# matterircd

Minimal IRC server which integrates with [mattermost](https://www.mattermost.org) 

Work in progress, does the basics for now.   
Should be rather stable now. Tested on Windows / Linux   

Most of the work happens in [mm-go-irckit](https://github.com/42wim/mm-go-irckit) (based on github.com/shazow/go-irckit)

# Features

* support direct messages / private channels
* auto-join/leave to same channels as on mattermost
* reconnects with backoff on mattermost restarts
* support multiple users
* support channel backlog (messages when you're disconnected from IRC/mattermost)
* search messages (/msg mattermost search query)
* restrict to specified mattermost instances
* set default team/server
* WHOIS, WHO, JOIN, LEAVE, NICK, LIST, ISON, PRIVMSG support

# Binaries
You can find the binaries [here](https://github.com/42wim/matterircd/releases/tag/v0.2)

# Usage

```
Usage of matterircd:
  -debug=false: enable debug logging
  -interface="127.0.0.1": interface to bind to
  -mmserver="": specify default mattermost server/instance
  -mmteam="": specify default mattermost team
  -port=6667: Port to bind to
  -restrict="": only allow connection to specified mattermost server/instances. Space delimited
```

Matterircd will listen by default on localhost port 6667.  
Connect with your favorite irc-client to localhost:6667

## Mattermost user commands
Login

```
/msg mattermost login <server> <team> <login> <password>
```

Search
```
/msg mattermost search query
```

## Examples

1. Login to your favorite mattermost service by sending a message to the mattermost user
![login](http://snag.gy/aAop5.jpg)

2. You'll be auto-joined to all the channels you're a member of
![channel](http://snag.gy/IzlXR.jpg)

3. Chat away
![chat](http://snag.gy/JyFd7.jpg)
![mmchat](http://snag.gy/3qMd1.jpg)

Also works with windows ;-)
![windows](http://snag.gy/cGSCA.jpg)

If you use chrome, you can easily test with [circ](https://chrome.google.com/webstore/detail/circ/bebigdkelppomhhjaaianniiifjbgocn?hl=en-US)
