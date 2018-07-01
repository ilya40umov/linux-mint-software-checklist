# Linux Mint - Software Checklist

This repository contains a checklist of software that I normally install on a fresh Linux Mint system. Please, keep in mind that the list is tailored for JVM-based software development and as such does not necessarily represents a regular LM user.

## TODOs

 - Add VisualVM, Java Mission Control, Eclipse Memory Analyzer, GCViewer

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

- `apt install dropbox` - **Dropbox** - a client for Dropbox, cloud synchronization engine
- `apt install guake` - **Guake** - a dropdown terminal that can be shown / hidden with a shortcut
- `apt install tmux` - **Tmux**, a terminal multiplexer, e.g. allows splitting your terminal into panes
- `apt install vim-gnome` - **Vim**, a version of Vim that allows yanking/pasting to/from the clipboard (`"+y`/`"+p`)
- `apt install direnv` - **Direnv**, unclutter your `.bashrc` by moving environment vars to individual `.envrc` files
- `apt install docker.io` - **Docker**, software for running containers ~*i.e. the lightweight VMs*~
- `apt install docker-compose` - **docker-compose**, bring up and tear down multi-container environments
- `apt install vivaldi-stable` - **Vivaldi**, a browser that supports grouping multiple web pages in a single tab
- `apt install google-chrome-stable` - **Google Chrome**, a free web browser from Google, IMO a bit more stable than Chromium
- `apt install tlp tlp-rdw` - **TLP**, a Linux power management tool, must-have on laptops
- `apt install nodejs` - **Node.js**, a javascript runtime, brings **npm** on board
- `apt install snapd` - **Snappy**, a cross-distro package manager developed by Canonical
- `apt install yubioath-desktop yubikey-neo-manager yubikey-personalization-gui` - **Yubikey Authenticator**, **Yubikey Neo Manager**, **Yubikey Personalization Tool**, all needed, one way or another, in case if you are using Yubikeys
- `apt install virtualbox virtualbox-qt` - **VirtualBox**, software for running VMs
- `apt install vagrant` - **Vagrant**, a tool for managing development environments, requires VirtualBox or an alternative
- `apt install wireshark-qt` - **Wireshark**, a GUI for wireshark packet analyzer

- `snap install skype` - **Skype**, a text/voice/video chat app ~pwned~ owned by Microsoft
- `snap install slack` - **Slack**, a team colaboration tool, i.e. a text chat on steroids
- `snap install spotify` - **Spotify**, a music streaming app by Spotify
- `snap install intellij-idea-ultimate`- **Intellij IDEA**, possibly the best IDE for developing any app that is JVM-based, there is also a free community edition with less features
- `snap install bitwarden` - **BitWarden**, an open source password manager done right (at least from the user perspective)
- `snap install tldr` or `npm install -g tldr` - **TLDR**, a great collection of simplified man pages, first stop for help on any terminal command
- `snap install kubectl` - **kubectl**, a cli for working with k8s clusters

- `pip install --user s-tui` - **S-TUI**, a cli tool that graps cpu freq, utilization and temperature over time
- `pip install --upgrade --user awscli` - **AWS CLI**, a cli tool to work with Amazon Web Services

To use some of the commands from this reference, you may also need to `apt install` the following packages:
- `finger`
- `htop`
- `powertop`
- `glances`
- `jq`
- `apache2-utils`

If you are developing on Java/Kotlin/Scala and hence require different versions of JDK, as well as Gradle, Maven or SBT, you may want to check out [SdkMan](https://sdkman.io/), which can help you out with this task. Alternativelly, you can try installing multiple JDKs via `apt` and switching between them via `update-java-alternatives` / `update-alternatives`, however I personally didn't get far with this approach because a) to install different versions of java I would end up using PPAs that I was not sure I could trust and b) installing a new JDK would sometimes break a previously installed one.
