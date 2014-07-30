# rmnbin

This is a collection of scripts I put in a global path (usually `/usr/local/bin`) on my system. Since I keep losing them when I format or change machines and frequently forget to restore them, I created a small repo to hold any I write.

### Scripts

##### [rmnupdate](https://github.com/rnelson/rmnbin/blob/master/sbin/rmnupdate)

The main administrative script, `rmnupdate`, creates or updates any symlinks to all files under `bin`/`sbin` to the appropriate global directory. Note that this script solely works on the local system; it does not update *rmnbin* from GitHub.

##### [updategems](https://github.com/rnelson/rmnbin/blob/master/bin/updategems)

`updategems` will update the gems on a project (via Bundler) in the current directory. If the project is under git, as determined by having a `.git` directory alongside the `Gemfile`, it will also commit the updated `Gemfile.lock`. **Warning:** this will also push any local commits.

##### [objcc](https://github.com/rnelson/rmnbin/blob/master/bin/objcc)

Compiling Objective-C requires a bunch of command line arguments which vary by system. To ease this, `objcc` calls [clang](http://clang.llvm.org) with the appropriate arguments. Tested on OS X (10.9), FreeBSD (PC-BSD 10), and Linux (Raspbian).

### Requirements

Scripts are currently written in the following languages:

+ Ruby (**note:** the `rmnupdate` script that creates symlinks is Ruby)
+ Bash

### Usage

1. Clone the repo somewhere (I use `/rmnbin`)
2. Run `sbin/rmnupdate` to update all of the links

### Notes

I haven't implemented a config of any sort yet, so `rmnupdate` has an `INSTDIR` variable that tells it to install under `/usr/local/{bin,sbin}`. I may or may not change that later.