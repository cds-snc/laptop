# CDS Laptop

Laptop is a shell script which turns your Mac into an awesome web development machine.  It can be run multiple times on the same machine 
safely. It installs, upgrades, or skips packages based on what is already installed on the machine.

Note: We are currently focussed on smaller PHP-based projects, so this Laptop script excludes some of the other common dev environments like
Ruby, Python and Go.  This will change over time as we ramp up our dev team, and this script will be updated to provide configuration of 
those environments as we start working with them.

## What it sets up

### Applications
* [Firefox](https://www.mozilla.org/en-US/firefox/) Just another browser
* [GitHub Desktop] for setting up your SSH keys automatically
* [Google Chrome](https://www.google.com/chrome/index.html) Yet another browser
* [Insomnia](https://insomnia.rest/) for testing APIs
* [iTerm2](http://iterm2.com/) A better terminal
* [Lastpass](https://www.lastpass.com/) For remembering passwords
* [Sequel Pro](https://www.sequelpro.com/) for working with MySQL databases
* [Slack] for communicating with your team
* [Sublime Text 3] for coding all the things
* [The Unarchiver](http://unarchiver.c3.cx/unarchiver) for unarchiving all the things

### PHP
* [Composer](https://getcomposer.org) for installing PHP packages
* [Laravel Installer](https://laravel.com/docs/5.4/installation) for starting new Laravel applications
* [Laravel Valet](https://laravel.com/docs/5.4/valet) for local PHP/Laravel development
* [PHP 7.1](http://www.php.net/)

### Utilities
* [Homebrew] for managing operating system libraries
* [Homebrew Cask] for quickly installing Mac apps from the command line
* [Homebrew Services] so you can easily stop, start, and restart services
* [hub] for interacting with the GitHub API
* [The Silver Searcher] for finding things in files
* [Zsh] as your shell
* [Yarn](https://yarnpkg.com/en/) An alternative to NPM
* [Mailhog](https://github.com/mailhog/MailHog) for local development email testing

### Databases
* [MySQL] for storing relational data
* [Postgres] for storing relational data

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

## Installation

To install, open a terminal and run the install script:

```bash
bash <(curl -s https://raw.githubusercontent.com/gcdigital-gcnumerique/laptop/master/laptop)
```

**Important: After installation, be sure to quit and restart Terminal for changes to take effect.**

It is highly recommended to run the script regularly to keep your computer up to date. Once the script has been installed, you'll be able to run it at your convenience by typing `laptop` and hitting return in your Terminal.

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

* [Atom](https://atom.io/) GitHub's open source text editor
* [BBEdit](https://www.barebones.com/products/bbedit/) Another great text editor
* [Dropbox](https://www.dropbox.com/) File sharing/storage
* [Skype](https://www.skype.com/en/) For video conferencing

If you want to install additional tools or Mac apps with Homebrew, you may add further customizations to your `~/Brewfile.local`.

## How to manage background services (Postgres, MySQL)

The script does not automatically launch these services after installation because you might not need or want them to be running. With Homebrew Services, starting, stopping, or restarting these services is as easy as:

```
brew services start|stop|restart [name of service]
```

For example:

```
brew services start mysql
brew services start mailhog
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

## Credit and License
This CDS script is based on the [18F/Laptop](https://github.com/18F/laptop) and in turn [thoughtbot's laptop](https://github.com/thoughtbot/laptop) script.

thoughtbot's original work remains covered under an [MIT License](https://github.com/thoughtbot/laptop/blob/c997c4fb5a986b22d6c53214d8f219600a4561ee/LICENSE)
