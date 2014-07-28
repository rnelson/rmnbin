# rmnbin

This is a collection of scripts I put in a global path (usually `/usr/local/bin`) on my system. Since I keep losing them when I format or change machines and frequently forget to restore them, I created a small repo to hold any I write.

### Scripts

##### rmnupdate

The main administrative script, `rmnupdate`, creates or updates any symlinks to all files under `bin`/`sbin` to the appropriate global directory. Note that this script solely works on the local system; it does not update *rmnbin* from GitHub.

##### updategems

`updategems` will update the gems on a project (via Bundler) in the current directory. If the project is under git, as determined by having a `.git` directory alongside the `Gemfile`, it will also commit the updated `Gemfile.lock`. **Warning:** this will also push any local commits.

### Usage

1. Clone the repo somewhere (I use `/rmnbin`)
2. Run `sbin/rmnupdate` to update all of the links

### Notes

I haven't implemented a config of any sort yet, so `rmnupdate` has an `INSTDIR` variable that tells it to install under `/usr/local/{bin,sbin}`. I may or may not change that later.