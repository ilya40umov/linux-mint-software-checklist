# Linux Mint 20 - Software Checklist

This repository contains a checklist of software that I normally install on a fresh Linux Mint system. Please, keep in mind that the list is tailored for software development, and as such does not necessarily represent the set-up of a regular LM user.

## Repos / PPAs

### Mandatory

In order to be able to install and/or get the latest version of the following software, add the repos mentioned below:

- [TLP](https://linrunner.de/en/tlp/docs/tlp-linux-advanced-power-management.html#installation) (a power management tool, hence only makes sense for laptops)
```
sudo add-apt-repository ppa:linrunner/tlp
```
- [Yubikey Tools](https://www.yubico.com/products/services-software/download/)
```
sudo add-apt-repository ppa:yubico/stable
```
- [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/#install-kubectl-binary-using-native-package-management)
```
sudo apt-get update && sudo apt-get install -y apt-transport-https
curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add -
echo "deb https://apt.kubernetes.io/ kubernetes-xenial main" | sudo tee -a /etc/apt/sources.list.d/kubernetes.list
```
- [helm](https://helm.sh/docs/intro/install/)
```
curl https://baltocdn.com/helm/signing.asc | sudo apt-key add -
sudo apt-get install apt-transport-https --yes
echo "deb https://baltocdn.com/helm/stable/debian/ all main" | sudo tee /etc/apt/sources.list.d/helm-stable-debian.list
```

### Optional

- Chrome
```
echo "deb [arch=amd64] http://dl.google.com/linux/chrome/deb/ stable main" | sudo tee /etc/apt/sources.list.d/google-chrome.list > /dev/null
wget -q -O - https://dl-ssl.google.com/linux/linux_signing_key.pub | sudo apt-key add -
```
- [PostgreSQL](https://www.postgresql.org/download/linux/ubuntu/)
```
echo "deb http://apt.postgresql.org/pub/repos/apt/ bionic-pgdg main" | sudo tee /etc/apt/sources.list.d/pgdg.list > /dev/null
wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -
```

## Software Checklist

### Via Aptitude

- `sudo apt install bash-completion` - allows configuring autocompletion for bash aliases
- `sudo apt install build-essential` - includes all packages needed to compile a Debian package (e.g. GCC)
- `sudo apt install python3-pip python3-setuptools python3-dev` - **PIP** for Python 3, as well as other major deps required for installing some Python packages
- `sudo apt install git` - **Git** - possibly the best version control system out there
- `sudo apt install guake` - **Guake** - a dropdown terminal that can be shown / hidden with a shortcut
- `sudo apt install tmux` - **Tmux**, a terminal multiplexer, e.g. allows splitting your terminal into panes
- `sudo apt install vim-gtk vim-python-jedi && vim-addons install python-jedi` - **Vim**, a version of Vim that allows yanking/pasting to/from the clipboard (`"+y`/`"+p`)
- `sudo apt install direnv` - **Direnv**, unclutter your `.bashrc` by moving environment vars to individual `.envrc` files
- `sudo apt install docker.io` - **Docker**, software for running containers ~*i.e. the lightweight VMs*~
- `sudo apt install docker-compose` - **docker-compose**, bring up and tear down multi-container environments
- `sudo apt install tlp tlp-rdw` - **TLP**, a Linux power management tool, must-have on laptops
- `sudo apt install nodejs npm` - **Node.js**, a javascript runtime & **npm** for package management
- `sudo apt install yubioath-desktop yubikey-personalization-gui` - **Yubikey Authenticator**, **Yubikey Personalization Tool**, needed in case if you are using Yubikeys (looks like `yubikey-manager-qt` is missing on LM 20)
- `sudo apt install scdaemon` - **Smartcard** daemon for GnuPG (required if you are using Yubikey to store your GPG keys)
- `sudo apt install wireshark-qt` - **Wireshark**, a GUI for wireshark packet analyzer
- `sudo apt install htop glances powertop sysstat` - monitorying tools
- `sudo apt install traceroute tcpflow nmap socat` - networking tools
- `sudo apt install stress siege apache2-utils` - various load testing tools
- `sudo apt install xclip` - a CLI utility that provides an interface to "the clipboard"
- `sudo apt install jq finger` - misc handy utilities
- `sudo apt install fonts-powerline` - fixed powerline fonts
- `sudo apt install kubectl` - **kubectl**, a CLI for working with k8s clusters
- `sudo apt install helm` - **Helm**, package manager for Kubernetes

Optional:
- `sudo apt install pgadmin4 postgis-gui postgresql-client` - various tools for working with **PostgreSQL**
- `sudo apt install mongodb-clients` - CLI client for **MongoDB**
- `sudo apt install snapd` - **Snappy**, a cross-distro package manager developed by Canonical

### KVM (a hypervisor for Minikube)

```
sudo apt install qemu-kvm libvirt-daemon-system libvirt-clients bridge-utils

# run & check out the output
virt-host-validate

sudo modprobe vhost_net
sudo lsmod | grep vhost
echo "vhost_net" | sudo tee -a /etc/modules

sudo apt install virt-manager
```

### Via Flatpak / Snap / NPM / Pip

- `flatpak install flathub com.skype.Client` or `snap install skype` - **Skype**, a text/voice/video chat app ~pwned~ owned by Microsoft
- `flatpak install flathub com.slack.Slack` or `snap install slack` - **Slack**, a team colaboration tool, i.e. a text chat on steroids
- `flatpak install flathub com.spotify.Client` or `snap install spotify` - **Spotify**, a music streaming app by Spotify
- `flatpak install flathub com.getpostman.Postman` or `snap intall postman` - **Postman**, a graphical tool for API development and testing
- `flatpak install flathub org.qgis.qgis` - **QGIS**, a desktop geographic information system app
- `flatpak install flathub com.jetbrains.IntelliJ-IDEA-Ultimate` or `snap install intellij-idea-ultimate --classic`- **Intellij IDEA**, possibly the best IDE for developing any app that is JVM-based, there is also a free community edition with less features
- `flatpak install flathub com.bitwarden.desktop` or `snap install bitwarden` - **BitWarden**, an open source password manager done right (at least from the user perspective)
- `npm install -g tldr` or `snap install tldr` - **TLDR**, a great collection of simplified man pages, first stop for help on any terminal command
- `pip3 install --user s-tui` - **S-TUI**, a cli tool that graps cpu freq, utilization and temperature over time
- `pip3 install --upgrade --user awscli` - **AWS CLI**, a cli tool to work with Amazon Web Services
- `pip3 install --user locust` - **Locust.io**, a load testing tool with scenarios written in Python
- `pip3 install --user powerline-status` - **Powerline**, a statusline plugin for bash, tmux etc
- `pip3 install --user powerline-gitstatus` - a Powerline segment for showing the status of a Git working copy

### Via SdkMan

- `curl -s "https://get.sdkman.io" | bash` - [SdkMan](https://sdkman.io/) itself
- `sdk install java`
- `sdk install gradle`
- `sdk install maven`
- `sdk install visualvm`

### Via other means (e.g. manually)

- [Tmux Plugin Manager](https://github.com/tmux-plugins/tpm)
- [Minikube](https://github.com/kubernetes/minikube)
- [kubectx & kubens](https://github.com/ahmetb/kubectx)
- [stern](https://github.com/wercker/stern)
- [Terraform version manager](https://github.com/tfutils/tfenv)
- [Eclipse Memory Analyzer](https://www.eclipse.org/mat/downloads.php)
- [GCViewer](https://github.com/chewiebug/GCViewer)
- [Java Mission Control](https://www.oracle.com/technetwork/java/javaseproducts/mission-control/index.html)
