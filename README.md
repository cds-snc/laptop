# CDS Laptop

Laptop is a shell script which turns your Mac into an awesome web development machine. 

It can be run multiple times on the same machine safely. It installs, upgrades, or skips packages based on what is already installed on the machine.

Based on [18F/Laptop](https://github.com/18F/laptop) and [thoughtbot's laptop](https://github.com/thoughtbot/laptop) script.

## What it sets up

* [chruby] for managing [Ruby] versions
* [GitHub Desktop] for setting up your SSH keys automatically
* [Homebrew] for managing operating system libraries
* [Homebrew Cask] for quickly installing Mac apps from the command line
* [Homebrew Services] so you can easily stop, start, and restart services
* [hub] for interacting with the GitHub API
* [MySQL] for storing relational data
* [n] for managing Node.js versions if you do not have [Node.js] already installed (Includes latest [Node.js] and [NPM], for running apps and installing JavaScript packages)
* [Postgres] for storing relational data
* [pyenv] for managing Python versions if you do not have [Python] already installed (includes the latest 3.x [Python])
* [ruby-install] for installing different versions of Ruby
* [Slack] for communicating with your team
* [Sublime Text 3] for coding all the things
* [The Silver Searcher] for finding things in files
* [Virtualenv] for creating isolated Python environments (via [pyenv] if it is installed)
* [Virtualenvwrapper] for extending Virtualenv (via [pyenv] if it is installed)
* [Zsh] as your shell
* PHP 7.1
* [Composer](https://getcomposer.org) for installing PHP packages
* [Sequel Pro](https://www.sequelpro.com/) for working with MySQL databases
* [Google Chrome](https://www.google.com/chrome/index.html) Just another browser

[chruby]: https://github.com/postmodern/chruby
[GitHub Desktop]: https://desktop.github.com/
[Homebrew]: http://brew.sh/
[Homebrew Cask]: http://caskroom.io/
[Homebrew Services]: https://github.com/Homebrew/homebrew-services
[hub]: https://github.com/github/hub
[MySQL]: https://www.mysql.com/
[n]: https://github.com/tj/n
[Node.js]: http://nodejs.org/
[NPM]: https://www.npmjs.org/
[Postgres]: http://www.postgresql.org/
[Python]: https://www.python.org/
[pyenv]: https://github.com/yyuu/pyenv/
[Ruby]: https://www.ruby-lang.org/en/
[ruby-install]: https://github.com/postmodern/ruby-install
[Slack]: https://slack.com/
[Sublime Text 3]: http://www.sublimetext.com/3
[The Silver Searcher]: https://github.com/ggreer/the_silver_searcher
[Virtualenv]: https://virtualenv.pypa.io/en/latest/
[Virtualenvwrapper]: http://virtualenvwrapper.readthedocs.org/en/latest/#
[Zsh]: http://www.zsh.org/

It should take less than 15 minutes to install (depends on your machine and internet connection).

## Customization

To customize your laptop setup, open a Terminal and execute the following commands:

```bash
# Go to your home directory
cd ~

# Download the files to your computer
curl --remote-name https://raw.githubusercontent.com/gcdigital-gcnumerique/laptop/master/.laptop.local
curl --remote-name https://raw.githubusercontent.com/gcdigital-gcnumerique/laptop/master/Brewfile.local
```

These config files will add a few extra packages that you may find useful, including:  

- [Firefox](https://www.mozilla.org/en-US/firefox/new/) Yet another browser 
- [Atom](https://atom.io/) GitHub's open source text editor
- [iTerm2](http://iterm2.com/) A better terminal
- [Insomnia](https://insomnia.rest/) for testing APIs

If you want to install additional tools or Mac apps with Homebrew, you may add further customizations to your `~/Brewfile.local`.

## Installation

To install, open a terminal and run the install script:

```bash
bash <(curl -s https://raw.githubusercontent.com/gcdigital-gcnumerique/laptop/master/laptop)
```

*Important* After installation, be sure to quit and restart Terminal for changes to take effect.

It is highly recommended to run the script regularly to keep your computer up to date. Once the script has been installed, you'll be able to run it at your convenience by typing laptop and hitting return in your Terminal.

## How to manage background services (Redis, Postgres, MySQL)

The script does not automatically launch these services after installation because you might not need or want them to be running. With Homebrew Services, starting, stopping, or restarting these services is as easy as:

```
brew services start|stop|restart [name of service]
```

For example:

```
brew services start mysql
```

To see a list of all installed services:

```
brew services list
```

To start all services at once:

```
brew services start --all
```

How to switch your shell back to bash from zsh (or vice versa)
--------------------------------------------------------------
1. Find out which shell you're currently running: `echo $SHELL`
2. Find out the location of the shell you want to switch to. For example, if
   you want to switch to `bash`, run `which bash`.
3. Verify if the shell location is included in `/etc/shells`.
   Run `cat /etc/shells` to see the contents of the file.
4. If the location of the shell is included, run
   `chsh -s [the location of the shell]`.
   For example, if `which bash` returned `/bin/bash`, you would run
  `chsh -s /bin/bash`.

   If the location of the shell is not in `/etc/shells`, add it, then run the
   `chsh` command.
   If you have Sublime Text, you can open the file by running
   `subl /etc/shells`.
5. Quit and restart Terminal (or iTerm2), or open a new tab for the new shell
   to take effect.

Whether you're using bash or zsh, we recommend installing the latest versions
with Homebrew because the versions that came with your Mac are really old.
```
brew install bash
```
or
```
brew install zsh
```
