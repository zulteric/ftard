---
title: "Ssh Keys With Namecheap"
date: 2021-01-01T16:47:53-05:00
draft: true
tags:
  - git
  - linux
  - windoz
---
I like linux but I'm on WinDoz a lot and I use Powershell never PuTTY. I have a namecheap shared hosting plan and I can never remember how to access my site with ssh-keys, for shell access to my server and also using git for revision control and pushing content to my server. Here is a walk though using powershell.

1st check OpenSSH status on Windows. from [docs.microsoft][1]
``` bash
Get-WindowsCapability -Online | ? Name -like 'OpenSSH*'
```
Should return something like,..
``` bash
Name  : OpenSSH.Client~~~~0.0.1.0
State : NotPresent
Name  : OpenSSH.Server~~~~0.0.1.0
State : NotPresent
```
Install OpenSSH Client type,..
``` bash
Add-WindowsCapability -Online -Name OpenSSH.Client~~~~0.0.1.0
```
If you want a server run,..(I did not install, if you do double check [docs.microsoft][1])
``` bash
Add-WindowsCapability -Online -Name OpenSSH.Server~~~~0.0.1.0
```
You should have a ~\.ssh\ directory if Not
``` bash
mkdir ~\.ssh
cd ~\.ssh
ssh-keygen -t rsa -b 4096 -C "your@email.com"
```
I add a passphrase but you shouldn't need one. You now should have 2 files in ~\.ssh.

---

- Log into your namecheap web panel.
- Go to Security --> SSH Access.
- Press 'Manage SSH Keys'
- then press 'import key'.
---
- In the 'public' box copy paste the file contents of your public key.
- Add your password you created for the key into the password field.
- Press 'import'.
- When you press 'back' you should see your key
- Now press the 'manage' icon for your key.
- Now press 'Authorize'.
---
Now here is the real deal and the make or break moment lets see if it works. If your plan is shared hosting and not a VPS or something you must specify the port as 21098. If you do have VPS it is port 22 as usual.
``` bash
ssh user@yoursite.com -p21098
```






[1]: https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse
