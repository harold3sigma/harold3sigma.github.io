---
author: jagira
date: '2011-06-15 08:06:00'
layout: post
slug: mysql-too-many-connections-error
status: publish
title: MySQL "Too many connections" Error
wordpress_id: '27'
tags:
- devops
- programming
- mysql
---

"Too many connections" error means that all available connections
are in use by other clients. The number of connections permitted is
controlled by **max\_connections** setting in */etc/my.cnf* file.

To fix this issue you can either increase the number of
max\_connections (*not recommended*) or analyze active processes
and kill them. Running this script will kill all active processes.

<script src="https://gist.github.com/1026670.js?file=mysql_connection_cleaner.rb"></script>


