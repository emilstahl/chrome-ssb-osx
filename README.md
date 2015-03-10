chrome-ssb
==========

2014-07-26 UPDATE: There are currently some outstanding potential issues between OS X and Chrome updates that I really don't have time to look at (see the open issues).  If you need a rock solid modern SSB, I suggest perhaps looking at node-webkit for building SSBs.

You'll need modern node/npm but other than that it's actually pretty straightforward to setup SSBs...

* https://github.com/rogerwang/node-webkit
* https://github.com/mllrsohn/node-webkit-builder
* https://github.com/user4815162342/nw-ssb
* https://github.com/chagel/gmail-ssb

Also, check out: https://github.com/dmarmor/osx-chrome-ssb-gui/

---

Simple script for making Chrome SSBs on OS X

This is an update of [Bracken King](https://twitter.com/brackenthebox)'s original script published in [this 2010 article](http://www.lessannoyingcrm.com/articles/149/Create_application_shortcuts_in_Google_Chrome_on_a_Mac).

I've updated it a bit to work better:
* Allow spaces in all variables
* Properly Trim spaces for easy drag and dropping of icon paths
* Properly look for Chrome location in /Applications (it uses the first one it finds)
* Make the new App wherever it's called from
* Your Profile is placed in the correct location (in the Bundle) no matter where you move the app

## Usage
* Place chrome-ssb.sh in your path or somewhere convenient to call from
* Run chrome-ssb.sh wherever you want
* You can also move the created app anywhere you want without issues

**Note:** Finder may not pick up the icon (shows up as invisible) if you have the creation target folder active/open. You can make it show up by moving the App to a different folder. If you know a workaround, please send a pull request...

## Notes
* This script now makes a copy of the 'Google Chrome' launcher executable stub at application start (it is pretty small, about 13KB) instead of symlinking to solve 10.9 compatibility issues (see #22). The executable points to a specific version of the Google Chrome Framework (../Versions/[VERSION]/Google Chrome Framework.framework/Google Chrome Framework).
* Copying the launcher executable instead of symlinking will break OS X Gatekeeper's code signing. This shouldn't normally be a problem, but is discussed in depth in Issue #23

## TODO
* Better Icon Processing
  * http://www.amnoid.de/icns/makeicns.html
  * http://superuser.com/questions/133784/manipulate-mac-os-x-file-icons-from-automator-or-command-line

## License
Do as you will
