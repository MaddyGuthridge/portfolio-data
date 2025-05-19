# Getting set up for COMP1531, the good way

> ## IMPORTANT
> This post has been mostly superseded by the official COMP1531 setup guide. I recommend referring to that instead, and only checking this post if you're interested in my specific recommendations.

Hello everyone! I'm Maddy, one of this term's tutors for UNSW's COMP1531 course. I'm writing this blog post to act as a resource to help you (presumably a new COMP1531 student) create a setup that work well for you, making you work and learn productively, efficiently and effectively.

<!--more-->

> As a small disclaimer, this isn't an official resource, and is primarily my own opinions. I've taken reasonable precautions to ensure that this information is correct and informative, but I shall not be held liable in the unlikely event that you damage your system while following instructions listed here. Of course, if anything in this post needs fixing, let me know and I'll update it as soon as I can.

Before we begin, I'd like to give a little more background on why I wanted to write this, and explain why I believe that having a setup that works for you is so important. I live with a significantly limited working memory and poor attention regulation. As such, if my setup doesn't work with me, I struggle to get things done: I constantly need to ask myself "what is my current task?" and "what can I do to accomplish that task?", so things can become immensely challenging if my setup doesn't help me answer those questions quickly. I don't mean this in a sob-story "woe is me" kind of way; rather, I believe that my experiences give me a unique insight into how a well-designed working environment can be the difference between surviving and thriving in the field of software engineering. Even if you don't face the same difficulties as me, a good setup will still help you work more productively, learn more effectively, and hopefully help you maintain your sanity a little more easily.

In this post, I'm only planning to cover the basic steps to get an environment that works for you, however, if there is demand, I may also create resources to help you learn to use more tools that integrate with your setup to work more effectively! Let me know if you'd like to see these!

## What approach should you take?

There are three main approaches to creating a great setup, and all of them have advantages and disadvantages. Different people have different needs and different priorities, so I don't know what the best choice is for you. I recommend considering all of your options and going with whichever one appeals to you the most, or even better, *why not try all of them*? There's nothing forcing you to stick with your first choice for all eternity, and there are no consequences for changing your mind, so you're always free to experiment until you find the best option for you!

With that out of the way, let's take a look at the main approaches!

### 1. VS Code with SSH-FS

