# bling-tty

A bling image for Toolbx and Distrobox.
Sure, you can use the distro you're used to, but what if ... 

This image is going to experiment with what a "born from cloud native" UNIX terminal experience would look like. 
Basically pretend a nerd is setting up your terminal for you but they're really opinionated.
We're starting small but have big aspirations.

- Starts with the latest Alpine image from the [Toolbx Community Images](https://github.com/toolbx-images/images)
- Adds some quality of life
  - starship prompt for that <3
  - just for task execution
  - chezmoi for dotfile management
  - btop for process management
  - micro and helix text editors
  - python3
  - Common tools: plocate, fzf
- Host Management QoL
  - These are meant for occasional one off commands, not complex workflows
    - Auto symlink the flatpak, podman, and docker commands
    - Auto symlink rpm-ostree for Fedora and EndlessOS
    - Auto symlink transactional-update for openSUSE MicroOS

## How to use

distrobox create -i ghcr.io/ublue-os/bling-tty -n bling-tty
distrobox enter blingtty

The user experience is much nicer if you [set your terminal open right in the container]() and is the intended experience for bling-tty.

## Why?

While LTS images pay the bills they move at that pace for a reason, I wanted:

- Something that kept up the pace with cloud native tech
- Expansive repos so all stack needs are covered
  - But also has all the cool new tools the rustaceans keep cranking out
- apk is _fast_

And of course, as the user space for a cloud-native desktop the biggest reason is it's everywhere in the stack, why not be the "default terminal"?

Also, I've never gotten really to know Alpine, the problem with running distros like this bare metal on my PC is that there's a whole bunch of hardware quirks and all sorts of little enablement things that more generalized distros tend to get right. 

But in a Toolbx/Distrobox world the kernel and anything that talks to hardware is handled by the host operating system.
This let's us concentrate on just the CLI experience, get yourself some of that UNIX bling.
Also apk is fast. 

## Scope and Cynicism

I know what you're thinking, we're just going to shove everything from [Modern UNIX](https://github.com/ibraheemdev/modern-unix) in there and it's going to look like a glitter explosion. 

That's why I'm going to be strongly opinionated, so use this as a base to build your own perfect CLI experience.

This is a tame first effort, one of you out there is going to make something better than this, the perfect CLI workspace, I salute you. 

## Finding Good Base Images

Of course you can make this however you want, but start with the [Toolbx Community images](https://github.com/toolbx-images/images).
These are a set of mostly-stock images with packages needed to run as a toolbox/distrobox already installed. 

Try to derive your blingbox from those base images so we can all help maintain them over time, you can't have bling without good stock!

Tag your image with `bling-tty` to share with others!