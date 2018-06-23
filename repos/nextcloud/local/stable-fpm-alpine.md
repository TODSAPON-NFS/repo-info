# `nextcloud:13.0.4-fpm-alpine`

## Docker Metadata

- Image ID: `sha256:0528ea18a6363b825db95ce19d4ef2fe8a7320a22b9d165e928e5d7f14c9d8b2`
- Created: `2018-06-21T01:36:06.773318036Z`
- Virtual Size: ~ 275.37 Mb  
  (total size of all layers on-disk)
- Arch: `linux`/`amd64`
- Entrypoint: `["/entrypoint.sh"]`
- Command: `["php-fpm"]`
- Environment:
  - `PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin`
  - `PHPIZE_DEPS=autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pkgconf 		re2c`
  - `PHP_INI_DIR=/usr/local/etc/php`
  - `PHP_EXTRA_CONFIGURE_ARGS=--enable-fpm --with-fpm-user=www-data --with-fpm-group=www-data --disable-cgi`
  - `PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2`
  - `PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2`
  - `PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie`
  - `GPG_KEYS=A917B1ECDA84AEC2B568FED6F50ABC807BD5DCD0 528995BFEDFBA7191D46839EF9BA0ADA31CBD89E 1729F83938DA44E27BA0F4D3DBDB397470D12172`
  - `PHP_VERSION=7.1.18`
  - `PHP_URL=https://secure.php.net/get/php-7.1.18.tar.xz/from/this/mirror`
  - `PHP_ASC_URL=https://secure.php.net/get/php-7.1.18.tar.xz.asc/from/this/mirror`
  - `PHP_SHA256=8bd91cea072ea5b368cc9b4533a1a683eb426abdacbf024bb6ffa9b799cd3b01`
  - `PHP_MD5=`
  - `NEXTCLOUD_VERSION=13.0.4`
