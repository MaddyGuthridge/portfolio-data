# Distro-hopper's checklist

I, like all Linux users, am eternally dissatisfied with my experience. In the life-long search for setup perfection, I frequently decide to delete everything and install a different distribution on average once every 3-5 months.

Since I am super forgetful, I always forget to back up at least something, so I am writing this blog post to contain a checklist of things I need to back up before I wipe my system for the millionth time, with the hope that it may be beneficial to others.

<!--more-->

## Files

First of all, you should make backups of all your documents, photos, videos and other **user data**. Basically, make a copy of any folders in your `$HOME` directory that you don't want to lose.

For **programming projects**, it may not be worthwhile making a physical backup if they are already hosted somewhere else (eg GitHub). Instead, go through all of them and make sure you've committed and pushed all of your work.

## Configurations

If you like to heavily customise your system (and let's face it, given you're a Linux user, you definitely do 😋), it can also be worthwhile backing up your configurations and settings for various programs. While I can't hope to cover everything, here's an overview for some of the more common things.

For **SSH keys**, it can be a pain to regenerate them every time you reinstall your OS, especially if you need to register them in many places. It's probably a bad idea to upload these online anywhere, but creating a temporary local copy is probably fine. Just remember to delete the second copy after you've restored your keys, since otherwise anyone can use them if they get access to your backup drive.

If you like to create lots of aliases and functions in your **shell's configuration**, it's also a good idea to create backups of your dotfiles. However, it could be even better to share them using a GitHub repo ([for example](https://github.com/MaddyGuthridge/.dotfiles)). By including those configuration files and a simple install script, you can set up your terminal with a single git clone and `./install.sh`. This is especially useful if you want a consistent environment on all your systems.

Finally, if you've modified your **fstab** (file system table), it could be worthwhile backing it up too, since it will save you 15 minutes of trying to get it working again later. For example, I modified my `/etc/fstab` to be able to access my Windows partition at `/mnt/windows`. After reinstalling, I simply copy that line back to my new system.

## Software

It's also a good idea to save a list of **software** that you use, so that you don't spend the next week frantically trying to reinstall tools you forgot about during your initial setup of your new system. Take the time to go through your apps list and make a list of the software you use the most.

If you've made any **modifications to files associated with software**, now would be a good idea to document those too. For example, I modified many of my `.desktop` entries in `~/.config/autostart` so that the apps would run minimised, so I added [a note in my dotfiles](https://github.com/MaddyGuthridge/.dotfiles/blob/main/autostart.md) that documents the changes required for each app.

If there are any drivers you've installed that are a little painful to set up, it's also a good idea to write yourself some instructions to get them working again.

## Extras for dual-booters

If you're dual-booting, some installers might mess with your existing boot partition entries (cough, cough, Fedora). Since I run Windows and Linux, I made a backup of `/boot/efi/EFI/Microsoft` to an external drive, then simply copied the directory back after reinstalling. After updating my Grub entries, I was able to boot Windows normally and Microsoft was none-the-wiser.

## The end

Thanks for reading, and I hope you found this useful. If I think of any other useful things that are worth considering before distro-hopping, I'll edit this post to add them in. If you've got any ideas, feel free to shoot me a message!

Happy hacking,

Maddy