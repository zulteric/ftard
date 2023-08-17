---
title: "Git Push to Remote Server"
date: 2021-01-01T18:09:16-05:00
draft: true
tags:
  - git
  - linux
---
Is there a better way to get those pages out into the wild and free them from your keystrokes and up onto your web server? Yes, and even better than ftp, scp, rsync or simply drag and dropping files, at your disposal there is [GIT]!
> Git is a free and open source distributed version control system designed to handle everything from small to very large projects with speed and efficiency.

Create your directory on your website, or use your root if that is what you are using. In my case I have an extra domain that sits in its own directory on the root. This is also set up with ssh-keys for authentication. Read how I did it for my set up,.. [SSH-Keys with Namecheap](http://ftard.me/posts/ssh-keys-with-namecheap/)

On your remote server:
initiate a new repo
``` bash
git init
```
to enable pushing to a checked out branch on the server type
``` bash
git config receive.denyCurrentBranch updateInstead
```
---
On your local machine:
``` bash
git remote add origin ssh://user@yourdomain:port/home/user/path_to_folder
git push origin (branch)
```
Where (branch) is the branch you wish to push (i.e. master, dev, pub etc,..)
In your remote directory make sure you check out the new branch or nothing will show.

``` bash
cd newdir/
git checkout (branch)
```

[GIT]: https://git-scm.com
