Xdebug PHP-app on Docker Host
=============================

References
----------

+ https://ccpalettes.wordpress.com/2013/06/03/remote-debugging-php-with-vim-and-xdebug/
+ https://gist.github.com/chadrien/c90927ec2d160ffea9c4
+ https://forums.docker.com/t/ip-address-for-xdebug/10460

Alias to local loopback
-----------------------

### On macOS

Make an alias for local loopback address `lo0` as `10.254.254.254` with

```
sudo ifconfig lo0 alias 10.254.254.254

```

### On Linux

Make an alias for local loopback address `lo:0` as `10.254.254.254` with

```
sudo ifconfig lo:0 10.254.254.254
```

Vim
---

[joonty/vdebug](https://github.com/joonty/vdebug) requires Python-enabled Vim, which can be built with configure option `--enable-pythoninterp`.


Before starting a debugging session, configure vdebug with commands:

```
:let g:vdebug_options = {}
```

```
:let g:vdebug_options['port'] = 9000
```

```
:let g:vdebug_options['path_maps'] = { '/public_html': '/your/local/path/to/php-fpm-xdebug/public_html' }
```

and open debuggin URL with query `?XDEBUG_SESSION_START=1`.

You can always check your vdebug configurations with:

```
:echo g:vdebug_options
```

### How to use vdebug

See https://github.com/joonty/vdebug#quick-guide
