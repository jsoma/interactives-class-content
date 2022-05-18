# Setting up your command line

## Install nvm

Instead of installing node with Homebrew, we're going to use [nvm](https://github.com/nvm-sh/nvm). It's like pyenv for node, in that it allows us to juggle different versions of node without too much trouble.

[The instructions for installing nvm](https://github.com/nvm-sh/nvm#installing-and-updating) also warn against using Homebrew. Instead, [run the command they give you](https://github.com/nvm-sh/nvm#installing-and-updating) – it's just one line, it should be the one that starts with `curl`.

### Potential problems

Read the output!!!!!

If it says `=> Profile not found. Tried ~/.bashrc, ~/.bash_profile, ~/.zshrc, and ~/.profile.`, no problem. You can create a profile file by running this command:

```
touch ~/.zshrc
```

Then re-run the install command.

### Confirm `nvm` was successfully installed

Open new shell, run `nvm --version`.

* If it says command not found, it didn't work
* If it says anything else, you're good to go

## Installing node

If you've confirmed that `nvm` was installed, now try to use it to [install node](https://github.com/nvm-sh/nvm#usage):

```
nvm install node
```

### Confirm node was successfully installed

Instead of just testing to see if node is installed, we'll test two things: that node is installed, *and that when you type `node` it's the one we just installed.* Run this command:

```
which node
```

* If it says something that includes `.nvm`, like `/Users/username/.nvm/versions/node/v18.2.0/bin/node`, you're good to go
* If it says anything else, you might have an existing node that is conflicting with the one we just installed. Let me know and we can fix it.
