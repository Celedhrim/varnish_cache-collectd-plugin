varnish_cache-collectd-plugin
=============================

A varnish plugin for collectd using python plugin.
It use **varnishstat** XML output.

Compatibility:  varnish 3.x and 4.x

Install
-------

1. Put **varnish_cache.py** and **getsigchld.py** in a python plugin directory (/usr/share/collectd/python)
2. Configure the plugin
3. Restart collectd

Configuration
-------------
Add the following to your collectd config **or** use the included varnish_cache.conf

```
<Plugin python>
  ModulePath "/usr/share/collectd/python"
  LogTraces true
  Interactive true
  Import "varnish_cache"
	Import "getsigchld"

  <Module varnish_cache>
   Varnishstats "/usr/bin/varnishstat"
   Verbose false
   Varnishver "4"
  </Module>
</Plugin>

```
**Varnishver** takes 3 or 4 , if nothing , 4 is default
