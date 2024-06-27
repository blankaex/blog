---
layout: post
title:  "How to Switch to Linux"
date: 2020-03-10
excerpt: "A guide on how to make the right choices."
tag:
- Linux
---

If you're reading this blog post, then you're probably one of my friends, because no one else reads my blog. But if you're not, then you're probably someone who's already considering switching your main operating system to some flavour of Linux. And the reason you haven't switched yet is because you still have some lingering concerns. If this sounds like you, then you've come to the right place.

I, like many others, used Windows as my main operating system for quite a long time, and I, like many others, found myself riddled with inconveniences at every stop and turn. I thought it was ridiculous that I had to jump through so many flaming hoops just to achieve basic quality of life changes, and that I had to reinstall my operating system every 6-12 months when the bubble gum and sticky tape inevitably fell apart.

Everyone told me ditching Windows would solve all of my problems, but I'd gotten so familiar with my entire configuration that I was reluctant to let go. Eventually though, I grew tired of someone else dictating how I should use my own computer and decided it was time to start fresh. It was the best decision of my life. My entire experience has been so much less stressful and I've never looked back or regretted a single second of it.

_<center>Now it's your turn.</center>_

{% capture images %}
    {{ site.url }}/assets/res/2020-03-10-switching-to-linux/1446021143955.jpg
{% endcapture %}
{% include gallery images=images %}

