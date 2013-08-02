zf-autocomplete
===============

This project is intended to auto-complete zftool providers through bash

**Zftool** is a pretty nifty feature from **Zend Framework**, however It's pretty tiring to remember all commands.

Using bash I've got a bunch of custom providers, and for that I have to remember all the commands or review them every time, so It's missing a killer feature which is the bash command auto-completion.

Installation
------------
**Clone it.**

Then move to bash_autocompletion

<code>sudo mv zf-autocomplete/zf /etc/bash_completion.d/</code>

I you want to run it immediately in the same opened shell you can do the following command
<code>. /etc/bash_completion.d/zf</code>

It will automatically available in any new shell.

Custom Providers and Caching
----------------------------

In case you are wondering, I've got many projects with many custom providers, will it **auto-complete** them?

The answer is **YES**, and it fetches the providers per directory basis. Since the fetching and filtering is a pretty heavy process, it caches the auto-completed options in /tmp/ so that it will only be slow the first time, and then it's going to be blazing fast.

Flush / Clear Cache
-----------------
Execute the following on the same directory to clear cache on that directory:

<code>rm "/tmp/"\`pwd | sed -e 's:/:_:g'\`"_actions" && rm "/tmp/"\`pwd | sed -e 's:/:_:g'\`"_providers"</code>
