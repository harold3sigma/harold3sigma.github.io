---
author: jagira
date: '2011-02-23 20:03:00'
layout: post
slug: configurable-message-templates-in-rails
status: publish
title: Configurable Message Templates in Rails
wordpress_id: '59'
tags:
- programming
- ruby
---

Modifying erb templates for small messages is not maintainable when
the number of messages is large. At that time we need configurable
message templates, which can be called from anywhere in the code
(along with some dynamic data). Plus points for storing the
template in database, as we can easily provide a GUI for modifying
'em.

This is one of the thousands of ways of accomplishing it.

<script src="https://gist.github.com/841051.js?file=template.rb"></script>

Here is an example of the GUI -



![Template\_1](/images/configurable-message-templates-in-rails/template_1.png)


