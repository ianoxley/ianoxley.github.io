---
layout: post
title: Managing Node.js Versions With Homebrew
date: 2018-02-02
tags:
  -nodejs
  -homebrew
---

**TL;DR** Manage [Node.js](https://nodejs.org) versions with [Homebrew](https://brew.sh/) by using `brew link` and `brew unlink`:

```sh
$> node -v
v9.5.0
$> brew unlink node
$> brew link --force node@8
$> node -v
v8.9.4
```

***


Although you can use [dedicated tools](https://github.com/creationix/nvm) to manage your Node.js versions, I've got
by just fine using Homebrew's `link` and `unlink` commands:

1. Homebrew's `node` package points at the latest version of Node.js. You can find out exactly which version by running `brew info node`:

   ```sh
   $> brew info node
   node: stable 9.5.0 (bottled), HEAD
   ...
   ```
2. Install `node` using `brew install node`
3. Homebrew formulae are available for prior versions of Node.js and follow the `node@<version>`
   naming convention. You can see exactly which version of Node.js a formula points to by
   using the `info` command:

   ```sh
   $> brew info node@8
   node@8: stable 8.9.4 (bottled), HEAD [keg-only]
   ...
   ```
4. Install `node@8` using `brew install node@8`
5. With `node` and `node@8` installed we can switch between them like so:

   ```sh
   $> node -v
   v9.5.0 # <- node is pointing at the node formula
   $> brew unlink node
   $> brew link --force node@8 # --force required as node@8 is a keg-only formula
   $> node -v
   v8.9.4 # <- node now points at the node@8 formula
   ```
6. To change back to the latest Node.js, just do the opposite to what we've
   just done:

   ```sh
   $> brew unlink node@8
   $> brew link node
   $> node -v
   v9.5.0
   ```
