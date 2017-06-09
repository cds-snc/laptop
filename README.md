# CDS Laptop Customizations

These are local config files for the [18F/laptop](https://github.com/18F/laptop) 
script that add a few packages specific to the CDS development environment.  
See the [18F/laptop](https://github.com/18F/laptop) documentation for an overview
of the script and packages installed.

## Usage

To include the CDS customizations in your laptop setup, open a Terminal:

```bash
# Go to your home directory
cd ~

# Download the files to your computer
curl --remote-name https://raw.githubusercontent.com/gcdigital-gcnumerique/laptop/master/.laptop.local
curl --remote-name https://raw.githubusercontent.com/gcdigital-gcnumerique/laptop/master/Brewfile.local
```

You may add further customizations to `Brewfile.local`.

Finally, run the 18F/laptop install script:

```bash
bash <(curl -s https://raw.githubusercontent.com/18F/laptop/master/laptop)
```

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
