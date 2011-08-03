---
layout: post
title: Removing a service from all run levels on Ubuntu 10.04
summary: The default installation of PostgreSQL starts automatically. Here's how to stop it. 
date: 2011-05-10
comments: true
categories: [Linux, svn, tutorials]
sharing: true
author: Bill Ingram
---

If postgres is running, stop it

<code>sudo /etc/init.d/postgresql-8.4 stop</code>

Or do it the proper way

<code>sudo service postgresql-8.4 stop</code>

Remove it from rc.d

<pre><code>sudo update-rc.d postgresql-8.4 remove
  update-rc.d: /etc/init.d/postgresql-8.4 exists during rc.d purge (use -f to force)
</code></pre>

This time with force!

<pre><code>sudo update-rc.d -f postgresql-8.4 remove
  Removing any system startup links for /etc/init.d/postgresql-8.4 ...
    /etc/rc0.d/K19postgresql-8.4
    /etc/rc1.d/K19postgresql-8.4
    /etc/rc2.d/S19postgresql-8.4
    /etc/rc3.d/S19postgresql-8.4
    /etc/rc4.d/S19postgresql-8.4
    /etc/rc5.d/S19postgresql-8.4
    /etc/rc6.d/K19postgresql-8.4
</code></pre>

That's it.
