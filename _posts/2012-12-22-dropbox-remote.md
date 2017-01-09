---
layout: post
date: 2012-12-22
title: "Using Dropbox as a Git Remote"
categories: git
comments: true
---

If you're working on a pet project and aren't quite ready to share it with the world via GitHub, here's a handy way you can backup your work to the cloud using Dropbox as a git remote:

1. Create a new, empty folder in your Dropbox to house your project's remote:

```
$ mkdir /path/to/Dropbox/gitremotes/yourproject
```

2. Initialise a bare git repository in this newly created folder:

```
$ git init --bare /path/to/Dropbox/gitremotes/yourproject
```

**NB** A _bare_ repository in Git is one that _only_ contains the revision info and system files (the files you'd normally find in the hidden `.git` directory), and doesn't contain the working tree. From Git version 1.7.0 and onwards, a repository has to be a bare repository in order to accept a push, so we must create our Dropbox remote as a bare repository.

3. Add our new remote to our project:

```
$ git remote add dropbox /path/to/Dropbox/gitremotes/yourproject
```

4. Push our work to our `dropbox` remote:

```
$ git push dropbox master
```

You can then interact with your Dropbox remote the same way you would with any other.
