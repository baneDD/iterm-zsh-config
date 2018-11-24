On MacOS Mojave, to get the wireless monitoring to work, we need to add /usr/local/bin folder and then link the airport folder to it:

```
sudo mkdir -p /usr/local/bin
sudo ln -s /System/Library/PrivateFrameworks/Apple80211.framework/Versions/Current/Resources/airport /usr/local/bin/airport
```

If you are having issues with ln command and are getting back an _'Operation not permitted'_ error, try the following:

- Open "System Preferences" on your Mac
- From there, open "Security & Privacy"
- In "Security & Privacy", click on the padlock icon in the bottom left corner (see screenshot below)
- Once you've allowed system to make changes, click on the "+" button and add iTerm (and optionally terminal)

[[https://github.com/baneDD/iterm-zsh-config/blob/master/images/security-and-privacy-tab.png]]
