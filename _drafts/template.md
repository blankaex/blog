---
layout: post
title:  "Template"
# date: 2045-0-0
excerpt: "Template"
tag:
---

{% capture images %}
    {{ site.url }}/assets/res/dir/filename.jpg
{% endcapture %}
{% include gallery images=images %}
