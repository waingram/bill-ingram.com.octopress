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

``` bash
    sudo /etc/init.d/postgresql-8.4 stop
```

Or do it the proper way

``` bash
    sudo service postgresql-8.4 stop
```

Remove it from rc.d

``` bash
    sudo update-rc.d postgresql-8.4 remove
      update-rc.d: /etc/init.d/postgresql-8.4 exists during rc.d purge (use -f to force)
```

This time with force!

``` bash
    sudo update-rc.d -f postgresql-8.4 remove
      Removing any system startup links for /etc/init.d/postgresql-8.4 ...
        /etc/rc0.d/K19postgresql-8.4
        /etc/rc1.d/K19postgresql-8.4
        /etc/rc2.d/S19postgresql-8.4
        /etc/rc3.d/S19postgresql-8.4
        /etc/rc4.d/S19postgresql-8.4
        /etc/rc5.d/S19postgresql-8.4
        /etc/rc6.d/K19postgresql-8.4
```

That's it.
