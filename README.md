# My iTerm2 and Zsh Setup on MacOS Mojave

![Beautiful Command Prompt Screenshot](https://github.com/baneDD/iterm-zsh-config/raw/master/images/good-prompt.png)

If you're a software developer like me, you find yourself spending a lot of time in the terminal using command-line tools. I do most of my development on a Mac and what follows is a collection of tools and configurations I've discovered over time that make my terminal life a little more pleasant in MacOS Mojave. Let's face it, the default terminal Apple ships with MacOS leaves a lot to be desired in terms of configuration flexibility, functionality and visual appeal.

Install [Homebrew](https://brew.sh/) on your Mac if you don't already have it installed:

```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

Once Homebrew is installed, we will need to install [iTerm2](https://www.iterm2.com/):

```
brew cask install iterm2
```

### ZSH INSTALLATION AND CONFIGURATION

Let's also install [zsh](http://www.zsh.org/) shell:

```
brew install zsh
```

Once this is done, we have the zsh shell installed and can use it instead of the default bash shell. The configuration file for zsh is located in your home folder as `.zshrc`. To change the default shell to zsh, we will need to run the change shell command in the terminal:

```
chsh -s /bin/zsh
```

There are a number of interesting plugins for zsh created by the community. Some of the more popular ones are [`zsh-syntax-highlighting`](https://github.com/zsh-users/zsh-syntax-highlighting) which adds a fish-shell-like sytax highlighting, [zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions) which add fish-like autosuggestions and [zsh-completions](https://github.com/zsh-users/zsh-completions) which offer additional completions in zsh. There are many more add-ons in [zsh-users](https://github.com/zsh-users) community repository so head on over there and check them out.

Let's go ahead and add a few of these:

```
brew install zsh-syntax-highlighting zsh-autosuggestions zsh-completions zsh-history-substring-search
```

### NERD FONTS INSTALLATION AND CONFIGURATION

```
brew tap homebrew/cask-fonts
brew install --cask font-hack-nerd-font
```

### GIT CONFIGURATION

This script gives you a pair of powerful GIT tools to use in your arsenal: 

- It adds an alias (gitprune) that deletes any local GIT branches that have been deleted on origin. This runs ```git fetch --all -p``` to update from origin before deleting any dangling branches.
- It enables GIT autocompletions. To install autocompletions use Homebrew: ```brew install bash-completion```

### POWERLEVEL9K INSTALLATION AND CONFIGURATION

Copy the `.zshrc` file from this repository to your home repository `~`

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

![Security & Privacy Panel Screenshot](https://github.com/baneDD/iterm-zsh-config/raw/master/images/security-and-privacy-tab.png)

### KNOWN ISSUES

Pointer colors are off in iTerm2:

![Beautiful Command Prompt Screenshot](https://github.com/baneDD/iterm-zsh-config/raw/master/images/bad-prompt.png "Bad Pointer Colors")

It should look like this instead:

![Beautiful Command Prompt Screenshot](https://github.com/baneDD/iterm-zsh-config/raw/master/images/good-prompt.png "Good Pointer Colors")

There are a couple of settings you need to change in iTerm2 to fix the colour issues. Head on over to iTerm2 -> Preferences -> Profiles and select the profile you want to update. In the colors tab, you will need to set "Minimum Contrast" slider to zero:

![Minimum Contrast Screenshot](https://github.com/baneDD/iterm-zsh-config/raw/master/images/minimum-contrast.png)

And under the Window tab, ensure your transparency is set to "Opaque":

![Transparency Screenshot](https://github.com/baneDD/iterm-zsh-config/raw/master/images/transparency.png)

That should resolve your issues and your terminal should now look correct.
