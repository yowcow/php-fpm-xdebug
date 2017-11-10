Xdebug PHP-app on Docker Host
=============================

References
----------

+ https://ccpalettes.wordpress.com/2013/06/03/remote-debugging-php-with-vim-and-xdebug/
+ https://gist.github.com/chadrien/c90927ec2d160ffea9c4
+ https://forums.docker.com/t/ip-address-for-xdebug/10460

Alias lo0
---------

Make an alias for local loopback address `lo0` as `10.254.254.254` with

```
sudo ifconfig lo0 alias 10.254.254.254

```

and configure Xdebug to accept DBGP debugger connection from `10.254.254.254` as

```
xdebug.remote_host=10.254.254.254
```

Vim
---

[joonty/vdebug](https://github.com/joonty/vdebug) requires Python-enabled Vim, which can be built with configure option `--enable-pythoninterp`.


joonty/vdebug
-------------

See https://github.com/joonty/vdebug#quick-guide
