---
layout: post
title:  "Derivative Distribution Degeneracy"
date: 2021-04-08
excerpt: "And why you should never use a derivative distro."
tag:
- Linux
---

If you're somewhat familiar with Windows UX customisation, then you've probably heard of [Classic Shell](http://www.classicshell.net). It's a hacky bit of software that provides a few tweaks to the start menu and file explorer, and gives self-proclaimed Windows "power users" a false sense of agency over their computing environments.

{% capture images %}
    {{ site.url }}/assets/res/2021-04-08-derivative-distros/explorer1.png
{% endcapture %}
{% include gallery images=images %}

Imagine if someone grabbed a fresh install of Windows 10, installed Classic Shell on it, packaged the operating system as "Windows Tenn", and made it available for download. Would you install it? You'd have to be retarded to even consider it. **Yet this is exactly what happens with Linux distributions every day.**

Take a look at Linux Mint, a pretentious distribution that's [constantly topping the charts on DistroWatch](https://distrowatch.com/). If you take a look at [their "About" page](https://linuxmint.com/about.php), you'll notice that none of their selling points are actually exclusive to Linux Mint. They call it "Ubuntu-based", which really means it's just Ubuntu, but instead of shipping with the GNOME desktop environment, it ships with Cinnamon (which ironically is a GNOME derivative). Yes, it's literally Ubuntu with a different hat.

{% capture images %}
    {{ site.url }}/assets/res/2021-04-08-derivative-distros/EyLvJpIUcAELM3G.jpg
{% endcapture %}
{% include gallery images=images %}

Pop! OS is another flatulent distribution that's gained a lot of popularity recently. Similar to Linux Mint, it's just another reskin that offers nothing of value, and I say this without exaggeration. If you remove GNOME from Pop! OS then you are left with just Ubuntu by every stretch of the definition.

<div style="width: 100%; height: 0px; position: relative; padding-bottom: 56.471%;"><iframe src="https://streamable.com/e/9zkidj" frameborder="0" width="100%" height="100%" allowfullscreen style="width: 100%; height: 100%; position: absolute;"></iframe></div>

If you wanted a different desktop environment on Ubuntu, you could just install Ubuntu and then swap the desktop environment for whatever you like. This isn't any effort or elitist gatekeeping either, it's usually just a single package to install. You don't have to install an entirely separate distribution and restrict yourself from official documentation, support, community forums and probably most importantly, [security updates](https://blog.frizn.fr/linux-kernel/cve-2020-14381).

Part of the problem is likely due to advertising. It's so easy to package your own Linux distribution that everyone and their mums are doing it, and these are the same people installing them. They'll focus on the outward appearance of the UI and fall for cheap marketing like _"beginner-friendly"_ and _"similar to Windows"_, while blissfully unaware that desktop environment is completely independent of distribution.

{% capture images %}
    {{ site.url }}/assets/res/2021-04-08-derivative-distros/like-windows.png
{% endcapture %}
{% include gallery images=images %}

But derivative distributions aren't just stupid, they're also malevolent. I briefly alluded to this earlier, but there are a non-trivial number of people using these derivatives, which means there is also a non-trivial number of skilled developers maintaining them.

All of these people could instead be contributing upstream and further improving the base distribution, instead of pointlessly forking, splitting development, and hindering progress. And I don't just mean contributing code—better documentation and forum responses benefit everyone. Even an end user asking a question on a forum provides a resource for the next user.

So the moral of the story is: _never\* use derivative distributions_. But if you should avoid derivatives and ignore desktop environment, how should you choose your first distro? Don't. [I've said it before]({{ site.url }}/switching-to-linux/) so I won't go over it again in detail; just [install Fedora](https://getfedora.org/en/workstation/).

{% capture images %}
    {{ site.url }}/assets/res/2021-04-08-derivative-distros/m'aki.jpg
{% endcapture %}
{% include gallery images=images %}

## Manjaro

Manjaro has a special place in my heart due to my extremely rational loathing of its existence. The very concept of Manjaro itself already falls apart. It's an Arch-based distribution that ships with a number of different desktop environments, which makes no sense.

There is a very good reason that you'll rarely see Arch Linux users with a packaged desktop environment. Desktop environments provide a suite of packages that form a mostly static ecosystem, and are intended to be upgraded alongside the OS. Contrary to this, Arch is rolling release and thus does not have OS version upgrades. Users are expected to manage individual packages and keep all of them updated, without any partial upgrading. Shipping with desktop environments by default is antithetical this entire philosophy.

The developers have also proven their incompetence time and time again. A classic example is the time their SSL certificate (a component that keeps their website secure) expired. Their solution was to encourage users to wind back their clocks to trick their system into thinking the certificate was still valid. Renewing an SSL certificate is **free** (as in free beer), by the way. It's also **automatic**, meaning it should never expire.

Alarm bells should be ringing. You cannot possibly convince me that there is any reason for this distribution to exist, and you'd better be `dd`ing a bootable drive if you're reading this blog post from Manjaro.

{% capture images %}
    {{ site.url }}/assets/res/2021-04-08-derivative-distros/>manjaro.png
{% endcapture %}
{% include gallery images=images %}

## \* The case for derivatives

I put an asterisk here to cover my bases, because there actually are use cases where it would make sense to not use a mainline distribution. While desktop environments are a very simple drop-in replacement, many components of a Linux system are not, such as init.

If you enjoy pacman and the AUR but are not a fan of systemd, then using [Artix Linux](https://artixlinux.org) would be a sensible choice as opposed to trying to remove systemd from Arch Linux. But if you know what this means then you're not the target audience of this blog post anyway, and you probably already know everything I've discussed. What are you doing here?
