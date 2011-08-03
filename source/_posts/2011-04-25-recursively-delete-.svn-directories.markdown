---
layout: post
title: Recursively delete .svn directories
summary: A useful example of Bash command substitution. 
date: 2011-04-25
comments: true
catagories: [Linux, svn, tutorials]
sharing: true
author: Bill Ingram
---

Finding all the .svn directories is easy

<pre><code>$ find . -type d -name .svn
./.svn
./sourceA/.svn
./sourceB/.svn
./sourceB/module/.svn
./sourceC/.svn
</code></pre>

Now use command substitution with @rm -rf@. 

<code>rm -rf `find . -type d -name .svn`</code>

Note the use of the _backtick_ symbol (located under the ~ on the English keyboard)&mdash;that is not a single quote.
