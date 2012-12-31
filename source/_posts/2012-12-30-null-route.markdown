---
layout: post
title: "null route"
date: 2012-12-30 22:52
comments: false
categories: 
- Technology
tags:
- Networking
---

When a network is under DDOS attack, one convenient and somewhat effective tool is the so-called "blackhole routing" or "null route".

A *null route* (*blackhole route*) is a network route that goes nowhere.  Matching packets are simply dropped.  In a sense, it's a very limited firewall.

Null routing has an advantage over classical firewalls in two aspects:
    1. it's available on every potential network router and almost all morden OS's; and
    2. it adds virtually no performance hit as it won't go through the firewall rule chain before it will be processed.

Hence, null routes are often used to mitigate denial-of-service (DDOS) attacks before the hostile packets reaching the *bottleneck*.

In Linux environment, one can easily add a null route using command:
{% codeblock %}
ip route add blackhole xxx.xxx.xxx.xxx/xx
{% endcodeblock %}

To remove the null route:
{% codeblock %}
route delete xxx.xxx.xxx.xxx/xx
{% endcodeblock %}
