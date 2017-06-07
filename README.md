# Laptop

Laptop is an idempotent script to set up a Mac OS X laptop for Rails development.

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
bash <(curl -s https://raw.githubusercontent.com/attack/laptop/master/mac)
```

## What it sets up

* chruby for managing versions of the Ruby programming language
* Ruby Build for installing Rubies
* Ruby stable for writing general-purpose code
* Bundler gem for managing Ruby libraries
* Homebrew + Cask for managing operating system libraries
* Hub gem for interacting with the GitHub API
* Heroku Config plugin for local `ENV` variables
* Heroku Toolbelt for interacting with the Heroku API
* Exuberant Ctags for indexing files for vim tab completion
* Postgres for storing relational data
* Redis for storing key-value data
* The Silver Searcher for finding things in files
* Tmux for saving project state and switching between projects
* Qt for headless JavaScript testing via Capybara Webkit
* Tig for an improved git log
* Alfred for application launching
* Caffeine for managing mac sleep
* Google Chrome
* Dropbox + Google Drive
* Textmate
* Gitx for a git GUI
* ItsyCal for a menu bar time + calendar
* Flux
* iTerm2
* vim + MacVim
* ShiftIt for window management
* solarized colour theme for terminal + iTerm
* [dotfiles](https://github.com/attack/dotfiles)

It should take less than 15 minutes to install (depends on your machine).

## Make your own customizations

Put your customizations in `~/.laptop.local`. For example, your
`~/.laptop.local` might look like this:

```sh
brew_cask_install spotify
brew_cask_install viscosity
start_if_needed Viscosity

rubies=( '1.9.3' '2.0.0' )
for local_ruby_version in ${rubies[@]}; do
  if ! is_ruby_version_installed $local_ruby_version; then
    fancy_echo "Installing Ruby $ruby ..."
      ruby_install $local_ruby_version
      chruby-exec $local_ruby_version gem update --system
      chruby-exec $local_ruby_version gem install bundler --no-document --pre
  fi
done

defaults write com.apple.menuextra.battery ShowPercent -string "YES"
```

## Credits

[thoughbot laptop](https://github.com/thoughtbot/laptop)

## License

Laptop is © 2011-2014 thoughtbot, inc. It is free software, and may be
redistributed under the terms specified in the LICENSE file.
