---
layout: post
title: Switching from Bash to Zsh
date: 2017-12-04
tags:
  -zsh
---

After years of using Bash without ever really having chosen Bash, I recently
switched my shell to Zsh. Why? Partly out of curiosity, and partly because
I was fed up with my bash history not always being available in multiple
terminals simultaneously.

Here's how I made the switch:

1. Installed the latest `zsh` and `zsh-completions` packages via Homebrew:
```bash
brew update
brew install zsh
brew install zsh-completions
```
2. Installed [Oh-My-Zsh](http://ohmyz.sh/)
3. Chose my preferred theme - I went with [avit](https://github.com/robbyrussell/oh-my-zsh/wiki/Themes#avit)
4. Added the `rbenv` setup code from my `.bash_profile` to my `.zshrc` file:
```bash
export PATH="$HOME/.rbenv/bin:$PATH"
eval "$(rbenv init -)"
```
5. Added aliases, ENV variables, and functions e.g. `docker_start` from my `.bash_profile` to my `.zshrc` file
6. Copied my bash history over to my zsh history using Ankit Goyal's fantastic [import bash history to
   zsh history](https://gist.github.com/goyalankit/a1c88bfc69107f93cda1)
script.
7. Set my shell to `zsh` in my `.vimrc` file:
```vimrc
set shell=/usr/local/bin/zsh
```
8. Enabled any relevant plugins for my workflow e.g. git, gitfast, docker.

It's now about two weeks since I made the switch and I've not looked back.
Granted, zsh won't be for everyone. But you've got to at least give these
things a try.