The first step is to choose your distro. Once you've done that, the rest is quite honestly smooth sailing. What's a distro? Well, Linux isn't actually an operating system, [but you don't need me to tell you that](https://wiki.installgentoo.com/index.php/Interjection). What you're actually looking to replace Windows with is a Linux _distribution_ (hence, distro), but it might be hard to decide when there are so many options and you have so little context. So, I'll make it easy for you:

**Install Fedora [(link)](https://getfedora.org/en/workstation/).**

{% capture images %}
    {{ site.url }}/assets/res/2020-03-10-switching-to-linux/1464143937191.jpg
{% endcapture %}
{% include gallery images=images caption="*tips fedora*" %}

I'm sure you've done some research and found a clickbait article or two that gave you recommendations with flimsy justifications along the lines of _"beginner friendly"_ or _"similar to Windows"_. Let me just make one thing clear before we move on: **all of this is complete bullshit**. The fact of the matter is, all distros are more or less the same thing. Anything you can do on Ubuntu, you can do on Debian, Fedora, Red Hat, Mint, Manjaro, Gentoo, Red Star, [Fried Chicken Linux](https://github.com/sacmt-hciie/fried-chicken-linux) or whatever.

This includes, by the way, the "theme" of your OS. I'm sure part of, or maybe even most of your reason for wanting to switch to Linux is to imitate a "cool" setup you saw on a desktop thread on /g/, so naturally you would want to go for the same distro. However, the look and feel of your environment is _completely independent_ of your distribution. Unlike changing visual styles on Windows, which only rotates a couple of colours, changing window managers or desktop environments on a Linux distro can get you from [this]({{ site.url }}/assets/res/2020-03-10-switching-to-linux/b231d61f93f00151c0059847ebf3636cf563e9a9.png) to [this]({{ site.url }}/assets/res/2020-03-10-switching-to-linux/1535239046271.gif), so there's no need to worry about your rice. In short, **choosing a distro based on how it looks is extremely stupid.**

{% capture images %}
    {{ site.url }}/assets/res/2020-03-10-switching-to-linux/screenshot.png
{% endcapture %}
{% include gallery images=images %}

_Why Fedora, then?_ Because it has great defaults. It's super easy to get up and running, and it's immediately usable out of the box. It comes with all the essentials, and is extremely well-integrated with the Linux ecosystem (i.e. [GNOME](https://en.wikipedia.org/wiki/GNOME), [SELinux](https://en.wikipedia.org/wiki/Security-Enhanced_Linux)). In fact, managing SELinux on Fedora is seamless because Red Hat maintains it. Your binaries will ship with the best protections, and you'll appreciate the minimal install option if you decide to eventually go down the power user rabbit hole.

_But if distros are mostly the same, then can't I just use anything?_ [No.]({{ site.url }}/derivative-distros/) Aside from the issues with derivatives, the features I mentioned above are some of the few ways distros _can_ differ, and you definitely want them all. Take it at faith and try Fedora for a few months, even if nothing about it seems appealing to you. Just as your first car need not be your last car, your first Linux distro need not be your last Linux distro.

If you've made it this far without messaging me to address the elephant in the room, congratulations.

{% capture images %}
    {{ site.url }}/assets/res/2020-03-10-switching-to-linux/3EQeOfsb-Jo0fm98DiPJC44Jc7WloVM4_UmZKk58aHM.jpg
{% endcapture %}
{% include gallery images=images %}

I know what you're going to say. _Blank, recommending a distro that isn't Arch? Perhaps I shall quickly look outside to make sure the sky is not falling and the seas are not running red with blood! Haw he haw he haw!_ [Well, you smarmy cunt,](https://youtu.be/Vtu0_wwMtgg?t=12) I still maintain that [Arch Linux is one of the easiest distros to use and manage](https://youtu.be/6bsNIdYw5Ak). However, I have a very good reason for not recommending it to inexperienced Linux users: Arch requires you to know what you want on your system.

Arch doesn't come with very many things. After a complete install, you won't have a file manager, a web browser, an image viewer, a video player, a word processor or anything you might consider "essential". Heck, you won't even have a graphical environment. All you get is a command line. This is a _good_ thing, because you can install exactly what you want and nothing more. However, this isn't so great for new Linux users because you _won't know_ what you want.

Of course, you _could_ use Arch and try all the different Linux offerings one by one, but let's be real—no one has the time or patience for that. More likely than not, you'll have no idea where to start because there are so many options, and you'll just grow miserable and get traumatised and leave Linux. It's the problem of choice all over again. I think it's much more beneficial to start off with what Fedora gives you, so you can learn what you do and don't like, and then adjust as necessary. The key here is to be open to change.

{% capture images %}
    {{ site.url }}/assets/res/2020-03-10-switching-to-linux/1408602060602.jpg
{% endcapture %}
{% include gallery images=images %}

Now, you may have noticed that I haven't given any specific software recommendations (aside from Fedora), or any links or installation instructions. That's because this isn't meant to be a technical guide—those are a dime a dozen—but rather a mindset one. Remember, the title of this blog post isn't "How to Install Linux", it's "How to Switch to Linux". And with that, I have one final recommendation: it would be best to let go of the Windows mindset.

It's very tempting to want to continue doing things the "Windows way", especially if you don't know any better. For example, to install a program on Windows, you'd usually go find its website, download an installer and run that. _This is not how you install programs in Linux._ The Linux way is to use your package manager, which is more secure, safer and better (like most things on Linux). Catch yourself relapsing back to Windows. It's understandable to be adverse to change when seemingly fundamental concepts have suddenly become foreign, but accept it and you'll come to love it.

Anyway, that's all from me. Hopefully this has been useful in providing some insight on how to get started on Linux, and why you should. I'll leave you with a bit of assigned watching below. It's oddly appropriate; Luke's story about getting into Linux is uncannily similar to mine, from the wants all the way to the motivations. He also has [a](https://youtu.be/3zpgQpdy_fI) [lot](https://youtu.be/GUQx72j9Q3Y) [of](https://youtu.be/gYDYSSOA2f8) [videos](https://youtu.be/G4g-du1MIas) on related subjects that you'd probably be interested in if you made it all the way to the end. If you look around at some of his program tutorials, you'll probably find even more reasons to make the jump.

<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/_hNMfVIsyIc" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

---

## Aside: What about vidya?

In my experience, Linux equivalents of Windows software have been better 100% of the time. Unfortunately, video games don't really have "equivalents" per se, so what can you do? Well, video games are bad so you shouldn't be playing them in the first place, but failing that, I have three suggestions:

1. Proton
    - Valve's implementation of Wine, which you've no doubt come across if you're looking to play video games on Linux. Lets you play most Steam games "natively" on Linux, [just check how well they work](https://www.protondb.com/).
2. Virtual Machine
    - Run an operating system inside an operating system. Quite resource-heavy, so a bit unrealistic for resource-hungry games, but works well for lighter things like visual novels and Minesweeper.
3. Dual Boot
    - Have Windows installed and switch to play. Sounds like a PITA but all of the qualms of rebooting Windows don't exist on Linux and it's very easy to maintain a separate Windows install exclusively for games.
