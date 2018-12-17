# Linux Mint - Software Checklist

This repository contains a checklist of software that I normally install on a fresh Linux Mint system. Please, keep in mind that the list is tailored for software development, and as such does not necessarily represent a regular LM user.

## Repos / PPAs

In order to be able to install and/or get the latest version of the following software, add the repos mentioned below:

- TLP
```
sudo add-apt-repository ppa:linrunner/tlp
```
- Yubikey Tools
```
sudo add-apt-repository ppa:yubico/stable
```
- kubectl
```
sudo apt-get update && sudo apt-get install -y apt-transport-https
curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add -
echo "deb https://apt.kubernetes.io/ kubernetes-xenial main" | sudo tee -a /etc/apt/sources.list.d/kubernetes.list
```
- Vivaldi
```
echo "deb http://repo.vivaldi.com/stable/deb/ stable main" | sudo tee /etc/apt/sources.list.d/vivaldi.list > /dev/null
wget -q -O - http://repo.vivaldi.com/stable/linux_signing_key.pub | sudo apt-key add -
```
- Chrome
```
echo "deb [arch=amd64] http://dl.google.com/linux/chrome/deb/ stable main" | sudo tee /etc/apt/sources.list.d/google-chrome.list > /dev/null
wget -q -O - https://dl-ssl.google.com/linux/linux_signing_key.pub | sudo apt-key add -
```
Depending on your Linux distro, you might also want to add more repos to be able to use the latest versions of the following: Docker, NodeJS, Postgres etc.

## Software Checklist

### Via Aptitude

- `apt install build-essential` - includes all packages needed to compile a Debian package (e.g. GCC)
- `apt install python3-pip python3-setuptools python3-dev` - **PIP** for Python 3, as well as other major deps required for installing some Python packages
- `apt install git` - **Git** - possibly the best version control system out there
- `apt install guake` - **Guake** - a dropdown terminal that can be shown / hidden with a shortcut
- `apt install tmux` - **Tmux**, a terminal multiplexer, e.g. allows splitting your terminal into panes
- `apt install vim-gnome` - **Vim**, a version of Vim that allows yanking/pasting to/from the clipboard (`"+y`/`"+p`)
- `apt install direnv` - **Direnv**, unclutter your `.bashrc` by moving environment vars to individual `.envrc` files
- `apt install docker.io` - **Docker**, software for running containers ~*i.e. the lightweight VMs*~
- `apt install docker-compose` - **docker-compose**, bring up and tear down multi-container environments
- `apt install google-chrome-stable` - **Google Chrome**, a free web browser from Google, IMO a bit more stable than Chromium
- `apt install vivaldi-stable` - **Vivaldi**, a browser that supports grouping multiple web pages in a single tab
- `apt install tlp tlp-rdw` - **TLP**, a Linux power management tool, must-have on laptops
- `apt install nodejs npm` - **Node.js**, a javascript runtime & **npm** for package management
- `apt install snapd` - **Snappy**, a cross-distro package manager developed by Canonical
- `apt install yubioath-desktop yubikey-manager-qt yubikey-personalization-gui` - **Yubikey Authenticator**, **Yubikey Manager**, **Yubikey Personalization Tool**, all needed, one way or another, in case if you are using Yubikeys
- `apt install scdaemon` - **Smartcard** daemon for GnuPG (required if you are using Yubikey to store your GPG keys)
- `apt install wireshark-qt` - **Wireshark**, a GUI for wireshark packet analyzer
- `apt install virtualbox virtualbox-qt` - **VirtualBox**, software for running VMs
- `apt install kubectl` - **kubectl**, a CLI for working with k8s clusters
- `apt install postgresql-client` - CLI client for **PostgreSQL**
- `apt install mongodb-clients` - CLI client for **MongoDB**
- `apt install htop glances powertop sysstat` - monitorying tools
- `apt install traceroute tcpflow nmap socat` - networking tools
- `apt install stress siege apache2-utils` - various load testing tools
- `apt install jq finger` - misc handy utilities

### Via Flatpak / Snap / NPM / Pip

- `flatpak install flathub com.skype.Client` or `snap install skype` - **Skype**, a text/voice/video chat app ~pwned~ owned by Microsoft
- `flatpak install flathub com.slack.Slack` or `snap install slack` - **Slack**, a team colaboration tool, i.e. a text chat on steroids
- `flatpak install flathub com.spotify.Client` or `snap install spotify` - **Spotify**, a music streaming app by Spotify
- `snap install intellij-idea-ultimate --classic`- **Intellij IDEA**, possibly the best IDE for developing any app that is JVM-based, there is also a free community edition with less features
- `snap install bitwarden` - **BitWarden**, an open source password manager done right (at least from the user perspective)
- `npm install -g tldr` or `snap install tldr` - **TLDR**, a great collection of simplified man pages, first stop for help on any terminal command
- `pip3 install --user s-tui` - **S-TUI**, a cli tool that graps cpu freq, utilization and temperature over time
- `pip3 install --upgrade --user awscli` - **AWS CLI**, a cli tool to work with Amazon Web Services

### Via SdkMan

- `curl -s "https://get.sdkman.io" | bash` - [SdkMan](https://sdkman.io/) itself
- `sdk install java`
- `sdk install gradle`
- `sdk install maven`
- `sdk install visualvm`
- `sdk install springboot`

### Via other means (e.g. manually)

- [Bash Autocomplete For Aliases](https://github.com/cykerway/complete-alias)
- [Tmux Plugin Manager](https://github.com/tmux-plugins/tpm)
- [Minikube](https://github.com/kubernetes/minikube)
- Java Mission Control
- Eclipse Memory Analyzer
- GCViewer

