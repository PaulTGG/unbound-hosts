# Unbound Hosts
Conversions of StevenBlack's unified hosts, and DuckDuckGo's tracker blocklists, to Unbound's config file format.

## Usage

### conf files
These files are designed for a working Unbound server (soooo... do that first, I guess?).  Once Unbound is up and running, you can download whichever conf files you'd like, then tell Unbound to include them.  Doesn't matter where the conf file are, as long as Unbound can read them.

Quick refresher - add an "include" line for each file, e.g.

`include: /path/to/sbhosts.conf`

or

`include: c:\path\to\sbhosts.conf`

**Remember to restart Unbound after changing the config files.**

Also, if you're running Unbound locally on a Windows machine (because the size of the hosts file on Windows is... limited...), remember to change your machine's DNS settings to point to the Unbound server ("127.0.0.1" should work).

### Scripts

If you're using *nix, the files in the "scripts" folder are used to download the latest hosts files, convert them to Unbound's format, put the conversions in the "conf" folder, then clean up the downloaded and working files.

To use the scripts, you'll need `awk`, `grep`, `jq`, and `wget` installed.  They're designed to work within the repo's folder structure, so if you want to add them to your bin (or move them someplace else), or if you want them to write the files to a different location, you'll want to change the scripts.  Otherwise, make sure you `cd` into the scripts folder.


## Contributing

If you want changes to the block lists, submit changes to [StevenBlack hosts](https://github.com/StevenBlack/hosts) and/or [DuckDuckGo's Tracker Blocklists](https://github.com/duckduckgo/tracker-blocklists).  When I get notified that an update has happened, I'll update this repo.  (If you don't want to wait, you can always use the scripts to get updated conf files at your leisure.)

If you want changes to the scripts, feel free to fork me.  (This repo is going to do what it says on the tin, anything beyond that is out of scope.)
