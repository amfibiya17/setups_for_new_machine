# Setups for new machine
---
Copy all the commands in terminal and run
```
#!/bin/bash
 
 # crontab -e
 # 0,30 8-11,13-17 * * 1-5 /usr/bin/say "Start work!"
 # 2 25,55 8-11,13-17 * * 1-5 /usr/bin/say "Stop work!"
 
 read -p "Enter your email: " email
 
 echo -e "set number\nsyntax on" > .vimrc
 
 say 'configuring O.S settings'
 defaults write -g ApplePressAndHoldEnabled -bool false
 defaults write -g CGDisableCursorLocationMagnification -bool true
 defaults write -g KeyRepeat -int 2
 defaults write -g InitialKeyRepeat -int 15
 
 say 'Installing home brew'
 install homebrew
 /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
 echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> ~/.zprofile
 eval "$(/opt/homebrew/bin/brew shellenv)"
 brew update
 export PATH="/usr/local/bin:$PATH"
 
 say 'Installing node'
 brew install node
 npm install --global eslint
 npm install --global jsonlint
 
 say 'Configuring Git'
 echo -e "[user]\nname = your_name\nemail = $email" > ~/.gitconfig
 npm install --global git-open
 
 say 'Installing VS Code'
 brew install visual-studio-code --cask
 
 say 'Installing Spotify'
 brew install spotify --cask
 
 say 'Installing draw.io'
 brew install drawio --cask
 
 say 'Installing GraphiQL'
 brew install graphiql --cask
 
 say 'Installing JQ'
 brew install jq
 
 say 'Installing powershell'
 brew install powershell --cask
 
 say 'Installing W get'
 brew install wget

 say 'Installing tree'
 brew install tree
 
 say 'Installing Go'
 brew install golang
 mkdir -p ~/go/{bin,src/github.com}
 echo -e "\n\n# Go lang" >> ~/Documents/.bash_profile
 echo 'export GOPATH=$HOME/go' >> ~/Documents/.bash_profile
 echo 'export PATH=$PATH:$GOPATH/bin' >> ~/Documents/.bash_profile
 
 say 'Installing R V M'
 gpg --keyserver hkp://pool.sks-keyservers.net --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3 7D2BAF1CF37B13E2069D6956105BD0E739499BDB
 curl -sSL https://get.rvm.io | bash
 
 say 'All tasks complete'
 ```
