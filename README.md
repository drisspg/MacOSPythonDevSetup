# MacOSPythonDevSetup
This is my current playlist and order of operations for setting up new Mac OS computer dev environment.

### Steps
1. Install xcode cli tools by running: `xcode-select —-install`.
2. Install Homebrew: `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"` If command doesn't work, check for updates [here](https://brew.sh).
3. Install iterm2, in terminal run `brew install iterm2` Once installed open up iterm and set default shell to zsh by running: `chsh -s /bin/zsh`
4. Insatll ohmyzsh by running `sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"` if command fails check out their github [here](https://github.com/ohmyzsh/ohmyzsh).
5. Before we setup OhMyZsh lets get a text editor or use (vim) `brew install --cask visual-studio-code`.

### Pretty up the terminal
7. Edit the .zshrc file by running `code .zshrc` from home dir. Handy plugins that I used are listed in the .zshrc file here. To use these plugins, two require further install. **UNCOMMENT LINE 12** `export ZSH="/Users/driss.guessous/.oh-my-zsh"` and export the correct path to OMZ.
8. [zsh autosuggestions](https://github.com/zsh-users/zsh-autosuggestions/blob/master/INSTALL.md). Run `git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions` to install. 
9. Install the powerlevel10k fonts by running: `git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k`. This is by far the best. If fails check website [here](https://github.com/romkatv/powerlevel10k#oh-my-zsh)
10. Now copy everything up to line 97 `source $ZSH/oh-my-zsh.sh` into your .zshrc. Start a new terminal window to check that it works. It will prompt you to go through the powerlevel10k config. My Choices can be found in this file:  ~/.p10k.zsh located in this folder.
11. Change the iterm Colors in iterm's preferences profiles. Upload the color profile .json file in this folder by clicking on the Other Actions.

### Python Specifc Steps:
1. Install pyenv (Used to manage multiple python versions) via `brew install pyenv`.Then Run the follwoing commands `echo 'eval "$(pyenv init --path)"' >> ~/.zprofile`|`echo 'eval "$(pyenv init -)"' >> ~/.zshrc `. Then install python build dependencies: `brew install openssl readline sqlite3 xz zlib`. 
2. Lets install python 3.7.9 (used for upchuck and quinn): `pyenv install 3.7.9`. I set this as global.. this may not be good but is needed for the next step: ` pyenv global 3.7.9`.
3. Install [pyenv virtualenv wrapper](https://github.com/pyenv/pyenv-virtualenvwrapper). `brew install pyenv-virtualenvwrapper` From root directory create venv dir: `mkdir .virtualenvs` this is where all virtualenvs will be stored. Install virutalenvwrapper: ` pip install virtualenvwrapper`.
4. Once this is done copy the rest of the .zshrc file into yours from line 97 onwards.

### Helpful Apps
1. Install Docker instructions can be found [here](https://docs.docker.com/desktop/mac/install/).
2. Install Postman `brew install --cask postman`
3. Install GitKraken `brew install --cask gitkraken`
4. Install Pycharm `brew install --cask pycharm`
