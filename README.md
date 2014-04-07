thoughtbot dotfiles (customized to andycroll)
===================

Install
-------

First, [fork this repo](https://github.com/andycroll/install.sh/dotfiles#fork_box) on Github.

Then, clone your Github fork onto your laptop and install it:

    git clone git@github.com:andycroll/dotfiles.git
    cd dotfiles
    ./install.sh

This will create symlinks for all config files in your home directory. You can
safely run this file multiple times to update.

Why fork?
---------

dotfiles are fairly personal. You should be able to modify your dotfiles, and save them in version control in your fork.

However, the thoughtbot folks are often tweaking these dotfiles and you want to be able to get those updates.

So, your master branch is meant for your customizations and use the `upstream` branch to get thoughtbot's updates.

Set up the upstream branch
--------------------------

You only have to do this once:

    git remote add upstream git@github.com:thoughtbot/dotfiles.git
    git fetch upstream
    git checkout -b upstream upstream/master

Update thoughtbot's changes into your customizations
----------------------------------------------------

You will want to customize your environment. We suggest making changes in files that are not in thoughtbot's files.

For example, to customize your `zsh` config, make your changes in `~/.zshenv`:

    # RVM
    [[ -s '/Users/croaky/.rvm/scripts/rvm' ]] && source '/Users/croaky/.rvm/scripts/rvm'

    # recommended by brew doctor
    export PATH="/usr/local/bin:/usr/local/sbin:$PATH"

Commit those kinds of things in your master branch.

Then, each time you want to update thoughtbot's changes.

    git checkout upstream
    git pull
    git checkout master
    git rebase upstream