# .dotfiles

## Setup
```sh
mkdir $HOME/.dotfiles
git init --bare $HOME/.dotfiles
echo "alias dotfiles='git --git-dir=$HOME/.dotfiles/ --work-tree=$HOME'" >> $HOME/.bashrc
alias dotfiles='git --git-dir=$HOME/.dotfiles/ --work-tree=$HOME'
dotfiles config --local status.showUntrackedFiles no
dotfiles remote add origin https://github.com/ifohancroft/.dotfiles.git
dotfiles remote set-url origin https://github.com/ifohancroft/.dotfiles.git
dotfiles add .bashrc
dotfiles status
dotfiles commit -m "Added .bashrc"
git push --set-upstream origin master
```

## Replication
```sh
git clone --bare https://github.com/ifohancroft/.dotfiles.git $HOME/.dotfiles
alias dotfiles='git --git-dir=$HOME/.dotfiles/ --work-tree=$HOME'
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
