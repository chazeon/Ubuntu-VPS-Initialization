# Initializing a new Ubuntu VPS server

## User

### Creation of the User named `${USER_NAME}`

```bash
# Creating a new user
useradd -m ${USER_NAME}
# Changing its password
passwd ${USER_NAME}
```

* Useradd with option `-m` creates the default home directory.

### Create its Home Directory:

```bash
mkhomedir_helper username
```

### Adding it to `sudo` User Group

```bash
usermod -aG sudo username
```

## Software Installation

### Upgrade

```bash
sudo apt-get update
sudo apt-get upgrade
sudo apt-get dist-upgrade
```

### Software

#### Shell Utils

```bash
apt-get install -y zsh vim tmux htop ntop aria2 p7zip-full
```

##### Set `.vimrc`
##### Set shell to `zsh`
##### Install `oh-my-zsh`

#### Server

```
apt-get install -y nginx 
```

#### Coding

```bash
apt-get install -y clang gcc python2 python3 aria2 build-essential git
```

##### Node.js

Look at [Installing Node.js via package manager](https://nodejs.org/en/download/package-manager/#debian-and-ubuntu-based-linux-distributions). Could try:

> Node.js is available from the NodeSource Debian and Ubuntu binary distributions repository (formerly Chris Lea's Launchpad PPA). Support for this repository, along with its scripts, can be found on GitHub at nodesource/distributions.
>
> NOTE: If you are using Ubuntu Precise or Debian Wheezy, you might want to read about running Node.js >= 6.x on older distros.
>
> ```bash
> curl -sL https://deb.nodesource.com/setup_6.x | sudo -E bash -
> sudo apt-get install -y nodejs
> ```
>
> Alternatively, for Node.js v7:
> ```bash
> curl -sL https://deb.nodesource.com/setup_7.x | sudo -E bash -
> sudo apt-get install -y nodejs
> ```