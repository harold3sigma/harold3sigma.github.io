---
author: jagira
date: '2010-06-26 11:55:00'
layout: post
slug: reddit-api-with-ruby-on-rails
status: publish
title: Reddit API with Ruby on Rails
tags:
- programming
- ruby
---

** This post is old!!! Checkout [Reddit's dev site](http://www.reddit.com/dev/api) for detailed API docs.**

Reddit is social news site which is quite popular among geeks.
Reddit provides an API which allows third party apps to access
stories, votes, comments etc. Reddit team is also developing API
that allows application to post data to Reddit. Using Reddit's API
in RoR is a two step process.

**Step 1: Install JSON gem**

<script src="https://gist.github.com/454006.js?file=install_json_gem.sh"></script>

Reddit provides response in JSON and XML/RSS formats. I personally
prefer JSON over XML because it is easier to read, lighter and
faster to transfer than XML. To deserialize JSON data you will need
the JSON gem.

 

**Step 2: Begin Hacking**

<script src="https://gist.github.com/453997.js?file=Reddit_API.rb"></script>

The code sends a request to the API url, deserializes the response
using JSON gem and the returns a hash.

Following is a part of such hash. You can easily access the values
like a regular hash.

**PS**-Make sure that:

-   You do not make more than two request per second.
-   Pages are cached for 30 seconds. So do not put unnecessary load
    on servers by hitting the same page frequently.
-   Reddit provides 25 stories per page and it offers approx. 40
    pages. So do not make more than 40 requests in a go.

\=\> Visit [Reddit Code](http://code.reddit.com) for more details.

 



