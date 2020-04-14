# Kirby 3 Page Memcached

![Release](https://flat.badgen.net/packagist/v/bnomei/kirby3-page-memcached?color=ae81ff)
![Downloads](https://flat.badgen.net/packagist/dt/bnomei/kirby3-page-memcached?color=272822)
[![Build Status](https://flat.badgen.net/travis/bnomei/kirby3-page-memcached)](https://travis-ci.com/bnomei/kirby3-page-memcached)
[![Coverage Status](https://flat.badgen.net/coveralls/c/github/bnomei/kirby3-page-memcached)](https://coveralls.io/github/bnomei/kirby3-page-memcached) 
[![Maintainability](https://flat.badgen.net/codeclimate/maintainability/bnomei/kirby3-page-memcached)](https://codeclimate.com/github/bnomei/kirby3-page-memcached) 
[![Twitter](https://flat.badgen.net/badge/twitter/bnomei?color=66d9ef)](https://twitter.com/bnomei)

Kirby 3 Plugin to cache the content file using the PHP Memcached extension

## Commercial Usage

This plugin is free (MIT license) but if you use it in a commercial project please consider to
- [make a donation 🍻](https://www.paypal.me/bnomei/5) or
- [buy me ☕](https://buymeacoff.ee/bnomei) or
- [buy a Kirby license using this affiliate link](https://a.paddle.com/v2/click/1129/35731?link=1170)

## Installation

- unzip [master.zip](https://github.com/bnomei/kirby3-page-memcached/archive/master.zip) as folder `site/plugins/kirby3-page-memcached` or
- `git submodule add https://github.com/bnomei/kirby3-page-memcached.git site/plugins/kirby3-page-memcached` or
- `composer require bnomei/kirby3-page-memcached`

### Usage

To use this plugin create [Page-Models](https://getkirby.com/docs/guide/templates/page-models) and extend the `\Bnomei\MemcachedPage` class. This will read and write a **copy** of your Content-File to and from Memcached.

**site/models/example.php**
```php
<?php

class ExamplePage extends \Bnomei\MemcachedPage
{
    // that's it. all done. 👍
}
```

> TIP: If you set Kirbys global debug option to `true` all cached Content-Files will be flushed.

## Performance, Limitations and Alternatives

How much and if you gain anything regarding performance depends on the hardware. But on most production servers reading data from RAM should be faster than reading files from SSD disks.

| Defaults for | Memcached | APCu | Redis |
|----|----|----|----|
| max memory size | 64MB | 32MB | 0 (none) |
| size of key/value pair | 1MB | 4MB | 512MB |

The [Redis Cachedriver Plugin](https://github.com/bnomei/kirby3-redis-cachedriver) has a `RedisPage` class that works pretty much like the `MemcachedPage` class but uses Redis.

## Settings

| bnomei.page-memcached.            | Default        | Description               |            
|---------------------------|----------------|---------------------------|
| host | `127.0.0.1` |  |
| port | `6379` |  |
| prefix | `page-memcached` |  |

## Dependencies

- PHP Memcached extentsion and class

## Disclaimer

This plugin is provided "as is" with no guarantee. Use it at your own risk and always test it yourself before using it in a production environment. If you find any issues, please [create a new issue](https://github.com/bnomei/kirby3-page-memcached/issues/new).

## License

[MIT](https://opensource.org/licenses/MIT)

It is discouraged to use this plugin in any project that promotes racism, sexism, homophobia, animal abuse, violence or any other form of hate speech.