---
layout: post
title: "ExpressJS Build System for Sublime Text"
date: 2015-08-14 23:11:15 +0100
comments: true
categories: editors
published: false
---

So I've recently been trying out Sublime Text. Why? I'm not sure to be honest. Vim key bindings courtesy of the Vintageous plugin are nice, but I digress. One of the first things I needed to do was setup a Node.js build system [1]:

1. From the menu select Tools -> Build System -> New Build System
2. Copy and paste the following into the build system file:

    {
        "cmd": ["/usr/local/bin/node", "$file"],
        "selector" : "source.js"
    }

3. Save the file as Node.sublime-build
4. Set your project to use your Node build system via the menu: Tools -> Build System -> Node

But what about Express? When you create an Express web app using the application generator tool, the docs tell you to start your app with the following command:

    DEBUG=myapp npm start

There's no point jumping out of Sublime Text to the terminal and back again over and over again, so why not create a build system to encapsulate this command? Why not indeed:

1. Tools -> Build System -> New Build System
2. Copy and paste the following code into the new build system file:

    {
        "shell_cmd": "DEBUG=myapp npm start"
    }

3. Save the file as ExpressJS.sublime-build
4. Set your Express project's build system to your new ExpressJS build system i.e. Tools -> Build System -> ExpressJS
5. Use the Build shortcut Cmd+B to start your server.

## Links
[1]: http://stackoverflow.com/a/20943710
