# Mac Terminal setup

## Install iTerm2

Install Homebrew and add to PATH:
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> /Users/[username]/.zprofile
eval "$(/opt/homebrew/bin/brew shellenv)"
```

Install iTerm2, Git and Oh My Zsh:
```bash
brew install --cask iterm2
brew install git
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

## Theme

Install PowerLevel10K Theme for Oh My Zsh:
```bash
git clone https://github.com/romkatv/powerlevel10k.git $ZSH_CUSTOM/themes/powerlevel10k
```

Open the "~/.zshrc" and change the value of "ZSH_THEME" as shown below:
```bash
ZSH_THEME="powerlevel10k/powerlevel10k"
```

To reflect this change in your terminal, restart it or run this command:
```bash
source ~/.zshrc
```

This will open up the configuration dialog for PowerLevel10K.
Press 'y' to install the Meslo Nerd Font, and then quit iTerm2.

When you re-open iTerm2, it should automatically continue with the P10K configuration. If it doesn't run:
```bash
p10k configure
```

## Font size
Open iTerm2 Preference > Profiles > Text

## Colours
Download colour profile:
```bash
curl https://raw.githubusercontent.com/josean-dev/dev-environment-files/main/coolnight.itermcolors --output ~/Downloads/coolnight.itermcolors
```

Open iTerm2 Preferences > Profiles > Colors
Import the downloaded colour profile from Downloads.
Select the colour profile.

## ZSH Plugins
```bash
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
plugins=(git zsh-autosuggestions zsh-syntax-highlighting web-search)
```

Load these new plugins by running
```bash
source ~/.zshrc
```
