# Setup Cheat Sheet
#### *Cheat sheet for installing all the stuff I need for a new Dev system*
Note: this is primarily for a Linux system (Arch or Ubuntu). I might update this to include MacOS at a later date :)

## Things to Install
- Chrome/Firefox
- Visual Studio Code
- Sublime Text 3
- Slack
- urxvt
- git
- Zsh
- zeal (docs)
- Heroku CLI
- MongoDB Compass
- Postman
- KeePassXC
- curl
- Postman
- Boostnote
- Dropbox (for Boostnote)

## Git
```
# Ubuntu
 sudo apt-get install git
 sudo apt-get install curl

# Arch
 pacman -S git
```
## Zsh
Install Zsh from terminal
```
sudo apt-get install zsh
```
Verify it installed
```
zsh --version
```

Set Zsh as default shell
```
chsh -s /bin/zsh
```
Logout and log back in. If you are greeted with a Zsh shell configuration prompt, select "2" to accept default settings.

## Oh My Zsh
```
sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

## Sublime Text
Install the GPG key:
```
wget -qO - https://download.sublimetext.com/sublimehq-pub.gpg | sudo apt-key add -
```

Ensure apt is set up to work with https sources:
```
sudo apt-get install apt-transport-https
```

Select the channel to use:
```
Stable
echo "deb https://download.sublimetext.com/ apt/stable/" | sudo tee /etc/apt/sources.list.d/sublime-text.list
```
```
Dev
echo "deb https://download.sublimetext.com/ apt/dev/" | sudo tee /etc/apt/sources.list.d/sublime-text.list
```

Update apt sources and install Sublime Text
```
sudo apt-get update
sudo apt-get install sublime-text
```

## Rbenv | Ruby | Rails
Get some required depenancies:
```
sudo apt-get install autoconf bison build-essential libssl-dev libyaml-dev libreadline6-dev zlib1g-dev libncurses5-dev libffi-dev libgdbm3 libgdbm-dev nodejs sqlite3 libsqlite3-dev
```

Using git - download rbenv git repo to a hidden directory
```
git clone https://github.com/rbenv/rbenv.git ~/.rbenv
```

Add terminal commands for rbenv 
NOTE: these will not give you back any feedback to tell you they are complete.
```
echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
```
```
echo 'eval "$(rbenv init -)"' >> ~/.bashrc
```

Run command for rbenv
```
echo 'source ~/.bashrc' >> ~/.bash_profile
```
Check if rbenv works, type 
```
rbenv
```
You should get back a "rbenv is a function" in the terminal

Install ruby-build to help rbenv using git:
```
git clone https://github.com/rbenv/ruby-build.git ~/.rbenv/plugins/ruby-build
```
Install ruby using rbenv
```
rbenv install 2.4.1
```

Setup the version of Ruby you wish to use
```
rbenv local 2.4.1
```

Once Ruby has been set to local you should be able to verify which version you have
```
ruby -v
```
Install Ruby On Rails
```
gem install rails --version 5.1.1 --no-ri --no-rdoc && rbenv rehash
```
Type rails -v to test your version

Note: need to put these lines at the bottom of the .zshrc
```
export PATH="$HOME/.rbenv/bin:$PATH"
eval "$(rbenv init -)"
```

## JavaScript | Node.js | Angular
#### Ubuntu
For Node.js 8:
```
curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash -
sudo apt-get install -y nodejs
```

#### Arch Linux
```
pacman -S nodejs npm
```

### Yarn
Ubuntu:
```
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list

sudo apt-get update && sudo apt-get install yarn
```

## Typescript
```
npm install -g typescript
```

## Angular CLI
```
npm install -g @angular/cli
```

## Gulp
```
// install globally
npm install gulp -g

// install to project
npm install gulp --save-dev
```

## Connecting to GitHub with SSH
Follow the guide linked below:
https://help.github.com/articles/connecting-to-github-with-ssh/

Setup local user:
```
git config --global user.email "you@example.com"
git config --global user.name "your name"
```

## Heroku CLI
For full documentation, go to:
https://devcenter.heroku.com/articles/heroku-cli

Ubuntu:
```
wget -qO- https://cli-assets.heroku.com/install-ubuntu.sh | sh
```

Arch:
```
npm install -g heroku-cli
```

After the installation has completed, login using your Heroku credentials:
```
heroku login
```

## Postgresql
*fun*

Install under Ubuntu:
```
sudo apt-get install postgresql postgresql-contrib libpq-dev
```

Start Server:
```
sudo systemctl start postgresql
```

Restart the server:
```
sudo /etc/init.d/postgresql restart 
```
#### Creating a new user:
Switch to postgress account
```
 sudo -i -u postgres 
```
The prompt should look like this:
```
postgres@server:~$ 
```
Enter the following:
```
createuser -P -s -e *username*
```
To make things easier, set your *username* to the username of your system, eg 'nick'. To make things even easier, leave the password blank, just hit enter.

## MongoDB

https://docs.mongodb.com/manual/tutorial/install-mongodb-on-ubuntu/

## Postman

https://blog.bluematador.com/posts/postman-how-to-install-on-ubuntu-1604/?utm_source=hootsuite&utm_medium=twitter&utm_campaign=

## Neofetch
```
sudo apt-get install neofetch
```
To get it to run on start up, add a call to it in the .zshrc file at the bottom.

#### display an image
Make sure imagemagick is installed, as well as w3m-img
```
sudo apt-get install w3m-img
```
add the following launch command to the neofetch call
```
--w3m /home/*username*/path/to/img
```

## Zeal Docs
```
sudo add-apt-repository ppa:zeal-developers/ppa
sudo apt-get update
sudo apt-get install zeal
```

## Powerline Fonts
https://github.com/powerline/fonts

## Papirus  Icon theme
https://github.com/PapirusDevelopmentTeam/papirus-icon-theme