A popular option for working on CSE projects at UNSW is SSH-FS. It lets you remotely access your account on the CSE servers, opening and editing files as well as running terminals all within Visual Studio Code. To do this, it uses a tool called [SSH](https://en.wikipedia.org/wiki/Secure_Shell) to let you access your CSE account. This takes a very small amount of setup and is awesome for quick file edits and small projects.

![Remote login is a lot like astral projection](https://i.imgur.com/NM8TQP3.png)


However, SSH-FS tends to become a hindrance as you gain more experience as a programmer. When you're just getting started and need to focus on writing code and running simple terminal commands it is all you need, but as the scope of your knowledge and the scale of your projects increases, its limitations become increasingly apparent, as it doesn't allow you to do much more than that. In fact, SSH-FS disables some of VS Code's most-useful features, so you won't be able to:

* Get automatic code completion across multiple files
* Have any errors (other than the most basic syntax errors) show up as you type
* See helpful information about the code you're working with (such as telling you what a function does when you put your mouse over it)
* Access VS Code's built-in debugger
* Use test runner extensions to simplify your testing process
* Hide files not relevant to the current project (ok, this is technically possible with SSH-FS, but is a little annoying to get working).

While you can get by with SSH-FS in COMP1531, it isn't sustainable to use it in the long-run in my opinion. COMP1531 will be significantly more challenging than it needs to be, and courses after it will be nearly impossible. I'd suggest trying out some of the other options available to you.

If you still want to use SSH-FS, you can refer to [these official UNSW resources](https://cgi.cse.unsw.edu.au/~learn/homecomputing/sshfs-remote/) for setup instructions.

### 2. Using UNSW's VLab system

VLab is the name for the computer systems provided by the CSE faculty at UNSW. It runs Debian Linux with the XFCE desktop environment, and can be accessed directly using lab computers as well as remotely using VNC (which is essentially SSH for a graphical environment, rather than being command-line only).

VLab is an excellent choice for a working environment, because it provides a reliable system with plenty of tools already set up for you! In particular, VLab has VS Code installed, and you can get access to all of the features that SSH-FS disables (listed above).

There are a few downsides to using VLab which you could consider before choosing it.

* Accessing it remotely can be a little laggy, since it needs to stream an entire desktop over the internet rather than just a command line. This is particularly noticeable if you have a slow internet connection or are living internationally.
* You are only allocated a limited amount of disk space, which (in my experience) is sometimes not enough for COMP1531. I've noticed that many students run out of disk space later in the term, which can be particularly stressful if you don't recognise the error messages (files and folders fail to get created, particularly when installing things).
* Earlier courses may have changed your VS Code settings to simplify your experience, disabling many features that are extremely useful in COMP1531 and later courses. You can fix this by [resetting your VS Code settings](https://code.visualstudio.com/docs/getstarted/settings#_how-can-i-reset-my-user-settings).

Overall, VLab makes a great choice for a working environment, since everything you need is already there, and the downsides are manageable. Later in this post, I've got some helpful [tips for using VS Code](#tips-for-using-vs-code) which will help you get the most out of VLab.

Instructions for setting up VLab are available [here](https://cgi.cse.unsw.edu.au/~learn/homecomputing/vlab/).

### 3. Working locally

In COMP1531, it is also possible to set up your own computer so you can complete all of your work on it, with no SSH or VNC needed. This approach is called working locally. Working locally takes a bit more work to begin with, since you need to set up all of the tools you need yourself, but it is possible to create a system that provides all of the features of VLab with significantly fewer limitations.

* You are free to install any tools you want, and customise your system to exactly match your needs (of course, with great power comes great responsibility).
* You can enjoy the full performance of your own computer, with no internet latency slowing you down.
* You'll learn a lot about installing and configuring the tools we teach.

While this approach is significantly more involved, it's not as difficult as it sounds and even if you don't end up choosing it, giving it a go is a super fun adventure, and you'll learn a lot! 

> #### IMPORTANT
> When you work locally, it is ***essential*** that you remember to test your code on VLab before submitting your work. If your code doesn't work on VLab, you might lose marks!


If you like the sound of this, the rest of this post contains instructions on how to get set up to work locally in COMP1531.

## Getting set up locally

### 1. Choosing a text editor.

While, you can use any text editor you prefer, such as Gedit, or Vim ~~(or even Notepad if you want to make your life far more difficult than it needs to be)~~, I recommend using Visual Studio Code. It works super well with JavaScript and has tons of useful features, some of which I may explore in later blog posts. Most tutors at CSE will be able to help you best if you use it. The rest of this guide assumes you're using VS Code. If you want to use something else, it'll be up to you to research the processes for getting it working - perhaps you could write your own guide for your setup!

If you haven't already, I'd suggest downloading and installing VS Code now ([Linux](https://code.visualstudio.com/docs/setup/linux), [MacOS](https://code.visualstudio.com/docs/setup/mac), [Windows](https://code.visualstudio.com/docs/setup/windows)).

### 2. Setting up Windows Subsystem for Linux

If you're using Windows, there are a few extra steps you'll need to take to get everything working. If you're using Linux or MacOS, feel free to [skip ahead to the next step](#3-setup-for-macos-and-linux).

Windows has very different origins to MacOS and Linux. While MacOS and Linux both share a design evolved from [UNIX](https://en.wikipedia.org/wiki/Unix), Windows was originally based on [DOS](https://en.wikipedia.org/wiki/DOS). Due to the massive differences at the core of Windows, there's a risk that UNSW code might not work correctly on your system, or worse, that your code will work on your system and not on UNSW systems. As such, we'll be creating a Linux system inside Windows using a tool called [Windows Subsystem for Linux (WSL)](https://learn.microsoft.com/en-us/windows/wsl/about).

1. Open up Powershell as an administrator, then run the command `wsl --install`. You might need to wait a few minutes for it to complete.

2. If you get an error saying that virtualisation is disabled, you might need to change some settings in your BIOS. The specific steps you need to follow depend on your computer, but here are [some generic instructions](https://support.microsoft.com/en-us/windows/enable-virtualization-on-windows-11-pcs-c5578302-6e43-4b4b-a449-8ced115f58e1) that may help.

3. Once WSL is installed, you'll need to restart your computer. It'll probably do a Windows Update since we added a few new features to Windows. When you log back in, the second stage of the installation should begin automatically. If a terminal doesn't open within a minute or so, you should launch the newly-installed Ubuntu app from your start menu.

4. Wait for the installation to finish. For some people, this takes 30 seconds, but for others it can take up to half an hour. Make sure you don't stop the process, or you might need to [delete and reinstall WSL](https://superuser.com/a/1755410/1709412).

5. Once it's finished installing, you'll be prompted to `Enter a new UNIX username`. This name should be entirely lowercase with no whitespace. Most people just use their first name, for example I might use `maddy`.

6. You'll then be asked to create a password. When you type this in, it won't be shown on-screen for security reasons, but it is reading your input. Make sure you choose a password you remember, since it can be a challenge to reset it.

7. Confirm your password and you'll be dropped into a new Linux terminal session (you can check by running the `uname` command). The first thing you should do is update your system by running `sudo apt update && sudo apt upgrade`. If possible, you should memorise and run this command every few weeks to make sure your Linux system stays up-to-date.

8. The next thing we need to do is link WSL to VS Code. Open VS Code from the Windows start menu, then go to the extensions panel (*4 boxes* icon on the left-hand side).

9. Search for and install the `WSL` extension. It tells VS Code how to communicate with the Windows Subsystem for Linux, which allows you to use VS Code on Windows with the back-end running on Linux.

10. Once the extension has installed, you should see a "two arrows" button in the bottom-left corner of your VS Code window. Click it and choose to `Connect to WSL`. Wait for it to download and install the backend.

11. When the VS Code server is installed to WSL, open a terminal by pressing ``Ctrl + ` `` (control back-tick). You should see that it connects to WSL's terminal automatically.

12. Finally, make sure Git is installed by running `git --version` in your terminal. If you see something like `git version 2.40.1`, it is installed correctly. If you get a `git: command not found` error, you should install Git by running `sudo apt install git`.

Congratulations, you've successfully set up WSL! You should now skip ahead to the [Installing NodeJS section](#4-installing-nodejs).

### 3. Setup for MacOS and Linux

If you haven't already, you should install Git.

* On **MacOS**, you should open the terminal app, then run `git`, which will trigger a prompt to download extra features. Wait for this to download.
* If you use **Linux**, the instructions will depend on your distro. I'll leave it up to you to google the steps if required.

Finally, you'll need to add VS Code to your `PATH` variable if you're using **MacOS**. To do this, launch VS Code, press `Cmd+Shift+P`, then type "PATH" into the command palette, choosing the option to install the `code` command in your `PATH`.

### 4. Installing NodeJS

Now it's time to install NodeJS! There are many approaches for this, but I've found that the most reliable strategy is to use a tool called [NVM](https://github.com/nvm-sh/nvm#readme).

1. If you're on MacOS, run the commands `touch ~/.zshrc` and `touch ~/.bashrc` to ensure that the setup for NVM can run correctly.

2. Copy the command listed in [the installation instructions](https://github.com/nvm-sh/nvm#installing-and-updating) and paste it into a terminal. If you're using Windows, make sure you use a WSL terminal (you can run the Ubuntu program from your start menu to create one).

3. After executing the installation command, close and reopen your terminal.

4. Run `nvm install 20`, which will download and install the correct version of NodeJS.

5. After it completes, run the `node --version` command to check if it installed correctly. You should see something like `v18.16.0` as the output.

### 5. Setting up SSH and GitLab

If you're working locally, you'll also need to set up SSH keys for your computer, as well as for VLab. You generally shouldn't copy your SSH keys between different computers, as using different keys for each machine makes it far easier to revoke access for a single device once you're done with it.

1. In a Linux/MacOS terminal, run `ssh-keygen -t ed25519` and follow the prompts to generate the key. Unless you have a good reason to change them, you should keep the default options by pressing enter with no input on each prompt.

2. Visit the [CSE GitLab instance](https://nw-syd-gitlab.cseunsw.tech/) and sign in. If this is your first time signing in, you may need to wait for your account to be approved, which can take up to a day.

3. Once you're logged in, open up [GitLab's SSH settings](https://nw-syd-gitlab.cseunsw.tech/-/profile/keys).

4. View the SSH public key you generated in step 1 by running `cat ~/.ssh/id_ed25519.pub` in your terminal.

5. Copy the public key and add it as a key in GitLab's settings. Make sure to give it a descriptive name such as "laptop" or "VLab" so that you can tell which device it belongs to later.

6. To allow for quick access to VLab from your own computer, you can use the `ssh-copy-id` command to let you SSH into VLab without a password. Run `ssh-copy-id z1234567@login.cse.unsw.edu.au`.

7. You can then set up an SSH alias by running `echo "Host cse\n  Hostname login.cse.unsw.edu.au\n  User z1234567\n" >> ~/.ssh/config`. Then you can run `ssh cse` to quickly get terminal access to VLab.

### Congratulations!

If you've reached this point, you're successfully set up to work on your own computer! Any additional setup is covered in your labs. Before you go, have a read of the VS Code tips below to make the most of your awesome new workspace!

## Tips for using VS Code

Now that you're set up, let's take a moment to get you acquainted with your new system! These tips apply to both local setups and VLab, but won't work with SSH-FS.

### 1. Open your projects the good way

To get the most out of VS Code, you should open entire folders rather than files. This has many advantages:

* You can see all of your project files in the left-hand panel, but all the files outside of your project are hidden.
* VS Code can see all of your project files, meaning it can process them to give you a more helpful experience. This includes better error information, cross-file suggestions, and improved inline documentation (meaning when you put your mouse over a variable or function, VS Code will tell you all about it).
* You can use extra tools such as debuggers and linters more easily. If you want, I'll write more posts on how to do this!

### 2. Tweak settings to your liking

VS Code gives you tons of options that you can use to make it work "just right" for you. Here are some you might want to look at:

* Enabling auto-save: search settings for `files.autoSave` and set it to "After delay".
* Enabling bracket pair guides (VS Code will draw lines to show which opening bracket matches to which closing bracket): search for `editor.guides.bracketPairs` and choose the option that works best for you.
* Adding rulers (to tell you when a line of code is too long): search for `editor.rulers` and choose to "Edit in settings.json". For example, you can set your maximum line length to 80 characters by setting its value to `"editor.rulers": [79],`.

### 3. Install extensions to make your life easier

VS Code has a huge number of extensions that let you add more features to it! If people want, I'll cover some more extensions in later posts. For now, here are some of my personal favourites you can look into:

* A colour theme: make your editor match your personality. There are thousands available. My favourites are `Dracula` and `Synthwave 84`.
* A spell checker (I use `Code Spell Checker` by Street Side Software).
* `Git Graph`: this extension gives you a button that lets you view the history of a project, which is super helpful for learning how Git works!
* `Todo Tree`: this makes all kinds of `// TODO` comments show in bright colours so you don't forget them. It's got tons of settings to make everything look exactly how you like it (if you want, [here are my settings](https://gist.github.com/MaddyGuthridge/62689840b890e6a06dfac9b11c42969e)).

## The end

Thanks for taking the time to read this post! I hope it's helped you learn more about your options for creating a working environment that works for you. I'd love to know your thoughts on this, so feel free to reach out if you want to share any feedback. If you have any questions, make sure you post on the course forum so we can help you out!

Happy hacking!
<br>
Maddy

