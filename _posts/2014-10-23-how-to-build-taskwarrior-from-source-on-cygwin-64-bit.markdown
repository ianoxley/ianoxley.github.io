---
layout: post
title: "How to build Taskwarrior from source on Cygwin 64-bit"
date: 2014-10-23 20:12:41 +0100
comments: true
categories: Productivity, Cygwin
---

I've been trying out Taskwarrior to manage my todo list(s) recently. Installing it up on my Mac easy thanks to Homebrew: `brew install task` and I was done. On Windows, Taskwarrior doesn't run natively, so I needed to run it via Cygwin. Although there is a `task` package for Cygwin, it's currently only available for 32-bit Cygwin. I use 64-bit Cygwin so had to build Taskwarrior from source. How hard could it be?

The answer, fortunately, was "not very". I had a couple of missing dependencies when I ran cmake, but that was it:

- The first caused a CMAKE_CXX_COMPILER not found error, for which I had to install the g++ compiler
- The second caused cmake to complain it couldn't find libuuid. I checked the CMakeLists.txt and CMakeCache.txt files, and it turned out there wasn't a problem with libuuid - the problem was the UUID_INCLUDE_DIR was not set. I installed the libuuid development package to fix this.

Once I'd installed g++ and libuuid-devel, Taskwarrior compiled and installed without a problem.
