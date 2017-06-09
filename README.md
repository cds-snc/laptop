# CDS Laptop Customizations

This repository contains config files for the [18F/laptop](https://github.com/18F/laptop) script to add a few packages specific to the CDS development environment. 

See the [18F/laptop](https://github.com/18F/laptop) documentation for an overview of the script and packages installed.

## 18F/laptop

[18F/Laptop](https://github.com/18F/laptop) is a shell script which turns your Mac into an awesome web development machine.

It can be run multiple times on the same machine safely. It installs, upgrades, or skips packages based on what is already installed on the machine.

## Usage

To include the CDS customizations in your laptop setup, open a Terminal and execute the following commands:

```bash
# Go to your home directory
cd ~

# Download the files to your computer
curl --remote-name https://raw.githubusercontent.com/gcdigital-gcnumerique/laptop/master/.laptop.local
curl --remote-name https://raw.githubusercontent.com/gcdigital-gcnumerique/laptop/master/Brewfile.local
```

If you want to install additional tools or Mac apps with Homebrew, you may add further customizations to your `~/Brewfile.local`.

Finally, run the 18F/laptop install script:

```bash
bash <(curl -s https://raw.githubusercontent.com/18F/laptop/master/laptop)
```

*Important* After installation, be sure to quit and restart Terminal for changes to take effect.

## How to manage background services (Redis, Postgres, MySQL)

The script does not automatically launch these services after installation because you might not need or want them to be running. With Homebrew Services, starting, stopping, or restarting these services is as easy as:

brew services start|stop|restart [name of service]
For example:

brew services start redis
To see a list of all installed services:

brew services list
To start all services at once:

brew services start --all

## Customizations

We've added a few extra applications that we find are helpful in developing at CDS:
- PHP 7.1
- [Composer](https://getcomposer.org) for installing PHP packages
- [Sequel Pro](https://www.sequelpro.com/) for working with MySQL databases
- [Insomnia](https://insomnia.rest/) for testing APIs
- [Google Chrome](https://www.google.com/chrome/index.html) Just another browser
- [Firefox](https://www.mozilla.org/en-US/firefox/new/) Yet another browser 
- [Atom](https://atom.io/) GitHub's open source text editor
- [iTerm2](http://iterm2.com/) A better terminal
