# .dotfiles

A comprehanseve way to store configuration files in a remoute repository

## Restoring configuration

To apply configs within current system we should clone this repo to our home `~` directory:

```
git clone https://github.com/HardRockLogic/dotfiles.git
```

Then `cd` inside `dotfiles` dir and recreate symlinks for each config file:

```
ln -s .zshrc ~/.zshrc
ln -s .tmux.conf ~/.tmux.conf
ln -s alacritty.yml ~/.config/alacritty/alacritty.yml
```

## Dealing with dependencies

Each config file can have its own dependencies, like plugin-managers, themes etc., this guide should be treated as a reference, so better
check oficial repos.\
**NOTE! that this dependencies should be installed before applying configs or errors to be occured.**

### Tmux

To work properly and load plugins used in `.tmux.conf` **tmux-plugin-manager** (tpm) should be installed locally in home directory.

```
git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm
```

For more info check [tpm github page](https://github.com/tmux-plugins/tpm).

### Alacritty

`alacritty.yml` config imports specific colorscheme form **alacritty-theme** repo, so be shure to repeat this steps:

```
# We use Alacritty's default Linux config directory as our storage location here.
mkdir -p ~/.config/alacritty/themes
git clone https://github.com/alacritty/alacritty-theme ~/.config/alacritty/themes
```

Instead of importing `yaml` from coroshceme collection, it is also possible to just paste colorscheme-setings into root of
your `alacritty.yml` config, so you dont need to clone **alacritty-theme** repo.

See [alacritty-theme](https://github.com/alacritty/alacritty-theme) for more.

### ZSH (OhMyZsh)

**OhMyZsh** is used to manage zsh config including plugins, aliases etc. Install **OhMyZsh** framework:

```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

Then install plugins:

- autosuggesions plugin\
  `git clone https://github.com/zsh-users/zsh-autosuggestions.git $ZSH_CUSTOM/plugins/zsh-autosuggestions`
- zsh-syntax-highlighting plugin\
  `git clone https://github.com/zsh-users/zsh-syntax-highlighting.git $ZSH_CUSTOM/plugins/zsh-syntax-highlighting`
