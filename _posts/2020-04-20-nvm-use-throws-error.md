---
title: Cannot create a file when that file already exists
published: true
---

# [](#header-1)nvm Error - Cannot create a file when that file already exists
Platform : Windows
NVM Installation Path C:\nvm

Recently i wanted to upgrade my node version in my machine. I switched to nvm and installed the latest version of node, which at the time of writing is 12.16.2.
Once i installed the new version, i tried to switch to the latest version using
```js
nvm use 12.16.2
```

However, nvm was quick to complain with an error message : 
exit status 1: Cannot create a file when that file already exists.

After some research i found that nvm internally creates a SYMLINK to point at the current version of node.js. The location of the symlink is at C:\nvm\current (in my machine) .
I deleted the file and then tried nvm use 12.16.2 and voila, it works.. !!

Hope this helps..