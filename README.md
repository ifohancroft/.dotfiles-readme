# dotfiles

## Setup
```sh
mkdir $XDG_DATA_HOME/dotfiles
git init --bare $XDG_DATA_HOME/dotfiles
echo "alias dotfiles='git --git-dir=$XDG_DATA_HOME/dotfiles/ --work-tree=$HOME'" >> $HOME/.bashrc
alias dotfiles='git --git-dir=$XDG_DATA_HOME/dotfiles/ --work-tree=$HOME'
dotfiles config --local status.showUntrackedFiles no
dotfiles remote add origin git@github.com:ifohancroft/dotfiles.git
dotfiles add .bashrc
dotfiles status
dotfiles commit -m "Added .bashrc"
dotfiles push -u origin master
```

## Replication
```sh
git clone --bare git@github.com:ifohancroft/dotfiles.git $XDG_DATA_HOME/dotfiles
alias dotfiles='git --git-dir=$XDG_DATA_HOME/dotfiles/ --work-tree=$HOME'
dotfiles checkout -f
dotfiles config --local status.showUntrackedFiles no
```

## Usage
```sh
dotfiles status
dotfiles add .Xresources
dotfiles commit -m "Added .Xresources"
dotfiles push
```
