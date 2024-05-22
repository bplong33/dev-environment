# Devepment Environment

This Development environment will use the following tools:

* **Terminal**: [Alacritty] or Windows Terminal
* **Shell**: ZSH / [Oh-My-Zsh]
* **Shell Theme Plugin**: [Powerlevel10K]
* **Editor**: [Neovim] (Nightly)
* **Neovim Distro**: [LazyVim]
* **Shell and Neovim Theme**: [Everforest]

Each of these will have their own Dependencies.

## Setup Rocky9 and WSL

### Import OS
Follow the steps in the [Import Rocky Linux to WSL] Guide:
* Pull desired image `.tar.xz`
* Create a directory to store WSL files (suggest creating at `%APPDATA%\RockyLinux9`)
* Run `wsl --import <machine-name> <path-to-vm-dir> <path-to\rocky-9-image.tar.xz>`

### Setup Users
* Run the following to create the user and assign them to the admins (wheel) group:
```bash
sudo adduser username
sudo passwd username
sudo usermod -aG wheel username
```

* Set the new user as the default user by adding to following to `/etc/wsl.conf`
```
[user]
default=username
```

## Install Alacritty (Optional)
* The [Alacritty] terminal can be downloaded from the [Alacritty Download] page
* Once installed, copy the [`alacritty.toml`] from this repo to `%APPDATA%/Roaming/alacritty/alacritty.toml`
  * At the top of this file, we set the default shell to WSL, so Alacritty will run WSL on startup.

## Windows Terminal (Alternate for Alacritty)

### Set Theme
* Open Windows Terminal's settings page, and click the `Open JSON file` option in the bottom left
* Copy the [`everforest.json`] file into the `schemes` section of the settings.
* In the Windows Terminal Settings UI, go to your linux box settings > Appearance and Choose `Everforest` as the theme.

## Setup Neovim
* Install build deps: `sudo dnf install g++ cmake python3.11`

### Install LazyVim

### Install RipGrep

<!-- File Links -->
[`alacritty.toml`]: ./alacritty.toml
[`everforest.json`]: ./everforest.json

<!-- Tool Links --> 
[Alacritty Download]: https://alacritty.org/
[Alacritty]: https://github.com/alacritty/alacritty
[Everforest]: https://github.com/sainnhe/everforest
[Import Rocky Linux to WSL]: https://docs.rockylinux.org/guides/interoperability/import_rocky_to_wsl/
[LazyVim]: https://www.lazyvim.org/
[Neovim]: https://github.com/neovim/neovim/blob/master/INSTALL.md#install-from-source
[Oh-My-Zsh]: https://github.com/ohmyzsh/ohmyzsh
[Powerlevel10K]: https://github.com/romkatv/powerlevel10k
