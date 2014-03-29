# Laptop

Laptop is a script to set up a Mac OS X laptop for Rails development.

## Requirements

### Mac OS X

Install a C compiler:

For Lion (10.7) or Mountain Lion (10.8): use [Command Line Tools for
XCode](https://developer.apple.com/downloads/index.action).

For Mavericks (10.9): run `sudo xcodebuild -license` and follow the instructions
to accept the XCode agreement.  Then run `xcode-select --install` in your
terminal and then click "Install".

## Install

### Mac OS X

Read, then run the script:

```sh
bash <(curl -s https://raw.github.com/attack/laptop/master/mac)
```

## What it sets up

* Bundler gem for managing Ruby libraries
* Exuberant Ctags for indexing files for vim tab completion
* Foreman gem for serving Rails apps locally
* Heroku Config plugin for local `ENV` variables
* Heroku Toolbelt for interacting with the Heroku API
* Hub gem for interacting with the GitHub API
* Homebrew for managing operating system libraries (OS X only)
* Postgres for storing relational data
* Qt for headless JavaScript testing via Capybara Webkit
* Rails gem for writing web applications
* Rbenv for managing versions of the Ruby programming language
* Redis for storing key-value data
* Ruby Build for installing Rubies
* Ruby stable for writing general-purpose code
* The Silver Searcher for finding things in files
* Tmux for saving project state and switching between projects

It should take less than 15 minutes to install (depends on your machine).

## Make your own customizations

Put your customizations in `~/.laptop.local`. For example, your
`~/.laptop.local` might look like this:

```sh
#!/bin/sh

brew tap phinze/homebrew-cask
brew install brew-cask

brew cask install dropbox
brew cask install google-chrome
brew cask install rdio
```

## Credits

[thoughbot laptop](https://github.com/thoughtbot/laptop)

## License

Laptop is © 2011-2014 thoughtbot, inc. It is free software, and may be
redistributed under the terms specified in the LICENSE file.
