---
layout: post
title:  "PC Hardware Sucks"
date: 2021-07-10
excerpt: "Software sucks too, but that's a topic for another day."
tag:
- Rambling
---

My home PC hasn't seen an upgrade since 2015. I've yet to run into any problems that require replacement parts, and I haven't encountered any use cases that demand more processing power either, so I haven't had much reason to purchase new hardware. In spite of this, I decided to have a look around to see what was available and ended up confirming a belief that I probably knew was true in the back of my mind the whole time: PC hardware is in an awful state at the moment.

{% capture images %}
    {{ site.url }}/assets/res/2021-07-10-pc-hardware/220_3f5753886e42807a.gif
{% endcapture %}
{% include gallery images=images %}

The prices of PC parts right now are ridiculous. Many have noticed, but don't seem to understand the real reason. All of the complaints I've seen have been extremely short-sighted, and call out things like COVID and cryptocurrency<sup>1</sup> mining as causes for the high prices as if it were a recent problem, one that only surfaced in the last year or two. While they are definitely contributing factors, this is a much deeper-rooted issue and prices have been getting worse for the better part of the last decade at least. The actual problem? _Gamers_<sup>2</sup>.

PC gaming has seen a huge uptick in popularity, and manufacturers have (smartly) capitalised on this new market. The norm now is gamers, and you're shit out of luck if you just want a computer for computing. _You want a normal stick of memory? Too bad, we don't make those any more. You'll have to pay a premium and buy this GAMING RAM with edgy plastic casing. Oh, and about that motherboard? I know you're just going to turn them off but you'll still need to pay an extra $50 because it's a GAMING motherboard with rainbow lights._ Now that this has become the standard, it's ceased to be recognised as the problem that it is.

{% capture images %}
    {{ site.url }}/assets/res/2021-07-10-pc-hardware/203_a9eadaa21e6e59ed.jpg
{% endcapture %}
{% include gallery images=images %}

My grief doesn't end with just useless and expensive bells and whistles, though. The _gamer_ is a strange beast. It acts solely on hearsay and made-up statistics, and needs the latest and greatest hardware despite it offering no noticeable performance improvements. All you need is a few "tech youtubers" to praise a component and show some graphs annotated with meaningless numbers, and hordes of gamers will stampede the nearest _Best Buy<sup>TM</sup>_ to get a piece of the pie. As a result, demand for hardware is perpetually sky-high.

This tendency has the adverse effect of affecting manufacturing goals as well. Manufacturers aren't stupid—they know people will buy into their product if they can show that their new piece of hardware outputs a few bigger numbers on clinically contrived tests that mean nothing in real-world use cases. They've stopped building hardware that's sensible and extensible, and have gone full [Goodhart's law](https://en.wikipedia.org/wiki/Goodhart's_law) to push out bigger numbers. And why wouldn't they? That's where the money is.

{% capture images %}
    {{ site.url }}/assets/res/2021-07-10-pc-hardware/52_a5fc585c765622be.jpg
{% endcapture %}
{% include gallery images=images %}

The shift away from making better computer parts isn't just economically harmful, either. Take branch prediction, a "feature" introduced in a number of modern CPUs that brought a truckload of CVEs along with it. Spectre and meltdown, anyone? This is a prime example of manufacturers tunnel-visioning so hard on optimising for numbers that they've lost sight of all of the other factors that makes hardware desirable... like security. If you ask me, I'd rather take a CPU that ran a few cycles slower if that meant I could understand how the damn thing worked.

And on the topic of bad practices, we also have companies like _Nvidia_ (actually, it's the only company) who refuse to comply with standard protocols and insist on being a special snowflake. While _AMD_ open-sources their drivers, uses standard APIs, and is friendly with the community, making it a breeze to resolve issues or make contributions to improve performance and compatibility, _Nvidia_ stands by its dumb pride and forces widely-used and well-intentioned software projects like GNOME to (literally) hack up silly workarounds like this:

```
if (nvidia) {
    do this
}
else {
    do this because everyone else isn't a cunt
}
```

It's no surprise that Torvalds calls out _Nvidia_ as "the single worst company we've ever dealt with".

<iframe width="560" height="315" src="https://www.youtube.com/embed/_36yNWw_07g" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

Anyway, the smart play is probably to not buy a PC right now. Or ever, because I don't see how this is going to improve. Though admittedly that's not really practical. My next machine is probably just going to be a laptop with an integrated GPU—lesser of two evils and whatnot.

---

<small>
<sup>1</sup> Calling cryptocurrencies "crypto" is stupid. Crypto is an abbreviation for cryptography, an actual respected field of study, and has been used to denote such for dozens of years. It would be extremely ignorant to conflate this term with some idiots that waste electricity for fake money.
<br>
<sup>2</sup> Honestly I feel dirty using this word. I hate that it's completely normalised and there's no umbrella term that better encompasses the demographic. I wish there was, but it seems like my only choice is to live with the second-hand embarrassment.
</small>
