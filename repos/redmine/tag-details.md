<!-- THIS FILE IS GENERATED VIA './update-remote.sh' -->

# Tags of `redmine`

-	[`redmine:3`](#redmine3)
-	[`redmine:3.3`](#redmine33)
-	[`redmine:3.3.8`](#redmine338)
-	[`redmine:3.3.8-passenger`](#redmine338-passenger)
-	[`redmine:3.3-passenger`](#redmine33-passenger)
-	[`redmine:3.4`](#redmine34)
-	[`redmine:3.4.6`](#redmine346)
-	[`redmine:3.4.6-passenger`](#redmine346-passenger)
-	[`redmine:3.4-passenger`](#redmine34-passenger)
-	[`redmine:3-passenger`](#redmine3-passenger)
-	[`redmine:latest`](#redminelatest)
-	[`redmine:passenger`](#redminepassenger)

## `redmine:3`

```console
$ docker pull redmine@sha256:7439dde0eae47d823c35e7f2e4c47d7cbb8b55dbf29844a2579fbd982421d3d3
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm variant v5
	-	linux; arm variant v7
	-	linux; arm64 variant v8
	-	linux; 386
	-	linux; ppc64le
	-	linux; s390x

### `redmine:3` - linux; amd64

```console
$ docker pull redmine@sha256:8dce5627271a3f21cd6ce5a3a29c6fbc11fcc99a0ca69d6e6e5882d8ecf4f196
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **250.7 MB (250669098 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:ebd79f5f9bc1c650b0f487dec3b167164c2c36f649ba15d25dbde5ddaae76fe0`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["rails","server","-b","0.0.0.0"]`

```dockerfile
# Sat, 28 Apr 2018 06:44:15 GMT
ADD file:3e6141c0c9cb74b14a281eb3ab7aaf162a625733e652c3948b323bb2ec8b4343 in / 
# Sat, 28 Apr 2018 06:44:16 GMT
CMD ["bash"]
# Sun, 29 Apr 2018 16:52:40 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Sun, 29 Apr 2018 16:52:41 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Sun, 29 Apr 2018 16:52:42 GMT
ENV RUBY_MAJOR=2.4
# Sun, 29 Apr 2018 16:52:42 GMT
ENV RUBY_VERSION=2.4.4
# Sun, 29 Apr 2018 16:52:42 GMT
ENV RUBY_DOWNLOAD_SHA256=1d0034071d675193ca769f64c91827e5f54cb3a7962316a41d5217c7bc6949f0
# Thu, 24 May 2018 01:25:52 GMT
ENV RUBYGEMS_VERSION=2.7.7
# Thu, 24 May 2018 01:25:52 GMT
ENV BUNDLER_VERSION=1.16.2
# Thu, 24 May 2018 01:29:14 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		dpkg-dev 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 		xz-utils 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& dpkg-query --show --showformat '${package}\n' 		| grep -P '^libreadline\d+$' 		| xargs apt-mark manual 	&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force 	&& rm -r /root/.gem/
# Thu, 24 May 2018 01:29:14 GMT
ENV GEM_HOME=/usr/local/bundle
# Thu, 24 May 2018 21:08:01 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Thu, 24 May 2018 21:08:02 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/bundle/gems/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Thu, 24 May 2018 21:08:02 GMT
RUN mkdir -p "$GEM_HOME" && chmod 777 "$GEM_HOME"
# Thu, 24 May 2018 21:08:03 GMT
CMD ["irb"]
# Fri, 25 May 2018 22:37:54 GMT
RUN groupadd -r redmine && useradd -r -g redmine redmine
# Fri, 25 May 2018 22:38:14 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		wget 	&& rm -rf /var/lib/apt/lists/*
# Fri, 25 May 2018 22:38:14 GMT
ENV GOSU_VERSION=1.10
# Fri, 25 May 2018 22:38:18 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Fri, 25 May 2018 22:38:18 GMT
ENV TINI_VERSION=v0.16.1
# Fri, 25 May 2018 22:38:20 GMT
RUN set -x 	&& wget -O /usr/local/bin/tini "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/tini.asc "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5 	&& gpg --batch --verify /usr/local/bin/tini.asc /usr/local/bin/tini 	&& rm -r "$GNUPGHOME" /usr/local/bin/tini.asc 	&& chmod +x /usr/local/bin/tini 	&& tini -h
# Wed, 20 Jun 2018 21:28:18 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		imagemagick 		mercurial 		openssh-client 		subversion 	&& rm -rf /var/lib/apt/lists/*
# Wed, 20 Jun 2018 21:28:18 GMT
ENV RAILS_ENV=production
# Wed, 20 Jun 2018 21:28:19 GMT
WORKDIR /usr/src/redmine
# Wed, 20 Jun 2018 21:28:19 GMT
ENV REDMINE_VERSION=3.4.6
# Wed, 20 Jun 2018 21:28:19 GMT
ENV REDMINE_DOWNLOAD_MD5=5f4993446ecf25782f469763c0d32ea1
# Wed, 20 Jun 2018 21:28:23 GMT
RUN wget -O redmine.tar.gz "https://www.redmine.org/releases/redmine-${REDMINE_VERSION}.tar.gz" 	&& echo "$REDMINE_DOWNLOAD_MD5 redmine.tar.gz" | md5sum -c - 	&& tar -xvf redmine.tar.gz --strip-components=1 	&& rm redmine.tar.gz files/delete.me log/delete.me 	&& mkdir -p tmp/pdf public/plugin_assets 	&& chown -R redmine:redmine ./
# Wed, 20 Jun 2018 21:31:54 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		freetds-dev 		gcc 		libmagickcore-dev 		libmagickwand-dev 		libmysqlclient-dev 		libpq-dev 		libsqlite3-dev 		make 		patch 	; 	rm -rf /var/lib/apt/lists/*; 		bundle install --without development test; 	for adapter in mysql2 postgresql sqlserver sqlite3; do 		echo "$RAILS_ENV:" > ./config/database.yml; 		echo "  adapter: $adapter" >> ./config/database.yml; 		bundle install --without development test; 		cp Gemfile.lock "Gemfile.lock.${adapter}"; 	done; 	rm ./config/database.yml; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| grep -v '^/usr/local/' 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false
# Wed, 20 Jun 2018 21:31:54 GMT
VOLUME [/usr/src/redmine/files]
# Wed, 20 Jun 2018 21:31:54 GMT
COPY file:8064eeba1336402e59165b07c73d0734f58aa7e83e3c0a42b6888098f2e2c11d in / 
# Wed, 20 Jun 2018 21:31:55 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Wed, 20 Jun 2018 21:31:55 GMT
EXPOSE 3000/tcp
# Wed, 20 Jun 2018 21:31:55 GMT
CMD ["rails" "server" "-b" "0.0.0.0"]
```

-	Layers:
	-	`sha256:3d77ce4481b119f00e53bee9b4a443469c42c224db954ddaa2e6b74cd73cd5d0`  
		Last Modified: Sat, 28 Apr 2018 08:24:47 GMT  
		Size: 54.3 MB (54262566 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:05a78650ca91970038096c478f5bc7b8155cf0226db13c86ccf40e0e476e23d5`  
		Last Modified: Sun, 29 Apr 2018 19:33:59 GMT  
		Size: 10.2 MB (10168983 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:860996a55f7fba99ae60e7be5fc25d885d982031d74467b9bcfc84f96e72def6`  
		Last Modified: Sun, 29 Apr 2018 19:33:57 GMT  
		Size: 205.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0af7e9644f308307bcbf19ad9eea243ce5dd469c0211039f47b3120cabdfc99c`  
		Last Modified: Thu, 24 May 2018 02:02:57 GMT  
		Size: 21.3 MB (21305911 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3c2741f1d4c75227c788ea0d4f97b9d842c26908b326b7341255dc08df8c2ff0`  
		Last Modified: Thu, 24 May 2018 21:16:41 GMT  
		Size: 149.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:085bf055e4f7fca4100b86db549ca65dbd113d5633f293b7d60c64580e40fc9c`  
		Last Modified: Fri, 25 May 2018 22:53:00 GMT  
		Size: 2.1 KB (2100 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:02757c5b4f758477ace554b047238004f1ba80dd0253f13e4afde2cff60c8fe2`  
		Last Modified: Fri, 25 May 2018 22:53:02 GMT  
		Size: 13.0 MB (12967769 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0b812d52f0b76913f780e051066b0aec46d9f1a2bc758a19b4872c304bf83525`  
		Last Modified: Fri, 25 May 2018 22:52:57 GMT  
		Size: 500.7 KB (500671 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a1ee2b52aad93348e461129e48f8cb4e4cbc9418e7363ce6ed71b679ed0da25e`  
		Last Modified: Fri, 25 May 2018 22:52:58 GMT  
		Size: 8.5 KB (8506 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:50ec0628480d6092f4ac1c09226941258eaa856ae2b192f54b82351b8147c5a2`  
		Last Modified: Wed, 20 Jun 2018 21:49:29 GMT  
		Size: 59.7 MB (59702353 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d7d52a5fdbb89bea397274ff00985194056ee68db884b686daa2e63575fa3730`  
		Last Modified: Wed, 20 Jun 2018 21:49:09 GMT  
		Size: 140.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:079a05a37d0bc8ec6e3819f8806a9ff391a4c3ff38e3c35679acabccd7281ed1`  
		Last Modified: Wed, 20 Jun 2018 21:49:11 GMT  
		Size: 2.5 MB (2456917 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:828f67b9c47148252d063a4e719ca8ed0be6c8a2487a5ac84f2bade3fd5e83ae`  
		Last Modified: Wed, 20 Jun 2018 21:49:35 GMT  
		Size: 89.3 MB (89291037 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d4660d39964eb0750734643da738a9352ccb35da2e28172ac5340f00f0cd40ea`  
		Last Modified: Wed, 20 Jun 2018 21:49:09 GMT  
		Size: 1.8 KB (1791 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `redmine:3` - linux; arm variant v5

```console
$ docker pull redmine@sha256:6d3319e8e0caf66469e15cba6f9b18da2b9994eaae19de97012d1aa9bf8c0402
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **244.2 MB (244218136 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:6b0e3d8938719b59edef5744897ff446a575e4be6543a6de3b33e801b768a7fc`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["rails","server","-b","0.0.0.0"]`

```dockerfile
# Sat, 28 Apr 2018 08:49:23 GMT
ADD file:2d2cd360e66aeff5557c7e7117985a00d109278c3f456ee970afcc9a46483264 in / 
# Sat, 28 Apr 2018 08:49:23 GMT
CMD ["bash"]
# Sat, 28 Apr 2018 11:50:09 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Sat, 28 Apr 2018 11:50:10 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Sat, 28 Apr 2018 11:50:11 GMT
ENV RUBY_MAJOR=2.4
# Sat, 28 Apr 2018 11:50:11 GMT
ENV RUBY_VERSION=2.4.4
# Sat, 28 Apr 2018 11:50:11 GMT
ENV RUBY_DOWNLOAD_SHA256=1d0034071d675193ca769f64c91827e5f54cb3a7962316a41d5217c7bc6949f0
# Thu, 24 May 2018 10:56:19 GMT
ENV RUBYGEMS_VERSION=2.7.7
# Thu, 24 May 2018 10:56:19 GMT
ENV BUNDLER_VERSION=1.16.2
# Thu, 24 May 2018 11:02:19 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		dpkg-dev 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 		xz-utils 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& dpkg-query --show --showformat '${package}\n' 		| grep -P '^libreadline\d+$' 		| xargs apt-mark manual 	&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force 	&& rm -r /root/.gem/
# Thu, 24 May 2018 11:02:20 GMT
ENV GEM_HOME=/usr/local/bundle
# Fri, 25 May 2018 09:09:45 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Fri, 25 May 2018 09:09:45 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/bundle/gems/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 25 May 2018 09:09:46 GMT
RUN mkdir -p "$GEM_HOME" && chmod 777 "$GEM_HOME"
# Fri, 25 May 2018 09:09:47 GMT
CMD ["irb"]
# Sat, 26 May 2018 10:03:35 GMT
RUN groupadd -r redmine && useradd -r -g redmine redmine
# Sat, 26 May 2018 10:04:04 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		wget 	&& rm -rf /var/lib/apt/lists/*
# Sat, 26 May 2018 10:04:04 GMT
ENV GOSU_VERSION=1.10
# Sat, 26 May 2018 10:04:06 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Sat, 26 May 2018 10:04:06 GMT
ENV TINI_VERSION=v0.16.1
# Sat, 26 May 2018 10:04:08 GMT
RUN set -x 	&& wget -O /usr/local/bin/tini "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/tini.asc "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5 	&& gpg --batch --verify /usr/local/bin/tini.asc /usr/local/bin/tini 	&& rm -r "$GNUPGHOME" /usr/local/bin/tini.asc 	&& chmod +x /usr/local/bin/tini 	&& tini -h
# Thu, 21 Jun 2018 09:33:55 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		imagemagick 		mercurial 		openssh-client 		subversion 	&& rm -rf /var/lib/apt/lists/*
# Thu, 21 Jun 2018 09:33:55 GMT
ENV RAILS_ENV=production
# Thu, 21 Jun 2018 09:33:56 GMT
WORKDIR /usr/src/redmine
# Thu, 21 Jun 2018 09:33:56 GMT
ENV REDMINE_VERSION=3.4.6
# Thu, 21 Jun 2018 09:33:56 GMT
ENV REDMINE_DOWNLOAD_MD5=5f4993446ecf25782f469763c0d32ea1
# Thu, 21 Jun 2018 09:34:00 GMT
RUN wget -O redmine.tar.gz "https://www.redmine.org/releases/redmine-${REDMINE_VERSION}.tar.gz" 	&& echo "$REDMINE_DOWNLOAD_MD5 redmine.tar.gz" | md5sum -c - 	&& tar -xvf redmine.tar.gz --strip-components=1 	&& rm redmine.tar.gz files/delete.me log/delete.me 	&& mkdir -p tmp/pdf public/plugin_assets 	&& chown -R redmine:redmine ./
# Thu, 21 Jun 2018 09:40:16 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		freetds-dev 		gcc 		libmagickcore-dev 		libmagickwand-dev 		libmysqlclient-dev 		libpq-dev 		libsqlite3-dev 		make 		patch 	; 	rm -rf /var/lib/apt/lists/*; 		bundle install --without development test; 	for adapter in mysql2 postgresql sqlserver sqlite3; do 		echo "$RAILS_ENV:" > ./config/database.yml; 		echo "  adapter: $adapter" >> ./config/database.yml; 		bundle install --without development test; 		cp Gemfile.lock "Gemfile.lock.${adapter}"; 	done; 	rm ./config/database.yml; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| grep -v '^/usr/local/' 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false
# Thu, 21 Jun 2018 09:40:17 GMT
VOLUME [/usr/src/redmine/files]
# Thu, 21 Jun 2018 09:40:17 GMT
COPY file:8064eeba1336402e59165b07c73d0734f58aa7e83e3c0a42b6888098f2e2c11d in / 
# Thu, 21 Jun 2018 09:40:17 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Thu, 21 Jun 2018 09:40:17 GMT
EXPOSE 3000/tcp
# Thu, 21 Jun 2018 09:40:18 GMT
CMD ["rails" "server" "-b" "0.0.0.0"]
```

-	Layers:
	-	`sha256:81fc0826192f72abe617753d378af4047dbce89faf17cdab9166877006a25d8e`  
		Last Modified: Sat, 28 Apr 2018 08:57:10 GMT  
		Size: 52.5 MB (52456037 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2119f18fa6f270436c891e0c459923ae24657bf4a8be20cfcfe964e7aa64b7b2`  
		Last Modified: Sat, 28 Apr 2018 12:31:30 GMT  
		Size: 9.1 MB (9119888 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:51757db9404a98c26c96cb6b65e8c7893c1e1b5ea9774a5786abe9ec88468cf3`  
		Last Modified: Sat, 28 Apr 2018 12:31:26 GMT  
		Size: 206.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:09fe38be652b02d310bce0a19598fe366080a17713f114eeb33355e15f6bf8c0`  
		Last Modified: Thu, 24 May 2018 11:29:31 GMT  
		Size: 21.1 MB (21074760 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:63fc7f9b6584b1727a86e7d2130c3f4129978990791d89d6af0f9950997cc782`  
		Last Modified: Fri, 25 May 2018 09:17:51 GMT  
		Size: 182.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bdbf4bf93be2e977124205e4f60ae3ba2a2f880c269a494237a056a419343587`  
		Last Modified: Sat, 26 May 2018 10:18:09 GMT  
		Size: 2.1 KB (2090 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:98b6a7f079c3c2475a4ae64a2f970ab18867099384ac59e88b28b14c37d777fc`  
		Last Modified: Sat, 26 May 2018 10:18:11 GMT  
		Size: 12.8 MB (12772572 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:33fbc82bebefed415e0d99d95c2199ccefd11254cfbefe0cb44e5c4235a80dbc`  
		Last Modified: Sat, 26 May 2018 10:18:06 GMT  
		Size: 491.1 KB (491125 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:494ed27bef31be226f9bb0b7dde7a3de53fee37d4a9defca95c65999a45bf288`  
		Last Modified: Sat, 26 May 2018 10:18:06 GMT  
		Size: 7.8 KB (7850 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:260011ea13c12e7f76c6ef3f3b6ac329067d5d62b1c3ea2e1438fc4d24c6e9f2`  
		Last Modified: Thu, 21 Jun 2018 09:46:58 GMT  
		Size: 57.1 MB (57055867 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7682be80ee6471502bcde4c8a3d03401fe0f247174899f7a298ea324b24bbaf8`  
		Last Modified: Thu, 21 Jun 2018 09:46:39 GMT  
		Size: 172.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e64810335b2932687826690900537543be72f782fbeb739f26c18c27c3f1a048`  
		Last Modified: Thu, 21 Jun 2018 09:46:41 GMT  
		Size: 2.5 MB (2457560 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:12da0e4bca312d2c2db7b5c9dc56916f4b56b158b309d62ae947b273fd04b8db`  
		Last Modified: Thu, 21 Jun 2018 09:47:03 GMT  
		Size: 88.8 MB (88778036 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b0398911b75ac4341523e8856acb1f5668b263bc57152d9ec5abda35b5ee15bd`  
		Last Modified: Thu, 21 Jun 2018 09:46:40 GMT  
		Size: 1.8 KB (1791 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `redmine:3` - linux; arm variant v7

```console
$ docker pull redmine@sha256:df7144a1137742adc5e4e11125da5e4d18e517fe491950489f2f97452b2522bf
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **238.4 MB (238431615 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:f661101282a8e3e492241307b1e3a098dbc6f66588f65c554e6267e3fa781492`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["rails","server","-b","0.0.0.0"]`

```dockerfile
# Sat, 28 Apr 2018 11:59:05 GMT
ADD file:4e9c283075c120ce66f83bf541b0aeaa8a46f74c21d38e4ab1578e7f1b892823 in / 
# Sat, 28 Apr 2018 11:59:05 GMT
CMD ["bash"]
# Sat, 28 Apr 2018 15:40:52 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Sat, 28 Apr 2018 15:40:56 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Sat, 28 Apr 2018 15:40:56 GMT
ENV RUBY_MAJOR=2.4
# Sat, 28 Apr 2018 15:40:57 GMT
ENV RUBY_VERSION=2.4.4
# Sat, 28 Apr 2018 15:40:57 GMT
ENV RUBY_DOWNLOAD_SHA256=1d0034071d675193ca769f64c91827e5f54cb3a7962316a41d5217c7bc6949f0
# Thu, 24 May 2018 13:13:30 GMT
ENV RUBYGEMS_VERSION=2.7.7
# Thu, 24 May 2018 13:13:31 GMT
ENV BUNDLER_VERSION=1.16.2
# Thu, 24 May 2018 13:18:52 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		dpkg-dev 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 		xz-utils 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& dpkg-query --show --showformat '${package}\n' 		| grep -P '^libreadline\d+$' 		| xargs apt-mark manual 	&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force 	&& rm -r /root/.gem/
# Thu, 24 May 2018 13:18:53 GMT
ENV GEM_HOME=/usr/local/bundle
# Fri, 25 May 2018 12:27:41 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Fri, 25 May 2018 12:27:42 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/bundle/gems/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 25 May 2018 12:27:43 GMT
RUN mkdir -p "$GEM_HOME" && chmod 777 "$GEM_HOME"
# Fri, 25 May 2018 12:27:43 GMT
CMD ["irb"]
# Sat, 26 May 2018 12:23:55 GMT
RUN groupadd -r redmine && useradd -r -g redmine redmine
# Sat, 26 May 2018 12:24:22 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		wget 	&& rm -rf /var/lib/apt/lists/*
# Sat, 26 May 2018 12:24:22 GMT
ENV GOSU_VERSION=1.10
# Sat, 26 May 2018 12:24:24 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Sat, 26 May 2018 12:24:24 GMT
ENV TINI_VERSION=v0.16.1
# Sat, 26 May 2018 12:24:26 GMT
RUN set -x 	&& wget -O /usr/local/bin/tini "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/tini.asc "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5 	&& gpg --batch --verify /usr/local/bin/tini.asc /usr/local/bin/tini 	&& rm -r "$GNUPGHOME" /usr/local/bin/tini.asc 	&& chmod +x /usr/local/bin/tini 	&& tini -h
# Thu, 21 Jun 2018 12:06:34 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		imagemagick 		mercurial 		openssh-client 		subversion 	&& rm -rf /var/lib/apt/lists/*
# Thu, 21 Jun 2018 12:06:34 GMT
ENV RAILS_ENV=production
# Thu, 21 Jun 2018 12:06:34 GMT
WORKDIR /usr/src/redmine
# Thu, 21 Jun 2018 12:06:35 GMT
ENV REDMINE_VERSION=3.4.6
# Thu, 21 Jun 2018 12:06:35 GMT
ENV REDMINE_DOWNLOAD_MD5=5f4993446ecf25782f469763c0d32ea1
# Thu, 21 Jun 2018 12:06:39 GMT
RUN wget -O redmine.tar.gz "https://www.redmine.org/releases/redmine-${REDMINE_VERSION}.tar.gz" 	&& echo "$REDMINE_DOWNLOAD_MD5 redmine.tar.gz" | md5sum -c - 	&& tar -xvf redmine.tar.gz --strip-components=1 	&& rm redmine.tar.gz files/delete.me log/delete.me 	&& mkdir -p tmp/pdf public/plugin_assets 	&& chown -R redmine:redmine ./
# Thu, 21 Jun 2018 12:12:24 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		freetds-dev 		gcc 		libmagickcore-dev 		libmagickwand-dev 		libmysqlclient-dev 		libpq-dev 		libsqlite3-dev 		make 		patch 	; 	rm -rf /var/lib/apt/lists/*; 		bundle install --without development test; 	for adapter in mysql2 postgresql sqlserver sqlite3; do 		echo "$RAILS_ENV:" > ./config/database.yml; 		echo "  adapter: $adapter" >> ./config/database.yml; 		bundle install --without development test; 		cp Gemfile.lock "Gemfile.lock.${adapter}"; 	done; 	rm ./config/database.yml; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| grep -v '^/usr/local/' 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false
# Thu, 21 Jun 2018 12:12:25 GMT
VOLUME [/usr/src/redmine/files]
# Thu, 21 Jun 2018 12:12:25 GMT
COPY file:8064eeba1336402e59165b07c73d0734f58aa7e83e3c0a42b6888098f2e2c11d in / 
# Thu, 21 Jun 2018 12:12:25 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Thu, 21 Jun 2018 12:12:26 GMT
EXPOSE 3000/tcp
# Thu, 21 Jun 2018 12:12:26 GMT
CMD ["rails" "server" "-b" "0.0.0.0"]
```

-	Layers:
	-	`sha256:5c478157e28e3c26a0209484edb518799e1c21863d4700579c010b7203e0537f`  
		Last Modified: Sat, 28 Apr 2018 12:10:24 GMT  
		Size: 50.2 MB (50195697 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:57cc82e3a61290e4bfc39b7ec615f84e7782d645852ff04b0f1077ba3a8d6c85`  
		Last Modified: Sat, 28 Apr 2018 16:21:20 GMT  
		Size: 8.8 MB (8777726 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e60d4b7c236d855ddd6a1f286ece09d909ea721b8959a806142de215e84ad242`  
		Last Modified: Sat, 28 Apr 2018 16:21:17 GMT  
		Size: 207.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fd714148500451500a2957112b77e7e1feb9b7fa3095266d84623a097aa9935b`  
		Last Modified: Thu, 24 May 2018 13:51:44 GMT  
		Size: 20.9 MB (20939873 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:15b699e7e8d225b3c8087b29914345882f41c75520d205595171039ab1e0c856`  
		Last Modified: Fri, 25 May 2018 12:40:08 GMT  
		Size: 182.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0e957186fb243adf5019585383bf19defaa1d82b4636998b537528235dd777f2`  
		Last Modified: Sat, 26 May 2018 12:37:45 GMT  
		Size: 2.1 KB (2092 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:11e22cb6dff3aef6e6185c86a85889793c9f7fff65d461c749557bc8884b9624`  
		Last Modified: Sat, 26 May 2018 12:37:50 GMT  
		Size: 12.6 MB (12629462 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9726b5b13c21e003fe07315e1e1f21db27480310aa0606a5699f7435f62801cf`  
		Last Modified: Sat, 26 May 2018 12:37:45 GMT  
		Size: 475.3 KB (475267 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3784a11f9e4def9da3250391267c9bcffd3edd695febdb607895c2fa1524e923`  
		Last Modified: Sat, 26 May 2018 12:37:44 GMT  
		Size: 7.3 KB (7313 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1374393c860f34b65841b3158be787bc2df985c718b0bd332c8d8c7428a83e52`  
		Last Modified: Thu, 21 Jun 2018 12:18:49 GMT  
		Size: 54.7 MB (54698588 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:42db57f6861effae6af53fac1d6db5790da8afb4d14f64a0f0f22aba5649080e`  
		Last Modified: Thu, 21 Jun 2018 12:18:32 GMT  
		Size: 172.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:590497ab77d278095f81c2e419971e26ef0d6483e14a0b97ed13f8ec94a76f83`  
		Last Modified: Thu, 21 Jun 2018 12:18:34 GMT  
		Size: 2.5 MB (2457572 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d3918493345313d19d0cbd4c26bd6142b71be53be71d3976bbd956e00a1c7da8`  
		Last Modified: Thu, 21 Jun 2018 12:18:57 GMT  
		Size: 88.2 MB (88245671 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e118f56902617fa8db9f49493a8d0039c3a90976f6506cf6df565557e09560af`  
		Last Modified: Thu, 21 Jun 2018 12:18:32 GMT  
		Size: 1.8 KB (1793 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `redmine:3` - linux; arm64 variant v8

```console
$ docker pull redmine@sha256:988df7496fea7b7cc53d5210dd1bd832b8d22cbf82fb0b9f6a7d61c366de95c4
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **243.2 MB (243226684 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:795f00ab797d1fb1e0e03e8ea4d2c01f3f953b9df56a7da35adfd390546f65a6`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["rails","server","-b","0.0.0.0"]`

```dockerfile
# Mon, 30 Apr 2018 23:21:38 GMT
ADD file:387c83918422a6546379c4d84818ca3949fcd63aec058da562b08c947a9ed571 in / 
# Mon, 30 Apr 2018 23:21:40 GMT
CMD ["bash"]
# Tue, 01 May 2018 08:41:36 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Tue, 01 May 2018 08:41:41 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Tue, 01 May 2018 08:41:42 GMT
ENV RUBY_MAJOR=2.4
# Tue, 01 May 2018 08:41:44 GMT
ENV RUBY_VERSION=2.4.4
# Tue, 01 May 2018 08:41:46 GMT
ENV RUBY_DOWNLOAD_SHA256=1d0034071d675193ca769f64c91827e5f54cb3a7962316a41d5217c7bc6949f0
# Fri, 25 May 2018 16:57:16 GMT
ENV RUBYGEMS_VERSION=2.7.7
# Fri, 25 May 2018 16:57:17 GMT
ENV BUNDLER_VERSION=1.16.2
# Fri, 25 May 2018 17:06:32 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		dpkg-dev 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 		xz-utils 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& dpkg-query --show --showformat '${package}\n' 		| grep -P '^libreadline\d+$' 		| xargs apt-mark manual 	&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force 	&& rm -r /root/.gem/
# Fri, 25 May 2018 17:06:33 GMT
ENV GEM_HOME=/usr/local/bundle
# Fri, 25 May 2018 17:06:34 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Fri, 25 May 2018 17:06:34 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/bundle/gems/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 25 May 2018 17:06:36 GMT
RUN mkdir -p "$GEM_HOME" && chmod 777 "$GEM_HOME"
# Fri, 25 May 2018 17:06:37 GMT
CMD ["irb"]
# Fri, 25 May 2018 21:43:13 GMT
RUN groupadd -r redmine && useradd -r -g redmine redmine
# Fri, 25 May 2018 21:43:38 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		wget 	&& rm -rf /var/lib/apt/lists/*
# Fri, 25 May 2018 21:43:38 GMT
ENV GOSU_VERSION=1.10
# Fri, 25 May 2018 21:43:43 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Fri, 25 May 2018 21:43:44 GMT
ENV TINI_VERSION=v0.16.1
# Fri, 25 May 2018 21:43:46 GMT
RUN set -x 	&& wget -O /usr/local/bin/tini "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/tini.asc "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5 	&& gpg --batch --verify /usr/local/bin/tini.asc /usr/local/bin/tini 	&& rm -r "$GNUPGHOME" /usr/local/bin/tini.asc 	&& chmod +x /usr/local/bin/tini 	&& tini -h
# Thu, 21 Jun 2018 16:59:11 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		imagemagick 		mercurial 		openssh-client 		subversion 	&& rm -rf /var/lib/apt/lists/*
# Thu, 21 Jun 2018 16:59:12 GMT
ENV RAILS_ENV=production
# Thu, 21 Jun 2018 16:59:13 GMT
WORKDIR /usr/src/redmine
# Thu, 21 Jun 2018 16:59:13 GMT
ENV REDMINE_VERSION=3.4.6
# Thu, 21 Jun 2018 16:59:14 GMT
ENV REDMINE_DOWNLOAD_MD5=5f4993446ecf25782f469763c0d32ea1
# Thu, 21 Jun 2018 16:59:20 GMT
RUN wget -O redmine.tar.gz "https://www.redmine.org/releases/redmine-${REDMINE_VERSION}.tar.gz" 	&& echo "$REDMINE_DOWNLOAD_MD5 redmine.tar.gz" | md5sum -c - 	&& tar -xvf redmine.tar.gz --strip-components=1 	&& rm redmine.tar.gz files/delete.me log/delete.me 	&& mkdir -p tmp/pdf public/plugin_assets 	&& chown -R redmine:redmine ./
# Thu, 21 Jun 2018 17:12:12 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		freetds-dev 		gcc 		libmagickcore-dev 		libmagickwand-dev 		libmysqlclient-dev 		libpq-dev 		libsqlite3-dev 		make 		patch 	; 	rm -rf /var/lib/apt/lists/*; 		bundle install --without development test; 	for adapter in mysql2 postgresql sqlserver sqlite3; do 		echo "$RAILS_ENV:" > ./config/database.yml; 		echo "  adapter: $adapter" >> ./config/database.yml; 		bundle install --without development test; 		cp Gemfile.lock "Gemfile.lock.${adapter}"; 	done; 	rm ./config/database.yml; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| grep -v '^/usr/local/' 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false
# Thu, 21 Jun 2018 17:12:14 GMT
VOLUME [/usr/src/redmine/files]
# Thu, 21 Jun 2018 17:12:14 GMT
COPY file:8064eeba1336402e59165b07c73d0734f58aa7e83e3c0a42b6888098f2e2c11d in / 
# Thu, 21 Jun 2018 17:12:15 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Thu, 21 Jun 2018 17:12:16 GMT
EXPOSE 3000/tcp
# Thu, 21 Jun 2018 17:12:17 GMT
CMD ["rails" "server" "-b" "0.0.0.0"]
```

-	Layers:
	-	`sha256:363cfded2ef3921ef972c85cafc77cf16cdcfddfd49782ad4540cb73fd5e57a2`  
		Last Modified: Mon, 30 Apr 2018 23:41:06 GMT  
		Size: 51.4 MB (51446854 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6aeaeeebfa7e2a1e6c69a484a7648b6313aff4bf219767667e43bbfc42bb40d9`  
		Last Modified: Tue, 01 May 2018 09:53:45 GMT  
		Size: 9.3 MB (9343083 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3b78cb3f4882a2b3bf1ecb4fdbe1e145a3ddb80ce1fde62a33ada1beaf12daf8`  
		Last Modified: Tue, 01 May 2018 09:53:41 GMT  
		Size: 205.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:18547e3cbea8ccf1a7ca22515077049b202d0f12cac441573f4edf1f9b567209`  
		Last Modified: Fri, 25 May 2018 18:07:21 GMT  
		Size: 21.3 MB (21265153 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1d6d550606a490752c05952acf272ef8a1e4df8e3a8be58f37f50260160a5b11`  
		Last Modified: Fri, 25 May 2018 18:07:10 GMT  
		Size: 148.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:548893d753de4a74e5a64d26225a85691cfd2ad2b0546591161f46916ea1229f`  
		Last Modified: Fri, 25 May 2018 22:12:00 GMT  
		Size: 2.1 KB (2113 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a5ecd4fc430347071a2c164435746340e018f58d8037eabf8dd5665ad1b0dff6`  
		Last Modified: Fri, 25 May 2018 22:12:03 GMT  
		Size: 12.9 MB (12940690 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bfc6b9486743d7946d7922a4c47f0cc78876f91c3db011553f4f9a25a1dc96e2`  
		Last Modified: Fri, 25 May 2018 22:11:58 GMT  
		Size: 468.7 KB (468701 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e8f19d3b246e0490714656220e538767a6b0f47ae8f43c10cc32017687ae3114`  
		Last Modified: Fri, 25 May 2018 22:11:58 GMT  
		Size: 8.2 KB (8154 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:33f179dd0cce7b503211ff6d22a331d47169a234442ac5b0f6d11519eb3ead53`  
		Last Modified: Thu, 21 Jun 2018 17:27:27 GMT  
		Size: 56.2 MB (56166767 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b00c8c2de88468ac5d8b2af1848ffa502eded4adfd3a7e8e3859a57018eaace6`  
		Last Modified: Thu, 21 Jun 2018 17:27:04 GMT  
		Size: 140.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:95eb29922954e0efbb03fb3ca6512c8ce0d257303fc9a551e8d52455bef6d5b1`  
		Last Modified: Thu, 21 Jun 2018 17:27:07 GMT  
		Size: 2.5 MB (2456916 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f2bfa5dcbc83e5d3cd044dfbc3d81faa5b22a07684e60e5ca7cc0c8f4c76a57f`  
		Last Modified: Thu, 21 Jun 2018 17:27:35 GMT  
		Size: 89.1 MB (89125967 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:51f3ad7cc3086c71f467f0eee89ca821bc6f3aae7bd05ce85b8eb78d72e15a94`  
		Last Modified: Thu, 21 Jun 2018 17:27:04 GMT  
		Size: 1.8 KB (1793 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `redmine:3` - linux; 386

```console
$ docker pull redmine@sha256:d87c7c46bff353bc7e6f129b084607c93da5931f3d61a8ab52a1a2e6895bf371
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **253.9 MB (253912619 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:f17b65464fff83d872964798559dc27680b6902daaba36df7306c9fa0a810e9d`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["rails","server","-b","0.0.0.0"]`

```dockerfile
# Sat, 28 Apr 2018 10:39:32 GMT
ADD file:ce5174f2b2c155a2421fac3ff37a02d9551d5d79e31a541189bcfd2416a6903a in / 
# Sat, 28 Apr 2018 10:39:32 GMT
CMD ["bash"]
# Fri, 01 Jun 2018 14:56:41 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Fri, 01 Jun 2018 14:56:42 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Fri, 01 Jun 2018 14:56:42 GMT
ENV RUBY_MAJOR=2.4
# Fri, 01 Jun 2018 14:56:42 GMT
ENV RUBY_VERSION=2.4.4
# Fri, 01 Jun 2018 14:56:42 GMT
ENV RUBY_DOWNLOAD_SHA256=1d0034071d675193ca769f64c91827e5f54cb3a7962316a41d5217c7bc6949f0
# Fri, 01 Jun 2018 14:56:42 GMT
ENV RUBYGEMS_VERSION=2.7.7
# Fri, 01 Jun 2018 14:56:42 GMT
ENV BUNDLER_VERSION=1.16.2
# Fri, 01 Jun 2018 15:04:05 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		dpkg-dev 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 		xz-utils 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& dpkg-query --show --showformat '${package}\n' 		| grep -P '^libreadline\d+$' 		| xargs apt-mark manual 	&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force 	&& rm -r /root/.gem/
# Fri, 01 Jun 2018 15:04:06 GMT
ENV GEM_HOME=/usr/local/bundle
# Fri, 01 Jun 2018 15:04:06 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Fri, 01 Jun 2018 15:04:06 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/bundle/gems/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 01 Jun 2018 15:04:07 GMT
RUN mkdir -p "$GEM_HOME" && chmod 777 "$GEM_HOME"
# Fri, 01 Jun 2018 15:04:07 GMT
CMD ["irb"]
# Fri, 01 Jun 2018 17:09:55 GMT
RUN groupadd -r redmine && useradd -r -g redmine redmine
# Fri, 01 Jun 2018 17:10:49 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		wget 	&& rm -rf /var/lib/apt/lists/*
# Fri, 01 Jun 2018 17:10:49 GMT
ENV GOSU_VERSION=1.10
# Fri, 01 Jun 2018 17:10:56 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Fri, 01 Jun 2018 17:10:56 GMT
ENV TINI_VERSION=v0.16.1
# Fri, 01 Jun 2018 17:10:59 GMT
RUN set -x 	&& wget -O /usr/local/bin/tini "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/tini.asc "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5 	&& gpg --batch --verify /usr/local/bin/tini.asc /usr/local/bin/tini 	&& rm -r "$GNUPGHOME" /usr/local/bin/tini.asc 	&& chmod +x /usr/local/bin/tini 	&& tini -h
# Thu, 21 Jun 2018 11:00:37 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		imagemagick 		mercurial 		openssh-client 		subversion 	&& rm -rf /var/lib/apt/lists/*
# Thu, 21 Jun 2018 11:00:38 GMT
ENV RAILS_ENV=production
# Thu, 21 Jun 2018 11:00:38 GMT
WORKDIR /usr/src/redmine
# Thu, 21 Jun 2018 11:00:38 GMT
ENV REDMINE_VERSION=3.4.6
# Thu, 21 Jun 2018 11:00:39 GMT
ENV REDMINE_DOWNLOAD_MD5=5f4993446ecf25782f469763c0d32ea1
# Thu, 21 Jun 2018 11:00:43 GMT
RUN wget -O redmine.tar.gz "https://www.redmine.org/releases/redmine-${REDMINE_VERSION}.tar.gz" 	&& echo "$REDMINE_DOWNLOAD_MD5 redmine.tar.gz" | md5sum -c - 	&& tar -xvf redmine.tar.gz --strip-components=1 	&& rm redmine.tar.gz files/delete.me log/delete.me 	&& mkdir -p tmp/pdf public/plugin_assets 	&& chown -R redmine:redmine ./
# Thu, 21 Jun 2018 11:07:27 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		freetds-dev 		gcc 		libmagickcore-dev 		libmagickwand-dev 		libmysqlclient-dev 		libpq-dev 		libsqlite3-dev 		make 		patch 	; 	rm -rf /var/lib/apt/lists/*; 		bundle install --without development test; 	for adapter in mysql2 postgresql sqlserver sqlite3; do 		echo "$RAILS_ENV:" > ./config/database.yml; 		echo "  adapter: $adapter" >> ./config/database.yml; 		bundle install --without development test; 		cp Gemfile.lock "Gemfile.lock.${adapter}"; 	done; 	rm ./config/database.yml; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| grep -v '^/usr/local/' 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false
# Thu, 21 Jun 2018 11:07:28 GMT
VOLUME [/usr/src/redmine/files]
# Thu, 21 Jun 2018 11:07:35 GMT
COPY file:8064eeba1336402e59165b07c73d0734f58aa7e83e3c0a42b6888098f2e2c11d in / 
# Thu, 21 Jun 2018 11:07:36 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Thu, 21 Jun 2018 11:07:36 GMT
EXPOSE 3000/tcp
# Thu, 21 Jun 2018 11:07:36 GMT
CMD ["rails" "server" "-b" "0.0.0.0"]
```

-	Layers:
	-	`sha256:05b419d667f793c8c2edf0ff0aec14fc4d66733cdb89957ac89e8bfbeaddd0fa`  
		Last Modified: Sat, 28 Apr 2018 10:44:20 GMT  
		Size: 54.5 MB (54486782 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3d6891754f33e4c1f328ba0f4530fdb8383be81d86d518c6967565db3d8a7d3f`  
		Last Modified: Fri, 01 Jun 2018 15:49:54 GMT  
		Size: 14.9 MB (14942131 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:089cb9bb407565a3373144a74a72a2345d043f8423185a11fe236787bfc2d617`  
		Last Modified: Fri, 01 Jun 2018 15:49:47 GMT  
		Size: 208.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b853b205add0f75c6d80bbdfcfd40d09d2435262eb1076c603fd5a6ffff58a15`  
		Last Modified: Fri, 01 Jun 2018 15:49:56 GMT  
		Size: 20.3 MB (20303639 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7911295bc17916b28653d7cd6782d5eaede8fbbd7814f157a445829de1488cc8`  
		Last Modified: Fri, 01 Jun 2018 15:49:47 GMT  
		Size: 148.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2f80ba1db311f9d427a674563c28a8673d1b2941bcf25116f71c8446c382a3b4`  
		Last Modified: Fri, 01 Jun 2018 17:31:18 GMT  
		Size: 2.1 KB (2090 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ff801544c3611060c1d01382b678c4ae46af418e380369f5ebe1d34b0f29d77e`  
		Last Modified: Fri, 01 Jun 2018 17:31:27 GMT  
		Size: 13.1 MB (13103088 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a8e57a3fcd9a49a1c8880a39b935633a3041926c55a56be8bd38c07adff2c4fa`  
		Last Modified: Fri, 01 Jun 2018 17:31:16 GMT  
		Size: 480.6 KB (480563 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0351ff4ecba98d1064a87e597d3a72a277f456c7c8c5ca2c5d3232ee7d9ac7a5`  
		Last Modified: Fri, 01 Jun 2018 17:31:14 GMT  
		Size: 8.6 KB (8565 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a6451afdfb1e0e39ceba0ae2d333f8b7517af15e4c692a597d1b54293e304bb1`  
		Last Modified: Thu, 21 Jun 2018 11:15:18 GMT  
		Size: 60.6 MB (60580239 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bf645102966d197165f4e7e583a568f06ddf47daafd8fb4d473042543a2cac26`  
		Last Modified: Thu, 21 Jun 2018 11:14:48 GMT  
		Size: 140.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ce01371909c6db5cdb9d92de323d2973c0dd219f9f8daba9055a9dc8195ec003`  
		Last Modified: Thu, 21 Jun 2018 11:14:50 GMT  
		Size: 2.5 MB (2456909 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:95d4b6248a4676e50ab8bbfe182fb99d5dd0caff607308555d3f8d9147948743`  
		Last Modified: Thu, 21 Jun 2018 11:15:20 GMT  
		Size: 87.5 MB (87546324 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:114fe7ad48c3d506f86cfc90e19d21acbd0d6f6f8686ffd8c241234719076c80`  
		Last Modified: Thu, 21 Jun 2018 11:14:48 GMT  
		Size: 1.8 KB (1793 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `redmine:3` - linux; ppc64le

```console
$ docker pull redmine@sha256:907c86f110cb9245f282d9daeb30d2fef6fe5073bc1c78cea57bc0f4c745dc1a
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **249.9 MB (249907098 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:b0de66b8b9f108221b0d577f34253c4482d759cf811a688bfc94660b4c03cb28`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["rails","server","-b","0.0.0.0"]`

```dockerfile
# Sat, 28 Apr 2018 08:17:46 GMT
ADD file:6a4bd4ea54f669286e984ecf8178e1fa7c12c8b6fc0f96e4203ae7a6f99a2279 in / 
# Sat, 28 Apr 2018 08:17:47 GMT
CMD ["bash"]
# Sat, 28 Apr 2018 11:24:06 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Sat, 28 Apr 2018 11:24:08 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Sat, 28 Apr 2018 11:24:08 GMT
ENV RUBY_MAJOR=2.4
# Sat, 28 Apr 2018 11:24:08 GMT
ENV RUBY_VERSION=2.4.4
# Sat, 28 Apr 2018 11:24:09 GMT
ENV RUBY_DOWNLOAD_SHA256=1d0034071d675193ca769f64c91827e5f54cb3a7962316a41d5217c7bc6949f0
# Thu, 24 May 2018 10:50:48 GMT
ENV RUBYGEMS_VERSION=2.7.7
# Thu, 24 May 2018 10:50:50 GMT
ENV BUNDLER_VERSION=1.16.2
# Thu, 24 May 2018 10:58:50 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		dpkg-dev 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 		xz-utils 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& dpkg-query --show --showformat '${package}\n' 		| grep -P '^libreadline\d+$' 		| xargs apt-mark manual 	&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force 	&& rm -r /root/.gem/
# Thu, 24 May 2018 10:58:51 GMT
ENV GEM_HOME=/usr/local/bundle
# Fri, 25 May 2018 09:19:08 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Fri, 25 May 2018 09:19:09 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/bundle/gems/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 25 May 2018 09:19:10 GMT
RUN mkdir -p "$GEM_HOME" && chmod 777 "$GEM_HOME"
# Fri, 25 May 2018 09:19:11 GMT
CMD ["irb"]
# Sat, 26 May 2018 09:41:15 GMT
RUN groupadd -r redmine && useradd -r -g redmine redmine
# Sat, 26 May 2018 09:42:45 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		wget 	&& rm -rf /var/lib/apt/lists/*
# Sat, 26 May 2018 09:42:51 GMT
ENV GOSU_VERSION=1.10
# Sat, 26 May 2018 09:43:05 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Sat, 26 May 2018 09:43:11 GMT
ENV TINI_VERSION=v0.16.1
# Sat, 26 May 2018 09:43:19 GMT
RUN set -x 	&& wget -O /usr/local/bin/tini "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/tini.asc "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5 	&& gpg --batch --verify /usr/local/bin/tini.asc /usr/local/bin/tini 	&& rm -r "$GNUPGHOME" /usr/local/bin/tini.asc 	&& chmod +x /usr/local/bin/tini 	&& tini -h
# Thu, 21 Jun 2018 09:57:56 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		imagemagick 		mercurial 		openssh-client 		subversion 	&& rm -rf /var/lib/apt/lists/*
# Thu, 21 Jun 2018 09:57:57 GMT
ENV RAILS_ENV=production
# Thu, 21 Jun 2018 09:57:58 GMT
WORKDIR /usr/src/redmine
# Thu, 21 Jun 2018 09:57:58 GMT
ENV REDMINE_VERSION=3.4.6
# Thu, 21 Jun 2018 09:57:59 GMT
ENV REDMINE_DOWNLOAD_MD5=5f4993446ecf25782f469763c0d32ea1
# Thu, 21 Jun 2018 09:58:05 GMT
RUN wget -O redmine.tar.gz "https://www.redmine.org/releases/redmine-${REDMINE_VERSION}.tar.gz" 	&& echo "$REDMINE_DOWNLOAD_MD5 redmine.tar.gz" | md5sum -c - 	&& tar -xvf redmine.tar.gz --strip-components=1 	&& rm redmine.tar.gz files/delete.me log/delete.me 	&& mkdir -p tmp/pdf public/plugin_assets 	&& chown -R redmine:redmine ./
# Thu, 21 Jun 2018 10:09:09 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		freetds-dev 		gcc 		libmagickcore-dev 		libmagickwand-dev 		libmysqlclient-dev 		libpq-dev 		libsqlite3-dev 		make 		patch 	; 	rm -rf /var/lib/apt/lists/*; 		bundle install --without development test; 	for adapter in mysql2 postgresql sqlserver sqlite3; do 		echo "$RAILS_ENV:" > ./config/database.yml; 		echo "  adapter: $adapter" >> ./config/database.yml; 		bundle install --without development test; 		cp Gemfile.lock "Gemfile.lock.${adapter}"; 	done; 	rm ./config/database.yml; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| grep -v '^/usr/local/' 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false
# Thu, 21 Jun 2018 10:09:12 GMT
VOLUME [/usr/src/redmine/files]
# Thu, 21 Jun 2018 10:09:12 GMT
COPY file:8064eeba1336402e59165b07c73d0734f58aa7e83e3c0a42b6888098f2e2c11d in / 
# Thu, 21 Jun 2018 10:09:14 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Thu, 21 Jun 2018 10:09:15 GMT
EXPOSE 3000/tcp
# Thu, 21 Jun 2018 10:09:19 GMT
CMD ["rails" "server" "-b" "0.0.0.0"]
```

-	Layers:
	-	`sha256:2668401c9f940b1d6b03e5f0086fa248cb957610ef9a7c79983d2fb0707ec76c`  
		Last Modified: Sat, 28 Apr 2018 08:24:36 GMT  
		Size: 53.4 MB (53392811 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ab444779be019b7a69946ce8e93e0062d82eedfe747470714b266730847305b0`  
		Last Modified: Sat, 28 Apr 2018 12:15:08 GMT  
		Size: 10.1 MB (10137971 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b6bfab4f27e54de1711e2752ce393ce141c20aef64a8cd42d95a20585d28fa73`  
		Last Modified: Sat, 28 Apr 2018 12:15:04 GMT  
		Size: 207.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8b15968d0ad41cd76cb81ece13f4d2ca5a0d8d6e4579ae1e619f8ddd2ad295c2`  
		Last Modified: Thu, 24 May 2018 11:43:15 GMT  
		Size: 21.8 MB (21757239 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:351a7ed5b215a7bd4c196ac77237a20aec73a9a6665d2224deead4283218f7d6`  
		Last Modified: Fri, 25 May 2018 09:32:02 GMT  
		Size: 183.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6bd39d3e6422d52b16dfac40b0f9fd915fe70de5266ff6e1c6a545538a617171`  
		Last Modified: Sat, 26 May 2018 10:28:52 GMT  
		Size: 2.1 KB (2122 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b890c32c8a35b49718465b739aa29851ea5d09645363047bcfd2646d0c7e59d2`  
		Last Modified: Sat, 26 May 2018 10:28:53 GMT  
		Size: 13.1 MB (13113602 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4a2678fca66b07491a24dbcff3ff476be318e02d27a9fa400cad6b5f547dd076`  
		Last Modified: Sat, 26 May 2018 10:28:49 GMT  
		Size: 469.8 KB (469848 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c4a046b512a788097cb981ae07112f3acf9a3a7e482327497e84752c042b0e3d`  
		Last Modified: Sat, 26 May 2018 10:28:49 GMT  
		Size: 8.6 KB (8645 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bbb5e064795a21c6fe2b678532828599dfeca38475f384ae401a3452917112a2`  
		Last Modified: Thu, 21 Jun 2018 10:24:26 GMT  
		Size: 58.6 MB (58565791 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8a889f049e1545e24c2d4646d29bf7b0a3e0f72f2d286d8c219dbe346c08efb9`  
		Last Modified: Thu, 21 Jun 2018 10:24:09 GMT  
		Size: 172.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7da14007fe0da424adf4a75292ded9fae229448fbca2f31fd9be25d875290f85`  
		Last Modified: Thu, 21 Jun 2018 10:24:10 GMT  
		Size: 2.5 MB (2457580 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ccc76284d5a2c5b70dc71348dd65954b145b82b10252ae4c34b4960f37e90b86`  
		Last Modified: Thu, 21 Jun 2018 10:24:30 GMT  
		Size: 90.0 MB (89999138 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f957288162825d819debf1f6f7c10ee1f44c5bd0d99f411380a51626910bda76`  
		Last Modified: Thu, 21 Jun 2018 10:24:10 GMT  
		Size: 1.8 KB (1789 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `redmine:3` - linux; s390x

```console
$ docker pull redmine@sha256:30b50ca230b2b96668f067c3aa64f4ab650c5d0f58b705b9475e8eb036d65f63
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **254.9 MB (254937140 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:924bf921e4b13986dd1234309bc076c1a40bf4134fc02b23ec26aac9448fc0e1`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["rails","server","-b","0.0.0.0"]`

```dockerfile
# Sat, 28 Apr 2018 11:42:31 GMT
ADD file:ac1cfec75c7e1898f2c9b7d17653da3684fdda7d14440ce16f1939bb66105cdc in / 
# Sat, 28 Apr 2018 11:42:31 GMT
CMD ["bash"]
# Sat, 28 Apr 2018 15:34:23 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Sat, 28 Apr 2018 15:34:24 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Sat, 28 Apr 2018 15:34:24 GMT
ENV RUBY_MAJOR=2.4
# Sat, 28 Apr 2018 15:34:24 GMT
ENV RUBY_VERSION=2.4.4
# Sat, 28 Apr 2018 15:34:24 GMT
ENV RUBY_DOWNLOAD_SHA256=1d0034071d675193ca769f64c91827e5f54cb3a7962316a41d5217c7bc6949f0
# Thu, 24 May 2018 13:16:30 GMT
ENV RUBYGEMS_VERSION=2.7.7
# Thu, 24 May 2018 13:16:30 GMT
ENV BUNDLER_VERSION=1.16.2
# Thu, 24 May 2018 13:19:35 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		dpkg-dev 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 		xz-utils 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& dpkg-query --show --showformat '${package}\n' 		| grep -P '^libreadline\d+$' 		| xargs apt-mark manual 	&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force 	&& rm -r /root/.gem/
# Thu, 24 May 2018 13:19:35 GMT
ENV GEM_HOME=/usr/local/bundle
# Fri, 25 May 2018 11:58:16 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Fri, 25 May 2018 11:58:17 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/bundle/gems/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 25 May 2018 11:58:17 GMT
RUN mkdir -p "$GEM_HOME" && chmod 777 "$GEM_HOME"
# Fri, 25 May 2018 11:58:18 GMT
CMD ["irb"]
# Sat, 26 May 2018 13:25:59 GMT
RUN groupadd -r redmine && useradd -r -g redmine redmine
# Sat, 26 May 2018 13:26:09 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		wget 	&& rm -rf /var/lib/apt/lists/*
# Sat, 26 May 2018 13:26:09 GMT
ENV GOSU_VERSION=1.10
# Sat, 26 May 2018 13:26:11 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Sat, 26 May 2018 13:26:12 GMT
ENV TINI_VERSION=v0.16.1
# Sat, 26 May 2018 13:26:14 GMT
RUN set -x 	&& wget -O /usr/local/bin/tini "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/tini.asc "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5 	&& gpg --batch --verify /usr/local/bin/tini.asc /usr/local/bin/tini 	&& rm -r "$GNUPGHOME" /usr/local/bin/tini.asc 	&& chmod +x /usr/local/bin/tini 	&& tini -h
# Thu, 21 Jun 2018 13:40:18 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		imagemagick 		mercurial 		openssh-client 		subversion 	&& rm -rf /var/lib/apt/lists/*
# Thu, 21 Jun 2018 13:40:20 GMT
ENV RAILS_ENV=production
# Thu, 21 Jun 2018 13:40:20 GMT
WORKDIR /usr/src/redmine
# Thu, 21 Jun 2018 13:40:20 GMT
ENV REDMINE_VERSION=3.4.6
# Thu, 21 Jun 2018 13:40:20 GMT
ENV REDMINE_DOWNLOAD_MD5=5f4993446ecf25782f469763c0d32ea1
# Thu, 21 Jun 2018 13:40:23 GMT
RUN wget -O redmine.tar.gz "https://www.redmine.org/releases/redmine-${REDMINE_VERSION}.tar.gz" 	&& echo "$REDMINE_DOWNLOAD_MD5 redmine.tar.gz" | md5sum -c - 	&& tar -xvf redmine.tar.gz --strip-components=1 	&& rm redmine.tar.gz files/delete.me log/delete.me 	&& mkdir -p tmp/pdf public/plugin_assets 	&& chown -R redmine:redmine ./
# Thu, 21 Jun 2018 13:43:55 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		freetds-dev 		gcc 		libmagickcore-dev 		libmagickwand-dev 		libmysqlclient-dev 		libpq-dev 		libsqlite3-dev 		make 		patch 	; 	rm -rf /var/lib/apt/lists/*; 		bundle install --without development test; 	for adapter in mysql2 postgresql sqlserver sqlite3; do 		echo "$RAILS_ENV:" > ./config/database.yml; 		echo "  adapter: $adapter" >> ./config/database.yml; 		bundle install --without development test; 		cp Gemfile.lock "Gemfile.lock.${adapter}"; 	done; 	rm ./config/database.yml; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| grep -v '^/usr/local/' 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false
# Thu, 21 Jun 2018 13:43:56 GMT
VOLUME [/usr/src/redmine/files]
# Thu, 21 Jun 2018 13:43:56 GMT
COPY file:8064eeba1336402e59165b07c73d0734f58aa7e83e3c0a42b6888098f2e2c11d in / 
# Thu, 21 Jun 2018 13:43:57 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Thu, 21 Jun 2018 13:43:57 GMT
EXPOSE 3000/tcp
# Thu, 21 Jun 2018 13:43:57 GMT
CMD ["rails" "server" "-b" "0.0.0.0"]
```

-	Layers:
	-	`sha256:e0524893a6d25f3e36c190fea678ecf1845e7c0d2ba833b077a429d64b943e0a`  
		Last Modified: Sat, 28 Apr 2018 11:47:52 GMT  
		Size: 54.5 MB (54465857 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:61347f1daff97305b17924679d0a40043c3c68c04ecd38580c03a9f5f14cc025`  
		Last Modified: Sat, 28 Apr 2018 16:00:45 GMT  
		Size: 10.0 MB (9963110 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4516576626d0afc4ce307a23343efc17d8fa199788465d6fb1966c6e38405270`  
		Last Modified: Sat, 28 Apr 2018 16:00:42 GMT  
		Size: 205.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5db3c4bbb862bf979405dbf70d32620b3868872a06f125c0636aa2ca5d9a8118`  
		Last Modified: Thu, 24 May 2018 13:48:49 GMT  
		Size: 21.7 MB (21709046 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cc118bcf2202904ad8addf51827feb3eb0be972ee9912cfef0c03d939af4af5d`  
		Last Modified: Fri, 25 May 2018 12:08:37 GMT  
		Size: 148.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0bedd5671d7bb05f77a136f485548dd94b826bcaeca59790f44d37972cac966c`  
		Last Modified: Sat, 26 May 2018 13:34:13 GMT  
		Size: 2.1 KB (2107 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:df0ad57d1afd283e6ea7a12a3fdb17282925a2ac6c8fc1e0b18594b70f4860d8`  
		Last Modified: Sat, 26 May 2018 13:34:15 GMT  
		Size: 13.1 MB (13130009 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:38f941c2e8a178296eb5ef00af421a44bd40170e8b4535faf85b8c0f669e4127`  
		Last Modified: Sat, 26 May 2018 13:34:13 GMT  
		Size: 486.8 KB (486831 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2b65703d4fed12215b832fd6eb431e15ec6df3ea624470903495fa95675645b2`  
		Last Modified: Sat, 26 May 2018 13:34:11 GMT  
		Size: 8.6 KB (8628 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:147ee1fc1b1a421958c0c5f1e52aa1fcd3bb3db7c6b68f6c4c69b8daa4356bdd`  
		Last Modified: Thu, 21 Jun 2018 13:47:39 GMT  
		Size: 59.5 MB (59533196 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:33fc24964afaca53a8f69b089f296f90016a97249c28644192e99669d94ca950`  
		Last Modified: Thu, 21 Jun 2018 13:47:26 GMT  
		Size: 139.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:95937785bb16f99b2d94476fe49fab2418fd81f458a9214d61406057d60561f7`  
		Last Modified: Thu, 21 Jun 2018 13:47:27 GMT  
		Size: 2.5 MB (2456908 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5621a26308c9d8073f8ef0d18bc14689e45b96da0d71fe09658c0311b4578690`  
		Last Modified: Thu, 21 Jun 2018 13:47:43 GMT  
		Size: 93.2 MB (93179163 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1ff10f665c615aa7ed26b1dd97eec9db4674eb2affa120fb7b23dc95d1b52b7c`  
		Last Modified: Thu, 21 Jun 2018 13:47:26 GMT  
		Size: 1.8 KB (1793 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `redmine:3.3`

```console
$ docker pull redmine@sha256:63d96aa21cbb8797c17f79a1e435270dbcd0ad7473be3bc55c9c7d2187d16d3d
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm variant v5
	-	linux; arm variant v7
	-	linux; arm64 variant v8
	-	linux; 386
	-	linux; ppc64le
	-	linux; s390x

### `redmine:3.3` - linux; amd64

```console
$ docker pull redmine@sha256:c8a3c4d82ee1def1fd7625dfe0026b0b9f2dc3c148d226f49e1a70238eaadb0d
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **244.7 MB (244669656 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:87ac1f743add57ad84817ae2e347c7a4edc919be1be31587c6356c45c7c4809a`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["rails","server","-b","0.0.0.0"]`

```dockerfile
# Sat, 28 Apr 2018 06:44:15 GMT
ADD file:3e6141c0c9cb74b14a281eb3ab7aaf162a625733e652c3948b323bb2ec8b4343 in / 
# Sat, 28 Apr 2018 06:44:16 GMT
CMD ["bash"]
# Sun, 29 Apr 2018 16:52:40 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Sun, 29 Apr 2018 16:52:41 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Sun, 29 Apr 2018 17:58:22 GMT
ENV RUBY_MAJOR=2.3
# Sun, 29 Apr 2018 17:58:22 GMT
ENV RUBY_VERSION=2.3.7
# Sun, 29 Apr 2018 17:58:22 GMT
ENV RUBY_DOWNLOAD_SHA256=c61f8f2b9d3ffff5567e186421fa191f0d5e7c2b189b426bb84498825d548edb
# Thu, 24 May 2018 01:47:00 GMT
ENV RUBYGEMS_VERSION=2.7.7
# Thu, 24 May 2018 01:47:00 GMT
ENV BUNDLER_VERSION=1.16.2
# Thu, 24 May 2018 01:49:52 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		dpkg-dev 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 		xz-utils 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& dpkg-query --show --showformat '${package}\n' 		| grep -P '^libreadline\d+$' 		| xargs apt-mark manual 	&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force 	&& rm -r /root/.gem/
# Thu, 24 May 2018 01:49:52 GMT
ENV GEM_HOME=/usr/local/bundle
# Thu, 24 May 2018 21:08:58 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Thu, 24 May 2018 21:08:58 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/bundle/gems/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Thu, 24 May 2018 21:08:59 GMT
RUN mkdir -p "$GEM_HOME" && chmod 777 "$GEM_HOME"
# Thu, 24 May 2018 21:08:59 GMT
CMD ["irb"]
# Fri, 25 May 2018 22:48:33 GMT
RUN groupadd -r redmine && useradd -r -g redmine redmine
# Fri, 25 May 2018 22:48:49 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		wget 	&& rm -rf /var/lib/apt/lists/*
# Fri, 25 May 2018 22:48:49 GMT
ENV GOSU_VERSION=1.10
# Fri, 25 May 2018 22:48:53 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Fri, 25 May 2018 22:48:53 GMT
ENV TINI_VERSION=v0.16.1
# Fri, 25 May 2018 22:48:55 GMT
RUN set -x 	&& wget -O /usr/local/bin/tini "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/tini.asc "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5 	&& gpg --batch --verify /usr/local/bin/tini.asc /usr/local/bin/tini 	&& rm -r "$GNUPGHOME" /usr/local/bin/tini.asc 	&& chmod +x /usr/local/bin/tini 	&& tini -h
# Wed, 20 Jun 2018 21:39:59 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		imagemagick 		mercurial 		openssh-client 		subversion 	&& rm -rf /var/lib/apt/lists/*
# Wed, 20 Jun 2018 21:40:00 GMT
ENV RAILS_ENV=production
# Wed, 20 Jun 2018 21:40:00 GMT
WORKDIR /usr/src/redmine
# Wed, 20 Jun 2018 21:40:00 GMT
ENV REDMINE_VERSION=3.3.8
# Wed, 20 Jun 2018 21:40:00 GMT
ENV REDMINE_DOWNLOAD_MD5=6ca9284fa1c3571f6c83dd0e0d0fec1b
# Wed, 20 Jun 2018 21:40:05 GMT
RUN wget -O redmine.tar.gz "https://www.redmine.org/releases/redmine-${REDMINE_VERSION}.tar.gz" 	&& echo "$REDMINE_DOWNLOAD_MD5 redmine.tar.gz" | md5sum -c - 	&& tar -xvf redmine.tar.gz --strip-components=1 	&& rm redmine.tar.gz files/delete.me log/delete.me 	&& mkdir -p tmp/pdf public/plugin_assets 	&& chown -R redmine:redmine ./
# Wed, 20 Jun 2018 21:42:41 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		freetds-dev 		gcc 		libmagickcore-dev 		libmagickwand-dev 		libmysqlclient-dev 		libpq-dev 		libsqlite3-dev 		make 		patch 	; 	rm -rf /var/lib/apt/lists/*; 		bundle install --without development test; 	for adapter in mysql2 postgresql sqlserver sqlite3; do 		echo "$RAILS_ENV:" > ./config/database.yml; 		echo "  adapter: $adapter" >> ./config/database.yml; 		bundle install --without development test; 		cp Gemfile.lock "Gemfile.lock.${adapter}"; 	done; 	rm ./config/database.yml; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| grep -v '^/usr/local/' 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false
# Wed, 20 Jun 2018 21:42:42 GMT
VOLUME [/usr/src/redmine/files]
# Wed, 20 Jun 2018 21:42:42 GMT
COPY file:8064eeba1336402e59165b07c73d0734f58aa7e83e3c0a42b6888098f2e2c11d in / 
# Wed, 20 Jun 2018 21:42:42 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Wed, 20 Jun 2018 21:42:43 GMT
EXPOSE 3000/tcp
# Wed, 20 Jun 2018 21:42:43 GMT
CMD ["rails" "server" "-b" "0.0.0.0"]
```

-	Layers:
	-	`sha256:3d77ce4481b119f00e53bee9b4a443469c42c224db954ddaa2e6b74cd73cd5d0`  
		Last Modified: Sat, 28 Apr 2018 08:24:47 GMT  
		Size: 54.3 MB (54262566 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:05a78650ca91970038096c478f5bc7b8155cf0226db13c86ccf40e0e476e23d5`  
		Last Modified: Sun, 29 Apr 2018 19:33:59 GMT  
		Size: 10.2 MB (10168983 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:860996a55f7fba99ae60e7be5fc25d885d982031d74467b9bcfc84f96e72def6`  
		Last Modified: Sun, 29 Apr 2018 19:33:57 GMT  
		Size: 205.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4b80dc12656f673e52960efe49e4f711be35249c76bd015018e7af9b261f65b9`  
		Last Modified: Thu, 24 May 2018 02:06:58 GMT  
		Size: 33.9 MB (33927309 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:608515211c40a538c0165044109a887c946268f6836b7a0486f709e1e1259ae1`  
		Last Modified: Thu, 24 May 2018 21:19:34 GMT  
		Size: 148.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1bc2ef993469835c8b5e39e0fdf1357175ab9b0c5558dc0414417a806cb06c50`  
		Last Modified: Fri, 25 May 2018 22:54:40 GMT  
		Size: 2.1 KB (2106 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:39a9802640b3283085a975cdd520f7885f034b870e41c195867aa9dbf7d432f2`  
		Last Modified: Fri, 25 May 2018 22:54:41 GMT  
		Size: 13.0 MB (12967854 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:01fa73fc0f4c5f19de0704b75842838d7e89f9900b9680dfedb39079c48c90cd`  
		Last Modified: Fri, 25 May 2018 22:54:38 GMT  
		Size: 500.7 KB (500674 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:11dd6ceb02ca6b57f8bdacbf04a2b26d8b28bfc691b961e9d5ca75ce90e65630`  
		Last Modified: Fri, 25 May 2018 22:54:37 GMT  
		Size: 8.5 KB (8510 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4bbed35f8bbe747dfc26c7ecda6a7dd05b490ecb9f1a66732e27fdf249e1e13e`  
		Last Modified: Wed, 20 Jun 2018 21:51:32 GMT  
		Size: 59.7 MB (59701163 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:66fb5daf0fa81dd94ce0c137679f0d0ddd03d68cd756cf9bef4809b7b07f2e53`  
		Last Modified: Wed, 20 Jun 2018 21:51:15 GMT  
		Size: 141.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8f72a72d48f560a273b47fa716ca9fed3828c5ed7be3462882f55bf02edb3c4c`  
		Last Modified: Wed, 20 Jun 2018 21:51:16 GMT  
		Size: 2.4 MB (2394059 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d28265a8c4bce8ed41c9ce7e5bc6eab27c2c9272ba835e52da389bd2a418c14e`  
		Last Modified: Wed, 20 Jun 2018 21:51:24 GMT  
		Size: 70.7 MB (70734145 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0c7ae25302669301e0ba8398fe0561a195cd5e8303c31bc3fab9c17cbe84c918`  
		Last Modified: Wed, 20 Jun 2018 21:51:15 GMT  
		Size: 1.8 KB (1793 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `redmine:3.3` - linux; arm variant v5

```console
$ docker pull redmine@sha256:92343ba20aba16b34f87e429c598372a25ca5f666e6d26dba40e9d941a9e4342
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **237.2 MB (237229856 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:dceebaa3f9d8a2c106fa2e07de34e0be66c0cfb207329a26684620d99c2d1e36`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["rails","server","-b","0.0.0.0"]`

```dockerfile
# Sat, 28 Apr 2018 08:49:23 GMT
ADD file:2d2cd360e66aeff5557c7e7117985a00d109278c3f456ee970afcc9a46483264 in / 
# Sat, 28 Apr 2018 08:49:23 GMT
CMD ["bash"]
# Sat, 28 Apr 2018 11:50:09 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Sat, 28 Apr 2018 11:50:10 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Sat, 28 Apr 2018 12:10:57 GMT
ENV RUBY_MAJOR=2.3
# Sat, 28 Apr 2018 12:10:58 GMT
ENV RUBY_VERSION=2.3.7
# Sat, 28 Apr 2018 12:10:58 GMT
ENV RUBY_DOWNLOAD_SHA256=c61f8f2b9d3ffff5567e186421fa191f0d5e7c2b189b426bb84498825d548edb
# Thu, 24 May 2018 11:17:12 GMT
ENV RUBYGEMS_VERSION=2.7.7
# Thu, 24 May 2018 11:17:12 GMT
ENV BUNDLER_VERSION=1.16.2
# Thu, 24 May 2018 11:21:41 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		dpkg-dev 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 		xz-utils 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& dpkg-query --show --showformat '${package}\n' 		| grep -P '^libreadline\d+$' 		| xargs apt-mark manual 	&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force 	&& rm -r /root/.gem/
# Thu, 24 May 2018 11:21:42 GMT
ENV GEM_HOME=/usr/local/bundle
# Fri, 25 May 2018 09:10:52 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Fri, 25 May 2018 09:10:52 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/bundle/gems/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 25 May 2018 09:10:53 GMT
RUN mkdir -p "$GEM_HOME" && chmod 777 "$GEM_HOME"
# Fri, 25 May 2018 09:10:53 GMT
CMD ["irb"]
# Sat, 26 May 2018 10:11:34 GMT
RUN groupadd -r redmine && useradd -r -g redmine redmine
# Sat, 26 May 2018 10:12:02 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		wget 	&& rm -rf /var/lib/apt/lists/*
# Sat, 26 May 2018 10:12:02 GMT
ENV GOSU_VERSION=1.10
# Sat, 26 May 2018 10:12:04 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Sat, 26 May 2018 10:12:05 GMT
ENV TINI_VERSION=v0.16.1
# Sat, 26 May 2018 10:12:06 GMT
RUN set -x 	&& wget -O /usr/local/bin/tini "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/tini.asc "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5 	&& gpg --batch --verify /usr/local/bin/tini.asc /usr/local/bin/tini 	&& rm -r "$GNUPGHOME" /usr/local/bin/tini.asc 	&& chmod +x /usr/local/bin/tini 	&& tini -h
# Thu, 21 Jun 2018 09:41:25 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		imagemagick 		mercurial 		openssh-client 		subversion 	&& rm -rf /var/lib/apt/lists/*
# Thu, 21 Jun 2018 09:41:26 GMT
ENV RAILS_ENV=production
# Thu, 21 Jun 2018 09:41:26 GMT
WORKDIR /usr/src/redmine
# Thu, 21 Jun 2018 09:41:27 GMT
ENV REDMINE_VERSION=3.3.8
# Thu, 21 Jun 2018 09:41:27 GMT
ENV REDMINE_DOWNLOAD_MD5=6ca9284fa1c3571f6c83dd0e0d0fec1b
# Thu, 21 Jun 2018 09:41:31 GMT
RUN wget -O redmine.tar.gz "https://www.redmine.org/releases/redmine-${REDMINE_VERSION}.tar.gz" 	&& echo "$REDMINE_DOWNLOAD_MD5 redmine.tar.gz" | md5sum -c - 	&& tar -xvf redmine.tar.gz --strip-components=1 	&& rm redmine.tar.gz files/delete.me log/delete.me 	&& mkdir -p tmp/pdf public/plugin_assets 	&& chown -R redmine:redmine ./
# Thu, 21 Jun 2018 09:46:16 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		freetds-dev 		gcc 		libmagickcore-dev 		libmagickwand-dev 		libmysqlclient-dev 		libpq-dev 		libsqlite3-dev 		make 		patch 	; 	rm -rf /var/lib/apt/lists/*; 		bundle install --without development test; 	for adapter in mysql2 postgresql sqlserver sqlite3; do 		echo "$RAILS_ENV:" > ./config/database.yml; 		echo "  adapter: $adapter" >> ./config/database.yml; 		bundle install --without development test; 		cp Gemfile.lock "Gemfile.lock.${adapter}"; 	done; 	rm ./config/database.yml; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| grep -v '^/usr/local/' 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false
# Thu, 21 Jun 2018 09:46:17 GMT
VOLUME [/usr/src/redmine/files]
# Thu, 21 Jun 2018 09:46:17 GMT
COPY file:8064eeba1336402e59165b07c73d0734f58aa7e83e3c0a42b6888098f2e2c11d in / 
# Thu, 21 Jun 2018 09:46:18 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Thu, 21 Jun 2018 09:46:18 GMT
EXPOSE 3000/tcp
# Thu, 21 Jun 2018 09:46:18 GMT
CMD ["rails" "server" "-b" "0.0.0.0"]
```

-	Layers:
	-	`sha256:81fc0826192f72abe617753d378af4047dbce89faf17cdab9166877006a25d8e`  
		Last Modified: Sat, 28 Apr 2018 08:57:10 GMT  
		Size: 52.5 MB (52456037 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2119f18fa6f270436c891e0c459923ae24657bf4a8be20cfcfe964e7aa64b7b2`  
		Last Modified: Sat, 28 Apr 2018 12:31:30 GMT  
		Size: 9.1 MB (9119888 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:51757db9404a98c26c96cb6b65e8c7893c1e1b5ea9774a5786abe9ec88468cf3`  
		Last Modified: Sat, 28 Apr 2018 12:31:26 GMT  
		Size: 206.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:65104c91b9394bb23a8afc0395aec5f928cef61120d6d7944e1f0081d2d231f2`  
		Last Modified: Thu, 24 May 2018 11:32:45 GMT  
		Size: 32.8 MB (32753332 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1c955480d3d1a7c63c64c0454f707a6515b7b8686a525442b2406c4c615cdcb0`  
		Last Modified: Fri, 25 May 2018 09:20:24 GMT  
		Size: 183.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4c0ad0ba38abaac1a64d49025488f6bc460bf3105f79cae5793dab1ffe9fc05d`  
		Last Modified: Sat, 26 May 2018 10:19:18 GMT  
		Size: 2.1 KB (2091 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4c0908f49977601b24ae47a6cd030bb728e452c6f92053f8681bc335b2ef3be6`  
		Last Modified: Sat, 26 May 2018 10:19:21 GMT  
		Size: 12.8 MB (12772579 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e0dd8d7f14e3d1ed9c471b63cb02d01ca2b1817e9b7baec789f437aabcd66756`  
		Last Modified: Sat, 26 May 2018 10:19:18 GMT  
		Size: 491.1 KB (491127 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2f1e4c5939feb4934132090f2eedf5491a004f003896731e342ad80523b4f1b4`  
		Last Modified: Sat, 26 May 2018 10:19:17 GMT  
		Size: 7.8 KB (7850 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7128acf94002efc8a4fb19efdb72617c1d64c7e48d9d23e1408f5c92b06b2eab`  
		Last Modified: Thu, 21 Jun 2018 09:47:46 GMT  
		Size: 57.1 MB (57055759 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ca149da96b14b046d83a61e3c1443c0b348543e147692f71090fafb13bf161cf`  
		Last Modified: Thu, 21 Jun 2018 09:47:26 GMT  
		Size: 172.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cbc43f27e5e16e73345b1ab00edafc9a5af24c7ee83f63f8e3ce0fa97aecaf3f`  
		Last Modified: Thu, 21 Jun 2018 09:47:28 GMT  
		Size: 2.4 MB (2394464 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:29356b7872aeabc36ff2e1aeebc2e4d2701367688f473d02345313a82af34636`  
		Last Modified: Thu, 21 Jun 2018 09:47:44 GMT  
		Size: 70.2 MB (70174375 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0fc71c97d263b9ceaf94453a2e90af7803854eb53ee14f1143aff7c29e6b8f3e`  
		Last Modified: Thu, 21 Jun 2018 09:47:27 GMT  
		Size: 1.8 KB (1793 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `redmine:3.3` - linux; arm variant v7

```console
$ docker pull redmine@sha256:0fc15bf64eac635c89adadd3806ff5afe8bc04610823ca1d50fe6ba086a7537e
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **231.6 MB (231578856 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:49b991834c05d7380cb1d103a1b162a258700c1d7c6a10b67c2997ff15714b8c`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["rails","server","-b","0.0.0.0"]`

```dockerfile
# Sat, 28 Apr 2018 11:59:05 GMT
ADD file:4e9c283075c120ce66f83bf541b0aeaa8a46f74c21d38e4ab1578e7f1b892823 in / 
# Sat, 28 Apr 2018 11:59:05 GMT
CMD ["bash"]
# Sat, 28 Apr 2018 15:40:52 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Sat, 28 Apr 2018 15:40:56 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Sat, 28 Apr 2018 16:01:00 GMT
ENV RUBY_MAJOR=2.3
# Sat, 28 Apr 2018 16:01:00 GMT
ENV RUBY_VERSION=2.3.7
# Sat, 28 Apr 2018 16:01:00 GMT
ENV RUBY_DOWNLOAD_SHA256=c61f8f2b9d3ffff5567e186421fa191f0d5e7c2b189b426bb84498825d548edb
# Thu, 24 May 2018 13:32:45 GMT
ENV RUBYGEMS_VERSION=2.7.7
# Thu, 24 May 2018 13:32:45 GMT
ENV BUNDLER_VERSION=1.16.2
# Thu, 24 May 2018 13:36:52 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		dpkg-dev 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 		xz-utils 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& dpkg-query --show --showformat '${package}\n' 		| grep -P '^libreadline\d+$' 		| xargs apt-mark manual 	&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force 	&& rm -r /root/.gem/
# Thu, 24 May 2018 13:36:58 GMT
ENV GEM_HOME=/usr/local/bundle
# Fri, 25 May 2018 12:28:58 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Fri, 25 May 2018 12:28:58 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/bundle/gems/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 25 May 2018 12:28:59 GMT
RUN mkdir -p "$GEM_HOME" && chmod 777 "$GEM_HOME"
# Fri, 25 May 2018 12:28:59 GMT
CMD ["irb"]
# Sat, 26 May 2018 12:31:26 GMT
RUN groupadd -r redmine && useradd -r -g redmine redmine
# Sat, 26 May 2018 12:31:53 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		wget 	&& rm -rf /var/lib/apt/lists/*
# Sat, 26 May 2018 12:31:53 GMT
ENV GOSU_VERSION=1.10
# Sat, 26 May 2018 12:31:55 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Sat, 26 May 2018 12:31:55 GMT
ENV TINI_VERSION=v0.16.1
# Sat, 26 May 2018 12:31:57 GMT
RUN set -x 	&& wget -O /usr/local/bin/tini "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/tini.asc "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5 	&& gpg --batch --verify /usr/local/bin/tini.asc /usr/local/bin/tini 	&& rm -r "$GNUPGHOME" /usr/local/bin/tini.asc 	&& chmod +x /usr/local/bin/tini 	&& tini -h
# Thu, 21 Jun 2018 12:13:23 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		imagemagick 		mercurial 		openssh-client 		subversion 	&& rm -rf /var/lib/apt/lists/*
# Thu, 21 Jun 2018 12:13:24 GMT
ENV RAILS_ENV=production
# Thu, 21 Jun 2018 12:13:24 GMT
WORKDIR /usr/src/redmine
# Thu, 21 Jun 2018 12:13:25 GMT
ENV REDMINE_VERSION=3.3.8
# Thu, 21 Jun 2018 12:13:25 GMT
ENV REDMINE_DOWNLOAD_MD5=6ca9284fa1c3571f6c83dd0e0d0fec1b
# Thu, 21 Jun 2018 12:13:29 GMT
RUN wget -O redmine.tar.gz "https://www.redmine.org/releases/redmine-${REDMINE_VERSION}.tar.gz" 	&& echo "$REDMINE_DOWNLOAD_MD5 redmine.tar.gz" | md5sum -c - 	&& tar -xvf redmine.tar.gz --strip-components=1 	&& rm redmine.tar.gz files/delete.me log/delete.me 	&& mkdir -p tmp/pdf public/plugin_assets 	&& chown -R redmine:redmine ./
# Thu, 21 Jun 2018 12:18:07 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		freetds-dev 		gcc 		libmagickcore-dev 		libmagickwand-dev 		libmysqlclient-dev 		libpq-dev 		libsqlite3-dev 		make 		patch 	; 	rm -rf /var/lib/apt/lists/*; 		bundle install --without development test; 	for adapter in mysql2 postgresql sqlserver sqlite3; do 		echo "$RAILS_ENV:" > ./config/database.yml; 		echo "  adapter: $adapter" >> ./config/database.yml; 		bundle install --without development test; 		cp Gemfile.lock "Gemfile.lock.${adapter}"; 	done; 	rm ./config/database.yml; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| grep -v '^/usr/local/' 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false
# Thu, 21 Jun 2018 12:18:08 GMT
VOLUME [/usr/src/redmine/files]
# Thu, 21 Jun 2018 12:18:08 GMT
COPY file:8064eeba1336402e59165b07c73d0734f58aa7e83e3c0a42b6888098f2e2c11d in / 
# Thu, 21 Jun 2018 12:18:09 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Thu, 21 Jun 2018 12:18:09 GMT
EXPOSE 3000/tcp
# Thu, 21 Jun 2018 12:18:09 GMT
CMD ["rails" "server" "-b" "0.0.0.0"]
```

-	Layers:
	-	`sha256:5c478157e28e3c26a0209484edb518799e1c21863d4700579c010b7203e0537f`  
		Last Modified: Sat, 28 Apr 2018 12:10:24 GMT  
		Size: 50.2 MB (50195697 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:57cc82e3a61290e4bfc39b7ec615f84e7782d645852ff04b0f1077ba3a8d6c85`  
		Last Modified: Sat, 28 Apr 2018 16:21:20 GMT  
		Size: 8.8 MB (8777726 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e60d4b7c236d855ddd6a1f286ece09d909ea721b8959a806142de215e84ad242`  
		Last Modified: Sat, 28 Apr 2018 16:21:17 GMT  
		Size: 207.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:79c49f5f68f7c6a9010b9b38fea693855a4635ca6d5d986d01420ea8d013c707`  
		Last Modified: Thu, 24 May 2018 13:55:41 GMT  
		Size: 32.5 MB (32542173 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:934dc94129d4496ffd10875a2c6058f6396f3efb21926efaaae7ad971facf665`  
		Last Modified: Fri, 25 May 2018 12:43:45 GMT  
		Size: 181.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:caa9a3c5fc967f8b658a66e0ae779ea381e13bc89289dbf72795bb49791fca5b`  
		Last Modified: Sat, 26 May 2018 12:39:04 GMT  
		Size: 2.1 KB (2094 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7b38fd1d46fe67fb5d158cd8c269017e89f4f63f7a5a9d014e13f159ce8a079f`  
		Last Modified: Sat, 26 May 2018 12:39:07 GMT  
		Size: 12.6 MB (12629394 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bbd3f2473b5fd66ce61544076766f578a5b58b36b084154675e2dbf55ffc5fa0`  
		Last Modified: Sat, 26 May 2018 12:39:03 GMT  
		Size: 475.3 KB (475271 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:85f96c619c7aac443df9ee910d0b0eeeafc84458e098f4695326b3a45537298b`  
		Last Modified: Sat, 26 May 2018 12:39:02 GMT  
		Size: 7.3 KB (7313 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:36e4ee90ace2e64cbcc2a2d3e280ad8d331131458bb72bd020c2fa5ecfb82d40`  
		Last Modified: Thu, 21 Jun 2018 12:19:37 GMT  
		Size: 54.7 MB (54698433 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2b85c9b67cd8f1ce20a9c1d3923ed89433a632918570e1d48bbcee0ddfd0aae1`  
		Last Modified: Thu, 21 Jun 2018 12:19:20 GMT  
		Size: 170.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e2d037d38862bafc6fd4f24ca7dfe5d9ca8faf2aeb76bfd10979335acf56806c`  
		Last Modified: Thu, 21 Jun 2018 12:19:22 GMT  
		Size: 2.4 MB (2394445 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:430bc271235e2ac890d803fb99d2fbcf46c6c451e1c64e8d7b496c43f2b3c5d4`  
		Last Modified: Thu, 21 Jun 2018 12:19:36 GMT  
		Size: 69.9 MB (69853959 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:56b845da62bdc2c86bf4bcd0ffe10678696982dfa0fbbfc2a8211b67fe46a4d3`  
		Last Modified: Thu, 21 Jun 2018 12:19:20 GMT  
		Size: 1.8 KB (1793 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `redmine:3.3` - linux; arm64 variant v8

```console
$ docker pull redmine@sha256:1f509a8d15a70a347b6a315b32a672a35f031d10a3f3269882be031ae423b951
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **237.1 MB (237077303 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:f79089a322c6f8fe1d38c00e7c0875658f5e1e0f112487af5e3394e40d9a15da`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["rails","server","-b","0.0.0.0"]`

```dockerfile
# Mon, 30 Apr 2018 23:21:38 GMT
ADD file:387c83918422a6546379c4d84818ca3949fcd63aec058da562b08c947a9ed571 in / 
# Mon, 30 Apr 2018 23:21:40 GMT
CMD ["bash"]
# Tue, 01 May 2018 08:41:36 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Tue, 01 May 2018 08:41:41 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Tue, 01 May 2018 09:21:51 GMT
ENV RUBY_MAJOR=2.3
# Tue, 01 May 2018 09:21:51 GMT
ENV RUBY_VERSION=2.3.7
# Tue, 01 May 2018 09:21:52 GMT
ENV RUBY_DOWNLOAD_SHA256=c61f8f2b9d3ffff5567e186421fa191f0d5e7c2b189b426bb84498825d548edb
# Fri, 25 May 2018 17:42:54 GMT
ENV RUBYGEMS_VERSION=2.7.7
# Fri, 25 May 2018 17:42:55 GMT
ENV BUNDLER_VERSION=1.16.2
# Fri, 25 May 2018 17:50:33 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		dpkg-dev 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 		xz-utils 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& dpkg-query --show --showformat '${package}\n' 		| grep -P '^libreadline\d+$' 		| xargs apt-mark manual 	&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force 	&& rm -r /root/.gem/
# Fri, 25 May 2018 17:50:34 GMT
ENV GEM_HOME=/usr/local/bundle
# Fri, 25 May 2018 17:50:35 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Fri, 25 May 2018 17:50:36 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/bundle/gems/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 25 May 2018 17:50:37 GMT
RUN mkdir -p "$GEM_HOME" && chmod 777 "$GEM_HOME"
# Fri, 25 May 2018 17:50:38 GMT
CMD ["irb"]
# Fri, 25 May 2018 21:57:09 GMT
RUN groupadd -r redmine && useradd -r -g redmine redmine
# Fri, 25 May 2018 21:57:32 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		wget 	&& rm -rf /var/lib/apt/lists/*
# Fri, 25 May 2018 21:57:33 GMT
ENV GOSU_VERSION=1.10
# Fri, 25 May 2018 21:57:37 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Fri, 25 May 2018 21:57:37 GMT
ENV TINI_VERSION=v0.16.1
# Fri, 25 May 2018 21:57:41 GMT
RUN set -x 	&& wget -O /usr/local/bin/tini "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/tini.asc "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5 	&& gpg --batch --verify /usr/local/bin/tini.asc /usr/local/bin/tini 	&& rm -r "$GNUPGHOME" /usr/local/bin/tini.asc 	&& chmod +x /usr/local/bin/tini 	&& tini -h
# Thu, 21 Jun 2018 17:15:33 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		imagemagick 		mercurial 		openssh-client 		subversion 	&& rm -rf /var/lib/apt/lists/*
# Thu, 21 Jun 2018 17:15:35 GMT
ENV RAILS_ENV=production
# Thu, 21 Jun 2018 17:15:35 GMT
WORKDIR /usr/src/redmine
# Thu, 21 Jun 2018 17:15:36 GMT
ENV REDMINE_VERSION=3.3.8
# Thu, 21 Jun 2018 17:15:37 GMT
ENV REDMINE_DOWNLOAD_MD5=6ca9284fa1c3571f6c83dd0e0d0fec1b
# Thu, 21 Jun 2018 17:15:42 GMT
RUN wget -O redmine.tar.gz "https://www.redmine.org/releases/redmine-${REDMINE_VERSION}.tar.gz" 	&& echo "$REDMINE_DOWNLOAD_MD5 redmine.tar.gz" | md5sum -c - 	&& tar -xvf redmine.tar.gz --strip-components=1 	&& rm redmine.tar.gz files/delete.me log/delete.me 	&& mkdir -p tmp/pdf public/plugin_assets 	&& chown -R redmine:redmine ./
# Thu, 21 Jun 2018 17:26:43 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		freetds-dev 		gcc 		libmagickcore-dev 		libmagickwand-dev 		libmysqlclient-dev 		libpq-dev 		libsqlite3-dev 		make 		patch 	; 	rm -rf /var/lib/apt/lists/*; 		bundle install --without development test; 	for adapter in mysql2 postgresql sqlserver sqlite3; do 		echo "$RAILS_ENV:" > ./config/database.yml; 		echo "  adapter: $adapter" >> ./config/database.yml; 		bundle install --without development test; 		cp Gemfile.lock "Gemfile.lock.${adapter}"; 	done; 	rm ./config/database.yml; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| grep -v '^/usr/local/' 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false
# Thu, 21 Jun 2018 17:26:44 GMT
VOLUME [/usr/src/redmine/files]
# Thu, 21 Jun 2018 17:26:45 GMT
COPY file:8064eeba1336402e59165b07c73d0734f58aa7e83e3c0a42b6888098f2e2c11d in / 
# Thu, 21 Jun 2018 17:26:46 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Thu, 21 Jun 2018 17:26:47 GMT
EXPOSE 3000/tcp
# Thu, 21 Jun 2018 17:26:47 GMT
CMD ["rails" "server" "-b" "0.0.0.0"]
```

-	Layers:
	-	`sha256:363cfded2ef3921ef972c85cafc77cf16cdcfddfd49782ad4540cb73fd5e57a2`  
		Last Modified: Mon, 30 Apr 2018 23:41:06 GMT  
		Size: 51.4 MB (51446854 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6aeaeeebfa7e2a1e6c69a484a7648b6313aff4bf219767667e43bbfc42bb40d9`  
		Last Modified: Tue, 01 May 2018 09:53:45 GMT  
		Size: 9.3 MB (9343083 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3b78cb3f4882a2b3bf1ecb4fdbe1e145a3ddb80ce1fde62a33ada1beaf12daf8`  
		Last Modified: Tue, 01 May 2018 09:53:41 GMT  
		Size: 205.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ed306b6b25ea2954c71b5a7a802e55dd849a0c4f9d9348974dfcf0aa3a3f4360`  
		Last Modified: Fri, 25 May 2018 18:12:58 GMT  
		Size: 34.0 MB (34023340 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:29958525b6f0d099361441683b4546e9a8fa17728f43cb8cefb616e936646278`  
		Last Modified: Fri, 25 May 2018 18:12:42 GMT  
		Size: 148.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:88dfdd87d35bfc527d1e1fa6e6765f3c543c6bcca388e3ccc197aeea1a620a7d`  
		Last Modified: Fri, 25 May 2018 22:13:20 GMT  
		Size: 2.1 KB (2116 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f8c84422c38a6db49dd44b5227afbaac45429fcf4544ea28aaa3549413795c55`  
		Last Modified: Fri, 25 May 2018 22:13:25 GMT  
		Size: 12.9 MB (12940754 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7f73061b438fd37a1444decd7254737e1c3eec6b552718eed4d0bca7956927e3`  
		Last Modified: Fri, 25 May 2018 22:13:19 GMT  
		Size: 468.7 KB (468693 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9c6169a236f22bae25d63b6d3a1628842abb147c2260fa1ff414f6840e55a9c4`  
		Last Modified: Fri, 25 May 2018 22:13:19 GMT  
		Size: 8.2 KB (8153 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:398742b41291631bc6f968c8cae2468ddd14b9b852af94083d96869eff6854f4`  
		Last Modified: Thu, 21 Jun 2018 17:28:41 GMT  
		Size: 56.2 MB (56167018 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fa9c2b611faef911068e185b9abd88ef0c5b6bdfecb029be9fe7ad4392ab6d45`  
		Last Modified: Thu, 21 Jun 2018 17:28:19 GMT  
		Size: 140.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9ac9acd59689fde9ce96612b78c07d99cdd4eb733d59dd9f750b2524453a81ce`  
		Last Modified: Thu, 21 Jun 2018 17:28:20 GMT  
		Size: 2.4 MB (2394066 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9fd8816d2648d1b0ddd291371cbd9a4c8907dcf114e58191a995f158ff215658`  
		Last Modified: Thu, 21 Jun 2018 17:28:39 GMT  
		Size: 70.3 MB (70280940 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5b5617e5c727381aa5b1aa4acd6061c0b23e79d70c5cea5169d6949554524713`  
		Last Modified: Thu, 21 Jun 2018 17:28:19 GMT  
		Size: 1.8 KB (1793 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `redmine:3.3` - linux; 386

```console
$ docker pull redmine@sha256:5ce7cb2d9fd7edd96f1b44d63502d01ca88ba1f1e08cd2c0db2c0da8d23eea5d
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **247.0 MB (247027540 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:b022a1e4e32c7eb479bf6553e707e7fcaf60ec92e49a579cb9e5b558ca135b09`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["rails","server","-b","0.0.0.0"]`

```dockerfile
# Sat, 28 Apr 2018 10:39:32 GMT
ADD file:ce5174f2b2c155a2421fac3ff37a02d9551d5d79e31a541189bcfd2416a6903a in / 
# Sat, 28 Apr 2018 10:39:32 GMT
CMD ["bash"]
# Fri, 01 Jun 2018 14:56:41 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Fri, 01 Jun 2018 14:56:42 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Fri, 01 Jun 2018 15:31:48 GMT
ENV RUBY_MAJOR=2.3
# Fri, 01 Jun 2018 15:31:48 GMT
ENV RUBY_VERSION=2.3.7
# Fri, 01 Jun 2018 15:31:48 GMT
ENV RUBY_DOWNLOAD_SHA256=c61f8f2b9d3ffff5567e186421fa191f0d5e7c2b189b426bb84498825d548edb
# Fri, 01 Jun 2018 15:31:48 GMT
ENV RUBYGEMS_VERSION=2.7.7
# Fri, 01 Jun 2018 15:31:48 GMT
ENV BUNDLER_VERSION=1.16.2
# Fri, 01 Jun 2018 15:37:54 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		dpkg-dev 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 		xz-utils 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& dpkg-query --show --showformat '${package}\n' 		| grep -P '^libreadline\d+$' 		| xargs apt-mark manual 	&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force 	&& rm -r /root/.gem/
# Fri, 01 Jun 2018 15:37:55 GMT
ENV GEM_HOME=/usr/local/bundle
# Fri, 01 Jun 2018 15:37:55 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Fri, 01 Jun 2018 15:37:55 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/bundle/gems/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 01 Jun 2018 15:37:56 GMT
RUN mkdir -p "$GEM_HOME" && chmod 777 "$GEM_HOME"
# Fri, 01 Jun 2018 15:37:56 GMT
CMD ["irb"]
# Fri, 01 Jun 2018 17:21:54 GMT
RUN groupadd -r redmine && useradd -r -g redmine redmine
# Fri, 01 Jun 2018 17:22:48 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		wget 	&& rm -rf /var/lib/apt/lists/*
# Fri, 01 Jun 2018 17:22:48 GMT
ENV GOSU_VERSION=1.10
# Fri, 01 Jun 2018 17:22:55 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Fri, 01 Jun 2018 17:22:55 GMT
ENV TINI_VERSION=v0.16.1
# Fri, 01 Jun 2018 17:22:57 GMT
RUN set -x 	&& wget -O /usr/local/bin/tini "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/tini.asc "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5 	&& gpg --batch --verify /usr/local/bin/tini.asc /usr/local/bin/tini 	&& rm -r "$GNUPGHOME" /usr/local/bin/tini.asc 	&& chmod +x /usr/local/bin/tini 	&& tini -h
# Thu, 21 Jun 2018 11:09:15 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		imagemagick 		mercurial 		openssh-client 		subversion 	&& rm -rf /var/lib/apt/lists/*
# Thu, 21 Jun 2018 11:09:16 GMT
ENV RAILS_ENV=production
# Thu, 21 Jun 2018 11:09:16 GMT
WORKDIR /usr/src/redmine
# Thu, 21 Jun 2018 11:09:16 GMT
ENV REDMINE_VERSION=3.3.8
# Thu, 21 Jun 2018 11:09:17 GMT
ENV REDMINE_DOWNLOAD_MD5=6ca9284fa1c3571f6c83dd0e0d0fec1b
# Thu, 21 Jun 2018 11:09:21 GMT
RUN wget -O redmine.tar.gz "https://www.redmine.org/releases/redmine-${REDMINE_VERSION}.tar.gz" 	&& echo "$REDMINE_DOWNLOAD_MD5 redmine.tar.gz" | md5sum -c - 	&& tar -xvf redmine.tar.gz --strip-components=1 	&& rm redmine.tar.gz files/delete.me log/delete.me 	&& mkdir -p tmp/pdf public/plugin_assets 	&& chown -R redmine:redmine ./
# Thu, 21 Jun 2018 11:14:20 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		freetds-dev 		gcc 		libmagickcore-dev 		libmagickwand-dev 		libmysqlclient-dev 		libpq-dev 		libsqlite3-dev 		make 		patch 	; 	rm -rf /var/lib/apt/lists/*; 		bundle install --without development test; 	for adapter in mysql2 postgresql sqlserver sqlite3; do 		echo "$RAILS_ENV:" > ./config/database.yml; 		echo "  adapter: $adapter" >> ./config/database.yml; 		bundle install --without development test; 		cp Gemfile.lock "Gemfile.lock.${adapter}"; 	done; 	rm ./config/database.yml; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| grep -v '^/usr/local/' 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false
# Thu, 21 Jun 2018 11:14:21 GMT
VOLUME [/usr/src/redmine/files]
# Thu, 21 Jun 2018 11:14:21 GMT
COPY file:8064eeba1336402e59165b07c73d0734f58aa7e83e3c0a42b6888098f2e2c11d in / 
# Thu, 21 Jun 2018 11:14:21 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Thu, 21 Jun 2018 11:14:21 GMT
EXPOSE 3000/tcp
# Thu, 21 Jun 2018 11:14:21 GMT
CMD ["rails" "server" "-b" "0.0.0.0"]
```

-	Layers:
	-	`sha256:05b419d667f793c8c2edf0ff0aec14fc4d66733cdb89957ac89e8bfbeaddd0fa`  
		Last Modified: Sat, 28 Apr 2018 10:44:20 GMT  
		Size: 54.5 MB (54486782 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3d6891754f33e4c1f328ba0f4530fdb8383be81d86d518c6967565db3d8a7d3f`  
		Last Modified: Fri, 01 Jun 2018 15:49:54 GMT  
		Size: 14.9 MB (14942131 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:089cb9bb407565a3373144a74a72a2345d043f8423185a11fe236787bfc2d617`  
		Last Modified: Fri, 01 Jun 2018 15:49:47 GMT  
		Size: 208.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8115b1e634948c41f632ab946ef11b82c36946e3400f38fdf3d7dd4859d47d0e`  
		Last Modified: Fri, 01 Jun 2018 15:53:49 GMT  
		Size: 31.2 MB (31159508 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:540caa681d0f094e7be3241a456e97e445472d53b9431fb5e59ade8a71be700f`  
		Last Modified: Fri, 01 Jun 2018 15:53:35 GMT  
		Size: 148.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:07cfdf83ac422932a67b6ed1ce96a3fa7172fdf95d4535c181c37cb05a0260bb`  
		Last Modified: Fri, 01 Jun 2018 17:32:53 GMT  
		Size: 2.1 KB (2089 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:458b6f451d4b864c82c5b14ad4abe587aeaf6c83e221686868b73d9f5bcfb6fb`  
		Last Modified: Fri, 01 Jun 2018 17:32:57 GMT  
		Size: 13.1 MB (13103058 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d217113ffe8b8cfc32044872c625cc67a4cb9c2f5c8942898aba04d724ff9941`  
		Last Modified: Fri, 01 Jun 2018 17:32:50 GMT  
		Size: 480.6 KB (480577 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9574eda8f6842775047763a6a61375169bd3730b604a896917d234e733fdc541`  
		Last Modified: Fri, 01 Jun 2018 17:32:48 GMT  
		Size: 8.6 KB (8568 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8c2654f85f5b7f668e683128adac1f725054af819ea55c6f7bde0e9cbf4f3a9c`  
		Last Modified: Thu, 21 Jun 2018 11:16:33 GMT  
		Size: 60.6 MB (60580201 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:75c5d16d908b5bbb9dc42ac5c42fbcb38e0339a5e8cccdc517d407fc2d9299c3`  
		Last Modified: Thu, 21 Jun 2018 11:16:04 GMT  
		Size: 139.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:54f02cd2bfa1aa35131d3ec3b391ed666e1c005709b4efde7af0c199606201ca`  
		Last Modified: Thu, 21 Jun 2018 11:16:06 GMT  
		Size: 2.4 MB (2394062 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5de0d5a78758a9d99af5f32a815f02e58d8960b1360797b02b0ccc7d614b1383`  
		Last Modified: Thu, 21 Jun 2018 11:16:27 GMT  
		Size: 69.9 MB (69868276 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9cce7d0a9ac71218e5f6253327d12ad23d12b93d2f5ad9aa9cbe763647a28798`  
		Last Modified: Thu, 21 Jun 2018 11:16:05 GMT  
		Size: 1.8 KB (1793 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `redmine:3.3` - linux; ppc64le

```console
$ docker pull redmine@sha256:7b3d314b8d89c31112ed2f34d9253010dbae03fb53229956cabd127be0615bde
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **244.0 MB (244005336 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:13ab9e257d92288192fa7cc584c2c2f9a8641dc51f48b6c033165025237cf80e`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["rails","server","-b","0.0.0.0"]`

```dockerfile
# Sat, 28 Apr 2018 08:17:46 GMT
ADD file:6a4bd4ea54f669286e984ecf8178e1fa7c12c8b6fc0f96e4203ae7a6f99a2279 in / 
# Sat, 28 Apr 2018 08:17:47 GMT
CMD ["bash"]
# Sat, 28 Apr 2018 11:24:06 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Sat, 28 Apr 2018 11:24:08 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Sat, 28 Apr 2018 11:47:05 GMT
ENV RUBY_MAJOR=2.3
# Sat, 28 Apr 2018 11:47:06 GMT
ENV RUBY_VERSION=2.3.7
# Sat, 28 Apr 2018 11:47:06 GMT
ENV RUBY_DOWNLOAD_SHA256=c61f8f2b9d3ffff5567e186421fa191f0d5e7c2b189b426bb84498825d548edb
# Thu, 24 May 2018 11:25:04 GMT
ENV RUBYGEMS_VERSION=2.7.7
# Thu, 24 May 2018 11:25:05 GMT
ENV BUNDLER_VERSION=1.16.2
# Thu, 24 May 2018 11:31:17 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		dpkg-dev 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 		xz-utils 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& dpkg-query --show --showformat '${package}\n' 		| grep -P '^libreadline\d+$' 		| xargs apt-mark manual 	&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force 	&& rm -r /root/.gem/
# Thu, 24 May 2018 11:31:19 GMT
ENV GEM_HOME=/usr/local/bundle
# Fri, 25 May 2018 09:22:00 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Fri, 25 May 2018 09:22:19 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/bundle/gems/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 25 May 2018 09:22:33 GMT
RUN mkdir -p "$GEM_HOME" && chmod 777 "$GEM_HOME"
# Fri, 25 May 2018 09:22:38 GMT
CMD ["irb"]
# Sat, 26 May 2018 10:00:11 GMT
RUN groupadd -r redmine && useradd -r -g redmine redmine
# Sat, 26 May 2018 10:01:14 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		wget 	&& rm -rf /var/lib/apt/lists/*
# Sat, 26 May 2018 10:01:18 GMT
ENV GOSU_VERSION=1.10
# Sat, 26 May 2018 10:01:23 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Sat, 26 May 2018 10:01:26 GMT
ENV TINI_VERSION=v0.16.1
# Sat, 26 May 2018 10:01:29 GMT
RUN set -x 	&& wget -O /usr/local/bin/tini "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/tini.asc "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5 	&& gpg --batch --verify /usr/local/bin/tini.asc /usr/local/bin/tini 	&& rm -r "$GNUPGHOME" /usr/local/bin/tini.asc 	&& chmod +x /usr/local/bin/tini 	&& tini -h
# Thu, 21 Jun 2018 10:13:00 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		imagemagick 		mercurial 		openssh-client 		subversion 	&& rm -rf /var/lib/apt/lists/*
# Thu, 21 Jun 2018 10:13:02 GMT
ENV RAILS_ENV=production
# Thu, 21 Jun 2018 10:13:02 GMT
WORKDIR /usr/src/redmine
# Thu, 21 Jun 2018 10:13:03 GMT
ENV REDMINE_VERSION=3.3.8
# Thu, 21 Jun 2018 10:13:04 GMT
ENV REDMINE_DOWNLOAD_MD5=6ca9284fa1c3571f6c83dd0e0d0fec1b
# Thu, 21 Jun 2018 10:13:11 GMT
RUN wget -O redmine.tar.gz "https://www.redmine.org/releases/redmine-${REDMINE_VERSION}.tar.gz" 	&& echo "$REDMINE_DOWNLOAD_MD5 redmine.tar.gz" | md5sum -c - 	&& tar -xvf redmine.tar.gz --strip-components=1 	&& rm redmine.tar.gz files/delete.me log/delete.me 	&& mkdir -p tmp/pdf public/plugin_assets 	&& chown -R redmine:redmine ./
# Thu, 21 Jun 2018 10:23:38 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		freetds-dev 		gcc 		libmagickcore-dev 		libmagickwand-dev 		libmysqlclient-dev 		libpq-dev 		libsqlite3-dev 		make 		patch 	; 	rm -rf /var/lib/apt/lists/*; 		bundle install --without development test; 	for adapter in mysql2 postgresql sqlserver sqlite3; do 		echo "$RAILS_ENV:" > ./config/database.yml; 		echo "  adapter: $adapter" >> ./config/database.yml; 		bundle install --without development test; 		cp Gemfile.lock "Gemfile.lock.${adapter}"; 	done; 	rm ./config/database.yml; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| grep -v '^/usr/local/' 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false
# Thu, 21 Jun 2018 10:23:39 GMT
VOLUME [/usr/src/redmine/files]
# Thu, 21 Jun 2018 10:23:41 GMT
COPY file:8064eeba1336402e59165b07c73d0734f58aa7e83e3c0a42b6888098f2e2c11d in / 
# Thu, 21 Jun 2018 10:23:42 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Thu, 21 Jun 2018 10:23:48 GMT
EXPOSE 3000/tcp
# Thu, 21 Jun 2018 10:23:52 GMT
CMD ["rails" "server" "-b" "0.0.0.0"]
```

-	Layers:
	-	`sha256:2668401c9f940b1d6b03e5f0086fa248cb957610ef9a7c79983d2fb0707ec76c`  
		Last Modified: Sat, 28 Apr 2018 08:24:36 GMT  
		Size: 53.4 MB (53392811 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ab444779be019b7a69946ce8e93e0062d82eedfe747470714b266730847305b0`  
		Last Modified: Sat, 28 Apr 2018 12:15:08 GMT  
		Size: 10.1 MB (10137971 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b6bfab4f27e54de1711e2752ce393ce141c20aef64a8cd42d95a20585d28fa73`  
		Last Modified: Sat, 28 Apr 2018 12:15:04 GMT  
		Size: 207.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:427cea24f278c9fb59c1f03139f4faacc225e025e81c234b072a9be00d7303b9`  
		Last Modified: Thu, 24 May 2018 11:47:28 GMT  
		Size: 35.0 MB (34990674 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8f9b55c0bcd4e1cd34161e4082c080b6406cb9d2a5356f6372aa7aef7419c1fd`  
		Last Modified: Fri, 25 May 2018 09:34:57 GMT  
		Size: 182.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d097d01cbc428cafdec3f56751d05f3cff334f5f8d610985b33656cd96659ce0`  
		Last Modified: Sat, 26 May 2018 10:29:47 GMT  
		Size: 2.1 KB (2102 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e6f5223afc6c5aee4dac4d6916f3de788e99fdaa39e3a3972fcbc563b8b58e85`  
		Last Modified: Sat, 26 May 2018 10:29:49 GMT  
		Size: 13.1 MB (13113543 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:09e2ae7242f7589196ea140019067ffef32ac76d1f22843f1d2427c6dc25044a`  
		Last Modified: Sat, 26 May 2018 10:29:45 GMT  
		Size: 469.8 KB (469848 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:684692c2a7707c733b3abc86089324168108f8e6fc848dcbc75959ecf1fe2b3e`  
		Last Modified: Sat, 26 May 2018 10:29:44 GMT  
		Size: 8.6 KB (8643 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:42c79d69aae34e53499a21afea2693b4bc013077028d74b0b5e30d95c4105f34`  
		Last Modified: Thu, 21 Jun 2018 10:25:20 GMT  
		Size: 58.6 MB (58566683 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9bb1e9e94ddcd0a664c099e296f3fb45d031da33a37bd806e710b1816d91e0c9`  
		Last Modified: Thu, 21 Jun 2018 10:25:04 GMT  
		Size: 172.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e40aeae3af6a508ff0f1e24b567dc752b887f1b87d9a60edb589858ec5222f10`  
		Last Modified: Thu, 21 Jun 2018 10:25:05 GMT  
		Size: 2.4 MB (2394466 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:164e6a8521582589d2cbc4a3909a075fafa9145a5628e972124540e0781d4ab4`  
		Last Modified: Thu, 21 Jun 2018 10:25:18 GMT  
		Size: 70.9 MB (70926240 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:518b0c78f3135cc2397f5518e13c56787bf4a42976bbfd520ec9ef66009e4149`  
		Last Modified: Thu, 21 Jun 2018 10:25:04 GMT  
		Size: 1.8 KB (1794 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `redmine:3.3` - linux; s390x

```console
$ docker pull redmine@sha256:028d5b0ca4cf97269aee1871190b401d8228a1927768549ad602c3bf1151b37d
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **251.2 MB (251229131 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:dac71d9197cf213eea8005de46c01f8589f639a2eb5a1b2c73aaefef5ef483ab`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["rails","server","-b","0.0.0.0"]`

```dockerfile
# Sat, 28 Apr 2018 11:42:31 GMT
ADD file:ac1cfec75c7e1898f2c9b7d17653da3684fdda7d14440ce16f1939bb66105cdc in / 
# Sat, 28 Apr 2018 11:42:31 GMT
CMD ["bash"]
# Sat, 28 Apr 2018 15:34:23 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Sat, 28 Apr 2018 15:34:24 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Sat, 28 Apr 2018 15:46:52 GMT
ENV RUBY_MAJOR=2.3
# Sat, 28 Apr 2018 15:46:52 GMT
ENV RUBY_VERSION=2.3.7
# Sat, 28 Apr 2018 15:46:52 GMT
ENV RUBY_DOWNLOAD_SHA256=c61f8f2b9d3ffff5567e186421fa191f0d5e7c2b189b426bb84498825d548edb
# Thu, 24 May 2018 13:34:21 GMT
ENV RUBYGEMS_VERSION=2.7.7
# Thu, 24 May 2018 13:34:21 GMT
ENV BUNDLER_VERSION=1.16.2
# Thu, 24 May 2018 13:36:59 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		dpkg-dev 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 		xz-utils 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& dpkg-query --show --showformat '${package}\n' 		| grep -P '^libreadline\d+$' 		| xargs apt-mark manual 	&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force 	&& rm -r /root/.gem/
# Thu, 24 May 2018 13:36:59 GMT
ENV GEM_HOME=/usr/local/bundle
# Fri, 25 May 2018 11:59:37 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Fri, 25 May 2018 11:59:37 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/bundle/gems/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 25 May 2018 11:59:38 GMT
RUN mkdir -p "$GEM_HOME" && chmod 777 "$GEM_HOME"
# Fri, 25 May 2018 11:59:38 GMT
CMD ["irb"]
# Sat, 26 May 2018 13:30:39 GMT
RUN groupadd -r redmine && useradd -r -g redmine redmine
# Sat, 26 May 2018 13:30:50 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		wget 	&& rm -rf /var/lib/apt/lists/*
# Sat, 26 May 2018 13:30:50 GMT
ENV GOSU_VERSION=1.10
# Sat, 26 May 2018 13:30:52 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Sat, 26 May 2018 13:30:52 GMT
ENV TINI_VERSION=v0.16.1
# Sat, 26 May 2018 13:30:53 GMT
RUN set -x 	&& wget -O /usr/local/bin/tini "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/tini.asc "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5 	&& gpg --batch --verify /usr/local/bin/tini.asc /usr/local/bin/tini 	&& rm -r "$GNUPGHOME" /usr/local/bin/tini.asc 	&& chmod +x /usr/local/bin/tini 	&& tini -h
# Thu, 21 Jun 2018 13:44:33 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		imagemagick 		mercurial 		openssh-client 		subversion 	&& rm -rf /var/lib/apt/lists/*
# Thu, 21 Jun 2018 13:44:34 GMT
ENV RAILS_ENV=production
# Thu, 21 Jun 2018 13:44:34 GMT
WORKDIR /usr/src/redmine
# Thu, 21 Jun 2018 13:44:34 GMT
ENV REDMINE_VERSION=3.3.8
# Thu, 21 Jun 2018 13:44:35 GMT
ENV REDMINE_DOWNLOAD_MD5=6ca9284fa1c3571f6c83dd0e0d0fec1b
# Thu, 21 Jun 2018 13:44:38 GMT
RUN wget -O redmine.tar.gz "https://www.redmine.org/releases/redmine-${REDMINE_VERSION}.tar.gz" 	&& echo "$REDMINE_DOWNLOAD_MD5 redmine.tar.gz" | md5sum -c - 	&& tar -xvf redmine.tar.gz --strip-components=1 	&& rm redmine.tar.gz files/delete.me log/delete.me 	&& mkdir -p tmp/pdf public/plugin_assets 	&& chown -R redmine:redmine ./
# Thu, 21 Jun 2018 13:47:09 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		freetds-dev 		gcc 		libmagickcore-dev 		libmagickwand-dev 		libmysqlclient-dev 		libpq-dev 		libsqlite3-dev 		make 		patch 	; 	rm -rf /var/lib/apt/lists/*; 		bundle install --without development test; 	for adapter in mysql2 postgresql sqlserver sqlite3; do 		echo "$RAILS_ENV:" > ./config/database.yml; 		echo "  adapter: $adapter" >> ./config/database.yml; 		bundle install --without development test; 		cp Gemfile.lock "Gemfile.lock.${adapter}"; 	done; 	rm ./config/database.yml; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| grep -v '^/usr/local/' 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false
# Thu, 21 Jun 2018 13:47:12 GMT
VOLUME [/usr/src/redmine/files]
# Thu, 21 Jun 2018 13:47:13 GMT
COPY file:8064eeba1336402e59165b07c73d0734f58aa7e83e3c0a42b6888098f2e2c11d in / 
# Thu, 21 Jun 2018 13:47:14 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Thu, 21 Jun 2018 13:47:14 GMT
EXPOSE 3000/tcp
# Thu, 21 Jun 2018 13:47:14 GMT
CMD ["rails" "server" "-b" "0.0.0.0"]
```

-	Layers:
	-	`sha256:e0524893a6d25f3e36c190fea678ecf1845e7c0d2ba833b077a429d64b943e0a`  
		Last Modified: Sat, 28 Apr 2018 11:47:52 GMT  
		Size: 54.5 MB (54465857 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:61347f1daff97305b17924679d0a40043c3c68c04ecd38580c03a9f5f14cc025`  
		Last Modified: Sat, 28 Apr 2018 16:00:45 GMT  
		Size: 10.0 MB (9963110 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4516576626d0afc4ce307a23343efc17d8fa199788465d6fb1966c6e38405270`  
		Last Modified: Sat, 28 Apr 2018 16:00:42 GMT  
		Size: 205.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:688703125c86a49bcd0cb37f53b8cac626f9955a87e6b53ea276458c812556a5`  
		Last Modified: Thu, 24 May 2018 13:53:06 GMT  
		Size: 37.8 MB (37834362 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:efaa249cd8ff410a3388bda85a23d5cbb433c832a6d8d48f9ea2657e4bf3fc74`  
		Last Modified: Fri, 25 May 2018 12:11:35 GMT  
		Size: 148.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:94de6c1f93af7a53a7462885f531826d15d58754eb2331e74481ca1feb375240`  
		Last Modified: Sat, 26 May 2018 13:35:04 GMT  
		Size: 2.1 KB (2108 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:99f7717f21c5fe51d9b4a0431eb42177a38a55ce86b8a91baf6844a2494316fc`  
		Last Modified: Sat, 26 May 2018 13:35:06 GMT  
		Size: 13.1 MB (13130026 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:801facac889b0875723265ee31a416dd8d2ebe6319baa73274d5e95735f61768`  
		Last Modified: Sat, 26 May 2018 13:35:03 GMT  
		Size: 486.8 KB (486830 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cfcfe324efe956c80846c306ea43e06cd3a7ecae28bd7083b7ffd7164f74a6b0`  
		Last Modified: Sat, 26 May 2018 13:35:03 GMT  
		Size: 8.6 KB (8629 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:eadd5af9bd5bd5e656cec7e9a9b27e84d8b168bbad3e06d90f5e18b1b7f71aff`  
		Last Modified: Thu, 21 Jun 2018 13:48:18 GMT  
		Size: 59.5 MB (59533442 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:72e764ca1a11cc27db3156d1dff72273d8e154ac5e070d472388d461ae4f0a93`  
		Last Modified: Thu, 21 Jun 2018 13:48:01 GMT  
		Size: 140.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7dd7e5240971a254b02cde3d738278621464164066f0f44fc13df12d4753d41e`  
		Last Modified: Thu, 21 Jun 2018 13:48:02 GMT  
		Size: 2.4 MB (2394068 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2d8c82c24194cfc982368473f00ebb8ab401c4ac53c7d36d9cf339250812dd45`  
		Last Modified: Thu, 21 Jun 2018 13:48:18 GMT  
		Size: 73.4 MB (73408413 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:69ba76ad79cc8fb20b6bb09792cfb6e98126a9e63f108db51c97d67bcf079c24`  
		Last Modified: Thu, 21 Jun 2018 13:48:01 GMT  
		Size: 1.8 KB (1793 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `redmine:3.3.8`

```console
$ docker pull redmine@sha256:63d96aa21cbb8797c17f79a1e435270dbcd0ad7473be3bc55c9c7d2187d16d3d
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm variant v5
	-	linux; arm variant v7
	-	linux; arm64 variant v8
	-	linux; 386
	-	linux; ppc64le
	-	linux; s390x

### `redmine:3.3.8` - linux; amd64

```console
$ docker pull redmine@sha256:c8a3c4d82ee1def1fd7625dfe0026b0b9f2dc3c148d226f49e1a70238eaadb0d
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **244.7 MB (244669656 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:87ac1f743add57ad84817ae2e347c7a4edc919be1be31587c6356c45c7c4809a`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["rails","server","-b","0.0.0.0"]`

```dockerfile
# Sat, 28 Apr 2018 06:44:15 GMT
ADD file:3e6141c0c9cb74b14a281eb3ab7aaf162a625733e652c3948b323bb2ec8b4343 in / 
# Sat, 28 Apr 2018 06:44:16 GMT
CMD ["bash"]
# Sun, 29 Apr 2018 16:52:40 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Sun, 29 Apr 2018 16:52:41 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Sun, 29 Apr 2018 17:58:22 GMT
ENV RUBY_MAJOR=2.3
# Sun, 29 Apr 2018 17:58:22 GMT
ENV RUBY_VERSION=2.3.7
# Sun, 29 Apr 2018 17:58:22 GMT
ENV RUBY_DOWNLOAD_SHA256=c61f8f2b9d3ffff5567e186421fa191f0d5e7c2b189b426bb84498825d548edb
# Thu, 24 May 2018 01:47:00 GMT
ENV RUBYGEMS_VERSION=2.7.7
# Thu, 24 May 2018 01:47:00 GMT
ENV BUNDLER_VERSION=1.16.2
# Thu, 24 May 2018 01:49:52 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		dpkg-dev 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 		xz-utils 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& dpkg-query --show --showformat '${package}\n' 		| grep -P '^libreadline\d+$' 		| xargs apt-mark manual 	&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force 	&& rm -r /root/.gem/
# Thu, 24 May 2018 01:49:52 GMT
ENV GEM_HOME=/usr/local/bundle
# Thu, 24 May 2018 21:08:58 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Thu, 24 May 2018 21:08:58 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/bundle/gems/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Thu, 24 May 2018 21:08:59 GMT
RUN mkdir -p "$GEM_HOME" && chmod 777 "$GEM_HOME"
# Thu, 24 May 2018 21:08:59 GMT
CMD ["irb"]
# Fri, 25 May 2018 22:48:33 GMT
RUN groupadd -r redmine && useradd -r -g redmine redmine
# Fri, 25 May 2018 22:48:49 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		wget 	&& rm -rf /var/lib/apt/lists/*
# Fri, 25 May 2018 22:48:49 GMT
ENV GOSU_VERSION=1.10
# Fri, 25 May 2018 22:48:53 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Fri, 25 May 2018 22:48:53 GMT
ENV TINI_VERSION=v0.16.1
# Fri, 25 May 2018 22:48:55 GMT
RUN set -x 	&& wget -O /usr/local/bin/tini "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/tini.asc "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5 	&& gpg --batch --verify /usr/local/bin/tini.asc /usr/local/bin/tini 	&& rm -r "$GNUPGHOME" /usr/local/bin/tini.asc 	&& chmod +x /usr/local/bin/tini 	&& tini -h
# Wed, 20 Jun 2018 21:39:59 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		imagemagick 		mercurial 		openssh-client 		subversion 	&& rm -rf /var/lib/apt/lists/*
# Wed, 20 Jun 2018 21:40:00 GMT
ENV RAILS_ENV=production
# Wed, 20 Jun 2018 21:40:00 GMT
WORKDIR /usr/src/redmine
# Wed, 20 Jun 2018 21:40:00 GMT
ENV REDMINE_VERSION=3.3.8
# Wed, 20 Jun 2018 21:40:00 GMT
ENV REDMINE_DOWNLOAD_MD5=6ca9284fa1c3571f6c83dd0e0d0fec1b
# Wed, 20 Jun 2018 21:40:05 GMT
RUN wget -O redmine.tar.gz "https://www.redmine.org/releases/redmine-${REDMINE_VERSION}.tar.gz" 	&& echo "$REDMINE_DOWNLOAD_MD5 redmine.tar.gz" | md5sum -c - 	&& tar -xvf redmine.tar.gz --strip-components=1 	&& rm redmine.tar.gz files/delete.me log/delete.me 	&& mkdir -p tmp/pdf public/plugin_assets 	&& chown -R redmine:redmine ./
# Wed, 20 Jun 2018 21:42:41 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		freetds-dev 		gcc 		libmagickcore-dev 		libmagickwand-dev 		libmysqlclient-dev 		libpq-dev 		libsqlite3-dev 		make 		patch 	; 	rm -rf /var/lib/apt/lists/*; 		bundle install --without development test; 	for adapter in mysql2 postgresql sqlserver sqlite3; do 		echo "$RAILS_ENV:" > ./config/database.yml; 		echo "  adapter: $adapter" >> ./config/database.yml; 		bundle install --without development test; 		cp Gemfile.lock "Gemfile.lock.${adapter}"; 	done; 	rm ./config/database.yml; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| grep -v '^/usr/local/' 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false
# Wed, 20 Jun 2018 21:42:42 GMT
VOLUME [/usr/src/redmine/files]
# Wed, 20 Jun 2018 21:42:42 GMT
COPY file:8064eeba1336402e59165b07c73d0734f58aa7e83e3c0a42b6888098f2e2c11d in / 
# Wed, 20 Jun 2018 21:42:42 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Wed, 20 Jun 2018 21:42:43 GMT
EXPOSE 3000/tcp
# Wed, 20 Jun 2018 21:42:43 GMT
CMD ["rails" "server" "-b" "0.0.0.0"]
```

-	Layers:
	-	`sha256:3d77ce4481b119f00e53bee9b4a443469c42c224db954ddaa2e6b74cd73cd5d0`  
		Last Modified: Sat, 28 Apr 2018 08:24:47 GMT  
		Size: 54.3 MB (54262566 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:05a78650ca91970038096c478f5bc7b8155cf0226db13c86ccf40e0e476e23d5`  
		Last Modified: Sun, 29 Apr 2018 19:33:59 GMT  
		Size: 10.2 MB (10168983 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:860996a55f7fba99ae60e7be5fc25d885d982031d74467b9bcfc84f96e72def6`  
		Last Modified: Sun, 29 Apr 2018 19:33:57 GMT  
		Size: 205.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4b80dc12656f673e52960efe49e4f711be35249c76bd015018e7af9b261f65b9`  
		Last Modified: Thu, 24 May 2018 02:06:58 GMT  
		Size: 33.9 MB (33927309 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:608515211c40a538c0165044109a887c946268f6836b7a0486f709e1e1259ae1`  
		Last Modified: Thu, 24 May 2018 21:19:34 GMT  
		Size: 148.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1bc2ef993469835c8b5e39e0fdf1357175ab9b0c5558dc0414417a806cb06c50`  
		Last Modified: Fri, 25 May 2018 22:54:40 GMT  
		Size: 2.1 KB (2106 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:39a9802640b3283085a975cdd520f7885f034b870e41c195867aa9dbf7d432f2`  
		Last Modified: Fri, 25 May 2018 22:54:41 GMT  
		Size: 13.0 MB (12967854 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:01fa73fc0f4c5f19de0704b75842838d7e89f9900b9680dfedb39079c48c90cd`  
		Last Modified: Fri, 25 May 2018 22:54:38 GMT  
		Size: 500.7 KB (500674 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:11dd6ceb02ca6b57f8bdacbf04a2b26d8b28bfc691b961e9d5ca75ce90e65630`  
		Last Modified: Fri, 25 May 2018 22:54:37 GMT  
		Size: 8.5 KB (8510 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4bbed35f8bbe747dfc26c7ecda6a7dd05b490ecb9f1a66732e27fdf249e1e13e`  
		Last Modified: Wed, 20 Jun 2018 21:51:32 GMT  
		Size: 59.7 MB (59701163 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:66fb5daf0fa81dd94ce0c137679f0d0ddd03d68cd756cf9bef4809b7b07f2e53`  
		Last Modified: Wed, 20 Jun 2018 21:51:15 GMT  
		Size: 141.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8f72a72d48f560a273b47fa716ca9fed3828c5ed7be3462882f55bf02edb3c4c`  
		Last Modified: Wed, 20 Jun 2018 21:51:16 GMT  
		Size: 2.4 MB (2394059 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d28265a8c4bce8ed41c9ce7e5bc6eab27c2c9272ba835e52da389bd2a418c14e`  
		Last Modified: Wed, 20 Jun 2018 21:51:24 GMT  
		Size: 70.7 MB (70734145 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0c7ae25302669301e0ba8398fe0561a195cd5e8303c31bc3fab9c17cbe84c918`  
		Last Modified: Wed, 20 Jun 2018 21:51:15 GMT  
		Size: 1.8 KB (1793 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `redmine:3.3.8` - linux; arm variant v5

```console
$ docker pull redmine@sha256:92343ba20aba16b34f87e429c598372a25ca5f666e6d26dba40e9d941a9e4342
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **237.2 MB (237229856 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:dceebaa3f9d8a2c106fa2e07de34e0be66c0cfb207329a26684620d99c2d1e36`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["rails","server","-b","0.0.0.0"]`

```dockerfile
# Sat, 28 Apr 2018 08:49:23 GMT
ADD file:2d2cd360e66aeff5557c7e7117985a00d109278c3f456ee970afcc9a46483264 in / 
# Sat, 28 Apr 2018 08:49:23 GMT
CMD ["bash"]
# Sat, 28 Apr 2018 11:50:09 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Sat, 28 Apr 2018 11:50:10 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Sat, 28 Apr 2018 12:10:57 GMT
ENV RUBY_MAJOR=2.3
# Sat, 28 Apr 2018 12:10:58 GMT
ENV RUBY_VERSION=2.3.7
# Sat, 28 Apr 2018 12:10:58 GMT
ENV RUBY_DOWNLOAD_SHA256=c61f8f2b9d3ffff5567e186421fa191f0d5e7c2b189b426bb84498825d548edb
# Thu, 24 May 2018 11:17:12 GMT
ENV RUBYGEMS_VERSION=2.7.7
# Thu, 24 May 2018 11:17:12 GMT
ENV BUNDLER_VERSION=1.16.2
# Thu, 24 May 2018 11:21:41 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		dpkg-dev 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 		xz-utils 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& dpkg-query --show --showformat '${package}\n' 		| grep -P '^libreadline\d+$' 		| xargs apt-mark manual 	&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force 	&& rm -r /root/.gem/
# Thu, 24 May 2018 11:21:42 GMT
ENV GEM_HOME=/usr/local/bundle
# Fri, 25 May 2018 09:10:52 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Fri, 25 May 2018 09:10:52 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/bundle/gems/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 25 May 2018 09:10:53 GMT
RUN mkdir -p "$GEM_HOME" && chmod 777 "$GEM_HOME"
# Fri, 25 May 2018 09:10:53 GMT
CMD ["irb"]
# Sat, 26 May 2018 10:11:34 GMT
RUN groupadd -r redmine && useradd -r -g redmine redmine
# Sat, 26 May 2018 10:12:02 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		wget 	&& rm -rf /var/lib/apt/lists/*
# Sat, 26 May 2018 10:12:02 GMT
ENV GOSU_VERSION=1.10
# Sat, 26 May 2018 10:12:04 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Sat, 26 May 2018 10:12:05 GMT
ENV TINI_VERSION=v0.16.1
# Sat, 26 May 2018 10:12:06 GMT
RUN set -x 	&& wget -O /usr/local/bin/tini "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/tini.asc "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5 	&& gpg --batch --verify /usr/local/bin/tini.asc /usr/local/bin/tini 	&& rm -r "$GNUPGHOME" /usr/local/bin/tini.asc 	&& chmod +x /usr/local/bin/tini 	&& tini -h
# Thu, 21 Jun 2018 09:41:25 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		imagemagick 		mercurial 		openssh-client 		subversion 	&& rm -rf /var/lib/apt/lists/*
# Thu, 21 Jun 2018 09:41:26 GMT
ENV RAILS_ENV=production
# Thu, 21 Jun 2018 09:41:26 GMT
WORKDIR /usr/src/redmine
# Thu, 21 Jun 2018 09:41:27 GMT
ENV REDMINE_VERSION=3.3.8
# Thu, 21 Jun 2018 09:41:27 GMT
ENV REDMINE_DOWNLOAD_MD5=6ca9284fa1c3571f6c83dd0e0d0fec1b
# Thu, 21 Jun 2018 09:41:31 GMT
RUN wget -O redmine.tar.gz "https://www.redmine.org/releases/redmine-${REDMINE_VERSION}.tar.gz" 	&& echo "$REDMINE_DOWNLOAD_MD5 redmine.tar.gz" | md5sum -c - 	&& tar -xvf redmine.tar.gz --strip-components=1 	&& rm redmine.tar.gz files/delete.me log/delete.me 	&& mkdir -p tmp/pdf public/plugin_assets 	&& chown -R redmine:redmine ./
# Thu, 21 Jun 2018 09:46:16 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		freetds-dev 		gcc 		libmagickcore-dev 		libmagickwand-dev 		libmysqlclient-dev 		libpq-dev 		libsqlite3-dev 		make 		patch 	; 	rm -rf /var/lib/apt/lists/*; 		bundle install --without development test; 	for adapter in mysql2 postgresql sqlserver sqlite3; do 		echo "$RAILS_ENV:" > ./config/database.yml; 		echo "  adapter: $adapter" >> ./config/database.yml; 		bundle install --without development test; 		cp Gemfile.lock "Gemfile.lock.${adapter}"; 	done; 	rm ./config/database.yml; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| grep -v '^/usr/local/' 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false
# Thu, 21 Jun 2018 09:46:17 GMT
VOLUME [/usr/src/redmine/files]
# Thu, 21 Jun 2018 09:46:17 GMT
COPY file:8064eeba1336402e59165b07c73d0734f58aa7e83e3c0a42b6888098f2e2c11d in / 
# Thu, 21 Jun 2018 09:46:18 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Thu, 21 Jun 2018 09:46:18 GMT
EXPOSE 3000/tcp
# Thu, 21 Jun 2018 09:46:18 GMT
CMD ["rails" "server" "-b" "0.0.0.0"]
```

-	Layers:
	-	`sha256:81fc0826192f72abe617753d378af4047dbce89faf17cdab9166877006a25d8e`  
		Last Modified: Sat, 28 Apr 2018 08:57:10 GMT  
		Size: 52.5 MB (52456037 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2119f18fa6f270436c891e0c459923ae24657bf4a8be20cfcfe964e7aa64b7b2`  
		Last Modified: Sat, 28 Apr 2018 12:31:30 GMT  
		Size: 9.1 MB (9119888 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:51757db9404a98c26c96cb6b65e8c7893c1e1b5ea9774a5786abe9ec88468cf3`  
		Last Modified: Sat, 28 Apr 2018 12:31:26 GMT  
		Size: 206.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:65104c91b9394bb23a8afc0395aec5f928cef61120d6d7944e1f0081d2d231f2`  
		Last Modified: Thu, 24 May 2018 11:32:45 GMT  
		Size: 32.8 MB (32753332 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1c955480d3d1a7c63c64c0454f707a6515b7b8686a525442b2406c4c615cdcb0`  
		Last Modified: Fri, 25 May 2018 09:20:24 GMT  
		Size: 183.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4c0ad0ba38abaac1a64d49025488f6bc460bf3105f79cae5793dab1ffe9fc05d`  
		Last Modified: Sat, 26 May 2018 10:19:18 GMT  
		Size: 2.1 KB (2091 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4c0908f49977601b24ae47a6cd030bb728e452c6f92053f8681bc335b2ef3be6`  
		Last Modified: Sat, 26 May 2018 10:19:21 GMT  
		Size: 12.8 MB (12772579 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e0dd8d7f14e3d1ed9c471b63cb02d01ca2b1817e9b7baec789f437aabcd66756`  
		Last Modified: Sat, 26 May 2018 10:19:18 GMT  
		Size: 491.1 KB (491127 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2f1e4c5939feb4934132090f2eedf5491a004f003896731e342ad80523b4f1b4`  
		Last Modified: Sat, 26 May 2018 10:19:17 GMT  
		Size: 7.8 KB (7850 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7128acf94002efc8a4fb19efdb72617c1d64c7e48d9d23e1408f5c92b06b2eab`  
		Last Modified: Thu, 21 Jun 2018 09:47:46 GMT  
		Size: 57.1 MB (57055759 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ca149da96b14b046d83a61e3c1443c0b348543e147692f71090fafb13bf161cf`  
		Last Modified: Thu, 21 Jun 2018 09:47:26 GMT  
		Size: 172.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cbc43f27e5e16e73345b1ab00edafc9a5af24c7ee83f63f8e3ce0fa97aecaf3f`  
		Last Modified: Thu, 21 Jun 2018 09:47:28 GMT  
		Size: 2.4 MB (2394464 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:29356b7872aeabc36ff2e1aeebc2e4d2701367688f473d02345313a82af34636`  
		Last Modified: Thu, 21 Jun 2018 09:47:44 GMT  
		Size: 70.2 MB (70174375 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0fc71c97d263b9ceaf94453a2e90af7803854eb53ee14f1143aff7c29e6b8f3e`  
		Last Modified: Thu, 21 Jun 2018 09:47:27 GMT  
		Size: 1.8 KB (1793 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `redmine:3.3.8` - linux; arm variant v7

```console
$ docker pull redmine@sha256:0fc15bf64eac635c89adadd3806ff5afe8bc04610823ca1d50fe6ba086a7537e
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **231.6 MB (231578856 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:49b991834c05d7380cb1d103a1b162a258700c1d7c6a10b67c2997ff15714b8c`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["rails","server","-b","0.0.0.0"]`

```dockerfile
# Sat, 28 Apr 2018 11:59:05 GMT
ADD file:4e9c283075c120ce66f83bf541b0aeaa8a46f74c21d38e4ab1578e7f1b892823 in / 
# Sat, 28 Apr 2018 11:59:05 GMT
CMD ["bash"]
# Sat, 28 Apr 2018 15:40:52 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Sat, 28 Apr 2018 15:40:56 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Sat, 28 Apr 2018 16:01:00 GMT
ENV RUBY_MAJOR=2.3
# Sat, 28 Apr 2018 16:01:00 GMT
ENV RUBY_VERSION=2.3.7
# Sat, 28 Apr 2018 16:01:00 GMT
ENV RUBY_DOWNLOAD_SHA256=c61f8f2b9d3ffff5567e186421fa191f0d5e7c2b189b426bb84498825d548edb
# Thu, 24 May 2018 13:32:45 GMT
ENV RUBYGEMS_VERSION=2.7.7
# Thu, 24 May 2018 13:32:45 GMT
ENV BUNDLER_VERSION=1.16.2
# Thu, 24 May 2018 13:36:52 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		dpkg-dev 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 		xz-utils 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& dpkg-query --show --showformat '${package}\n' 		| grep -P '^libreadline\d+$' 		| xargs apt-mark manual 	&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force 	&& rm -r /root/.gem/
# Thu, 24 May 2018 13:36:58 GMT
ENV GEM_HOME=/usr/local/bundle
# Fri, 25 May 2018 12:28:58 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Fri, 25 May 2018 12:28:58 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/bundle/gems/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 25 May 2018 12:28:59 GMT
RUN mkdir -p "$GEM_HOME" && chmod 777 "$GEM_HOME"
# Fri, 25 May 2018 12:28:59 GMT
CMD ["irb"]
# Sat, 26 May 2018 12:31:26 GMT
RUN groupadd -r redmine && useradd -r -g redmine redmine
# Sat, 26 May 2018 12:31:53 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		wget 	&& rm -rf /var/lib/apt/lists/*
# Sat, 26 May 2018 12:31:53 GMT
ENV GOSU_VERSION=1.10
# Sat, 26 May 2018 12:31:55 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Sat, 26 May 2018 12:31:55 GMT
ENV TINI_VERSION=v0.16.1
# Sat, 26 May 2018 12:31:57 GMT
RUN set -x 	&& wget -O /usr/local/bin/tini "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/tini.asc "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5 	&& gpg --batch --verify /usr/local/bin/tini.asc /usr/local/bin/tini 	&& rm -r "$GNUPGHOME" /usr/local/bin/tini.asc 	&& chmod +x /usr/local/bin/tini 	&& tini -h
# Thu, 21 Jun 2018 12:13:23 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		imagemagick 		mercurial 		openssh-client 		subversion 	&& rm -rf /var/lib/apt/lists/*
# Thu, 21 Jun 2018 12:13:24 GMT
ENV RAILS_ENV=production
# Thu, 21 Jun 2018 12:13:24 GMT
WORKDIR /usr/src/redmine
# Thu, 21 Jun 2018 12:13:25 GMT
ENV REDMINE_VERSION=3.3.8
# Thu, 21 Jun 2018 12:13:25 GMT
ENV REDMINE_DOWNLOAD_MD5=6ca9284fa1c3571f6c83dd0e0d0fec1b
# Thu, 21 Jun 2018 12:13:29 GMT
RUN wget -O redmine.tar.gz "https://www.redmine.org/releases/redmine-${REDMINE_VERSION}.tar.gz" 	&& echo "$REDMINE_DOWNLOAD_MD5 redmine.tar.gz" | md5sum -c - 	&& tar -xvf redmine.tar.gz --strip-components=1 	&& rm redmine.tar.gz files/delete.me log/delete.me 	&& mkdir -p tmp/pdf public/plugin_assets 	&& chown -R redmine:redmine ./
# Thu, 21 Jun 2018 12:18:07 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		freetds-dev 		gcc 		libmagickcore-dev 		libmagickwand-dev 		libmysqlclient-dev 		libpq-dev 		libsqlite3-dev 		make 		patch 	; 	rm -rf /var/lib/apt/lists/*; 		bundle install --without development test; 	for adapter in mysql2 postgresql sqlserver sqlite3; do 		echo "$RAILS_ENV:" > ./config/database.yml; 		echo "  adapter: $adapter" >> ./config/database.yml; 		bundle install --without development test; 		cp Gemfile.lock "Gemfile.lock.${adapter}"; 	done; 	rm ./config/database.yml; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| grep -v '^/usr/local/' 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false
# Thu, 21 Jun 2018 12:18:08 GMT
VOLUME [/usr/src/redmine/files]
# Thu, 21 Jun 2018 12:18:08 GMT
COPY file:8064eeba1336402e59165b07c73d0734f58aa7e83e3c0a42b6888098f2e2c11d in / 
# Thu, 21 Jun 2018 12:18:09 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Thu, 21 Jun 2018 12:18:09 GMT
EXPOSE 3000/tcp
# Thu, 21 Jun 2018 12:18:09 GMT
CMD ["rails" "server" "-b" "0.0.0.0"]
```

-	Layers:
	-	`sha256:5c478157e28e3c26a0209484edb518799e1c21863d4700579c010b7203e0537f`  
		Last Modified: Sat, 28 Apr 2018 12:10:24 GMT  
		Size: 50.2 MB (50195697 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:57cc82e3a61290e4bfc39b7ec615f84e7782d645852ff04b0f1077ba3a8d6c85`  
		Last Modified: Sat, 28 Apr 2018 16:21:20 GMT  
		Size: 8.8 MB (8777726 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e60d4b7c236d855ddd6a1f286ece09d909ea721b8959a806142de215e84ad242`  
		Last Modified: Sat, 28 Apr 2018 16:21:17 GMT  
		Size: 207.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:79c49f5f68f7c6a9010b9b38fea693855a4635ca6d5d986d01420ea8d013c707`  
		Last Modified: Thu, 24 May 2018 13:55:41 GMT  
		Size: 32.5 MB (32542173 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:934dc94129d4496ffd10875a2c6058f6396f3efb21926efaaae7ad971facf665`  
		Last Modified: Fri, 25 May 2018 12:43:45 GMT  
		Size: 181.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:caa9a3c5fc967f8b658a66e0ae779ea381e13bc89289dbf72795bb49791fca5b`  
		Last Modified: Sat, 26 May 2018 12:39:04 GMT  
		Size: 2.1 KB (2094 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7b38fd1d46fe67fb5d158cd8c269017e89f4f63f7a5a9d014e13f159ce8a079f`  
		Last Modified: Sat, 26 May 2018 12:39:07 GMT  
		Size: 12.6 MB (12629394 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bbd3f2473b5fd66ce61544076766f578a5b58b36b084154675e2dbf55ffc5fa0`  
		Last Modified: Sat, 26 May 2018 12:39:03 GMT  
		Size: 475.3 KB (475271 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:85f96c619c7aac443df9ee910d0b0eeeafc84458e098f4695326b3a45537298b`  
		Last Modified: Sat, 26 May 2018 12:39:02 GMT  
		Size: 7.3 KB (7313 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:36e4ee90ace2e64cbcc2a2d3e280ad8d331131458bb72bd020c2fa5ecfb82d40`  
		Last Modified: Thu, 21 Jun 2018 12:19:37 GMT  
		Size: 54.7 MB (54698433 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2b85c9b67cd8f1ce20a9c1d3923ed89433a632918570e1d48bbcee0ddfd0aae1`  
		Last Modified: Thu, 21 Jun 2018 12:19:20 GMT  
		Size: 170.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e2d037d38862bafc6fd4f24ca7dfe5d9ca8faf2aeb76bfd10979335acf56806c`  
		Last Modified: Thu, 21 Jun 2018 12:19:22 GMT  
		Size: 2.4 MB (2394445 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:430bc271235e2ac890d803fb99d2fbcf46c6c451e1c64e8d7b496c43f2b3c5d4`  
		Last Modified: Thu, 21 Jun 2018 12:19:36 GMT  
		Size: 69.9 MB (69853959 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:56b845da62bdc2c86bf4bcd0ffe10678696982dfa0fbbfc2a8211b67fe46a4d3`  
		Last Modified: Thu, 21 Jun 2018 12:19:20 GMT  
		Size: 1.8 KB (1793 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `redmine:3.3.8` - linux; arm64 variant v8

```console
$ docker pull redmine@sha256:1f509a8d15a70a347b6a315b32a672a35f031d10a3f3269882be031ae423b951
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **237.1 MB (237077303 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:f79089a322c6f8fe1d38c00e7c0875658f5e1e0f112487af5e3394e40d9a15da`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["rails","server","-b","0.0.0.0"]`

```dockerfile
# Mon, 30 Apr 2018 23:21:38 GMT
ADD file:387c83918422a6546379c4d84818ca3949fcd63aec058da562b08c947a9ed571 in / 
# Mon, 30 Apr 2018 23:21:40 GMT
CMD ["bash"]
# Tue, 01 May 2018 08:41:36 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Tue, 01 May 2018 08:41:41 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Tue, 01 May 2018 09:21:51 GMT
ENV RUBY_MAJOR=2.3
# Tue, 01 May 2018 09:21:51 GMT
ENV RUBY_VERSION=2.3.7
# Tue, 01 May 2018 09:21:52 GMT
ENV RUBY_DOWNLOAD_SHA256=c61f8f2b9d3ffff5567e186421fa191f0d5e7c2b189b426bb84498825d548edb
# Fri, 25 May 2018 17:42:54 GMT
ENV RUBYGEMS_VERSION=2.7.7
# Fri, 25 May 2018 17:42:55 GMT
ENV BUNDLER_VERSION=1.16.2
# Fri, 25 May 2018 17:50:33 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		dpkg-dev 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 		xz-utils 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& dpkg-query --show --showformat '${package}\n' 		| grep -P '^libreadline\d+$' 		| xargs apt-mark manual 	&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force 	&& rm -r /root/.gem/
# Fri, 25 May 2018 17:50:34 GMT
ENV GEM_HOME=/usr/local/bundle
# Fri, 25 May 2018 17:50:35 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Fri, 25 May 2018 17:50:36 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/bundle/gems/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 25 May 2018 17:50:37 GMT
RUN mkdir -p "$GEM_HOME" && chmod 777 "$GEM_HOME"
# Fri, 25 May 2018 17:50:38 GMT
CMD ["irb"]
# Fri, 25 May 2018 21:57:09 GMT
RUN groupadd -r redmine && useradd -r -g redmine redmine
# Fri, 25 May 2018 21:57:32 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		wget 	&& rm -rf /var/lib/apt/lists/*
# Fri, 25 May 2018 21:57:33 GMT
ENV GOSU_VERSION=1.10
# Fri, 25 May 2018 21:57:37 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Fri, 25 May 2018 21:57:37 GMT
ENV TINI_VERSION=v0.16.1
# Fri, 25 May 2018 21:57:41 GMT
RUN set -x 	&& wget -O /usr/local/bin/tini "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/tini.asc "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5 	&& gpg --batch --verify /usr/local/bin/tini.asc /usr/local/bin/tini 	&& rm -r "$GNUPGHOME" /usr/local/bin/tini.asc 	&& chmod +x /usr/local/bin/tini 	&& tini -h
# Thu, 21 Jun 2018 17:15:33 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		imagemagick 		mercurial 		openssh-client 		subversion 	&& rm -rf /var/lib/apt/lists/*
# Thu, 21 Jun 2018 17:15:35 GMT
ENV RAILS_ENV=production
# Thu, 21 Jun 2018 17:15:35 GMT
WORKDIR /usr/src/redmine
# Thu, 21 Jun 2018 17:15:36 GMT
ENV REDMINE_VERSION=3.3.8
# Thu, 21 Jun 2018 17:15:37 GMT
ENV REDMINE_DOWNLOAD_MD5=6ca9284fa1c3571f6c83dd0e0d0fec1b
# Thu, 21 Jun 2018 17:15:42 GMT
RUN wget -O redmine.tar.gz "https://www.redmine.org/releases/redmine-${REDMINE_VERSION}.tar.gz" 	&& echo "$REDMINE_DOWNLOAD_MD5 redmine.tar.gz" | md5sum -c - 	&& tar -xvf redmine.tar.gz --strip-components=1 	&& rm redmine.tar.gz files/delete.me log/delete.me 	&& mkdir -p tmp/pdf public/plugin_assets 	&& chown -R redmine:redmine ./
# Thu, 21 Jun 2018 17:26:43 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		freetds-dev 		gcc 		libmagickcore-dev 		libmagickwand-dev 		libmysqlclient-dev 		libpq-dev 		libsqlite3-dev 		make 		patch 	; 	rm -rf /var/lib/apt/lists/*; 		bundle install --without development test; 	for adapter in mysql2 postgresql sqlserver sqlite3; do 		echo "$RAILS_ENV:" > ./config/database.yml; 		echo "  adapter: $adapter" >> ./config/database.yml; 		bundle install --without development test; 		cp Gemfile.lock "Gemfile.lock.${adapter}"; 	done; 	rm ./config/database.yml; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| grep -v '^/usr/local/' 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false
# Thu, 21 Jun 2018 17:26:44 GMT
VOLUME [/usr/src/redmine/files]
# Thu, 21 Jun 2018 17:26:45 GMT
COPY file:8064eeba1336402e59165b07c73d0734f58aa7e83e3c0a42b6888098f2e2c11d in / 
# Thu, 21 Jun 2018 17:26:46 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Thu, 21 Jun 2018 17:26:47 GMT
EXPOSE 3000/tcp
# Thu, 21 Jun 2018 17:26:47 GMT
CMD ["rails" "server" "-b" "0.0.0.0"]
```

-	Layers:
	-	`sha256:363cfded2ef3921ef972c85cafc77cf16cdcfddfd49782ad4540cb73fd5e57a2`  
		Last Modified: Mon, 30 Apr 2018 23:41:06 GMT  
		Size: 51.4 MB (51446854 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6aeaeeebfa7e2a1e6c69a484a7648b6313aff4bf219767667e43bbfc42bb40d9`  
		Last Modified: Tue, 01 May 2018 09:53:45 GMT  
		Size: 9.3 MB (9343083 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3b78cb3f4882a2b3bf1ecb4fdbe1e145a3ddb80ce1fde62a33ada1beaf12daf8`  
		Last Modified: Tue, 01 May 2018 09:53:41 GMT  
		Size: 205.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ed306b6b25ea2954c71b5a7a802e55dd849a0c4f9d9348974dfcf0aa3a3f4360`  
		Last Modified: Fri, 25 May 2018 18:12:58 GMT  
		Size: 34.0 MB (34023340 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:29958525b6f0d099361441683b4546e9a8fa17728f43cb8cefb616e936646278`  
		Last Modified: Fri, 25 May 2018 18:12:42 GMT  
		Size: 148.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:88dfdd87d35bfc527d1e1fa6e6765f3c543c6bcca388e3ccc197aeea1a620a7d`  
		Last Modified: Fri, 25 May 2018 22:13:20 GMT  
		Size: 2.1 KB (2116 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f8c84422c38a6db49dd44b5227afbaac45429fcf4544ea28aaa3549413795c55`  
		Last Modified: Fri, 25 May 2018 22:13:25 GMT  
		Size: 12.9 MB (12940754 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7f73061b438fd37a1444decd7254737e1c3eec6b552718eed4d0bca7956927e3`  
		Last Modified: Fri, 25 May 2018 22:13:19 GMT  
		Size: 468.7 KB (468693 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9c6169a236f22bae25d63b6d3a1628842abb147c2260fa1ff414f6840e55a9c4`  
		Last Modified: Fri, 25 May 2018 22:13:19 GMT  
		Size: 8.2 KB (8153 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:398742b41291631bc6f968c8cae2468ddd14b9b852af94083d96869eff6854f4`  
		Last Modified: Thu, 21 Jun 2018 17:28:41 GMT  
		Size: 56.2 MB (56167018 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fa9c2b611faef911068e185b9abd88ef0c5b6bdfecb029be9fe7ad4392ab6d45`  
		Last Modified: Thu, 21 Jun 2018 17:28:19 GMT  
		Size: 140.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9ac9acd59689fde9ce96612b78c07d99cdd4eb733d59dd9f750b2524453a81ce`  
		Last Modified: Thu, 21 Jun 2018 17:28:20 GMT  
		Size: 2.4 MB (2394066 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9fd8816d2648d1b0ddd291371cbd9a4c8907dcf114e58191a995f158ff215658`  
		Last Modified: Thu, 21 Jun 2018 17:28:39 GMT  
		Size: 70.3 MB (70280940 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5b5617e5c727381aa5b1aa4acd6061c0b23e79d70c5cea5169d6949554524713`  
		Last Modified: Thu, 21 Jun 2018 17:28:19 GMT  
		Size: 1.8 KB (1793 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `redmine:3.3.8` - linux; 386

```console
$ docker pull redmine@sha256:5ce7cb2d9fd7edd96f1b44d63502d01ca88ba1f1e08cd2c0db2c0da8d23eea5d
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **247.0 MB (247027540 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:b022a1e4e32c7eb479bf6553e707e7fcaf60ec92e49a579cb9e5b558ca135b09`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["rails","server","-b","0.0.0.0"]`

```dockerfile
# Sat, 28 Apr 2018 10:39:32 GMT
ADD file:ce5174f2b2c155a2421fac3ff37a02d9551d5d79e31a541189bcfd2416a6903a in / 
# Sat, 28 Apr 2018 10:39:32 GMT
CMD ["bash"]
# Fri, 01 Jun 2018 14:56:41 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Fri, 01 Jun 2018 14:56:42 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Fri, 01 Jun 2018 15:31:48 GMT
ENV RUBY_MAJOR=2.3
# Fri, 01 Jun 2018 15:31:48 GMT
ENV RUBY_VERSION=2.3.7
# Fri, 01 Jun 2018 15:31:48 GMT
ENV RUBY_DOWNLOAD_SHA256=c61f8f2b9d3ffff5567e186421fa191f0d5e7c2b189b426bb84498825d548edb
# Fri, 01 Jun 2018 15:31:48 GMT
ENV RUBYGEMS_VERSION=2.7.7
# Fri, 01 Jun 2018 15:31:48 GMT
ENV BUNDLER_VERSION=1.16.2
# Fri, 01 Jun 2018 15:37:54 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		dpkg-dev 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 		xz-utils 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& dpkg-query --show --showformat '${package}\n' 		| grep -P '^libreadline\d+$' 		| xargs apt-mark manual 	&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force 	&& rm -r /root/.gem/
# Fri, 01 Jun 2018 15:37:55 GMT
ENV GEM_HOME=/usr/local/bundle
# Fri, 01 Jun 2018 15:37:55 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Fri, 01 Jun 2018 15:37:55 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/bundle/gems/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 01 Jun 2018 15:37:56 GMT
RUN mkdir -p "$GEM_HOME" && chmod 777 "$GEM_HOME"
# Fri, 01 Jun 2018 15:37:56 GMT
CMD ["irb"]
# Fri, 01 Jun 2018 17:21:54 GMT
RUN groupadd -r redmine && useradd -r -g redmine redmine
# Fri, 01 Jun 2018 17:22:48 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		wget 	&& rm -rf /var/lib/apt/lists/*
# Fri, 01 Jun 2018 17:22:48 GMT
ENV GOSU_VERSION=1.10
# Fri, 01 Jun 2018 17:22:55 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Fri, 01 Jun 2018 17:22:55 GMT
ENV TINI_VERSION=v0.16.1
# Fri, 01 Jun 2018 17:22:57 GMT
RUN set -x 	&& wget -O /usr/local/bin/tini "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/tini.asc "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5 	&& gpg --batch --verify /usr/local/bin/tini.asc /usr/local/bin/tini 	&& rm -r "$GNUPGHOME" /usr/local/bin/tini.asc 	&& chmod +x /usr/local/bin/tini 	&& tini -h
# Thu, 21 Jun 2018 11:09:15 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		imagemagick 		mercurial 		openssh-client 		subversion 	&& rm -rf /var/lib/apt/lists/*
# Thu, 21 Jun 2018 11:09:16 GMT
ENV RAILS_ENV=production
# Thu, 21 Jun 2018 11:09:16 GMT
WORKDIR /usr/src/redmine
# Thu, 21 Jun 2018 11:09:16 GMT
ENV REDMINE_VERSION=3.3.8
# Thu, 21 Jun 2018 11:09:17 GMT
ENV REDMINE_DOWNLOAD_MD5=6ca9284fa1c3571f6c83dd0e0d0fec1b
# Thu, 21 Jun 2018 11:09:21 GMT
RUN wget -O redmine.tar.gz "https://www.redmine.org/releases/redmine-${REDMINE_VERSION}.tar.gz" 	&& echo "$REDMINE_DOWNLOAD_MD5 redmine.tar.gz" | md5sum -c - 	&& tar -xvf redmine.tar.gz --strip-components=1 	&& rm redmine.tar.gz files/delete.me log/delete.me 	&& mkdir -p tmp/pdf public/plugin_assets 	&& chown -R redmine:redmine ./
# Thu, 21 Jun 2018 11:14:20 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		freetds-dev 		gcc 		libmagickcore-dev 		libmagickwand-dev 		libmysqlclient-dev 		libpq-dev 		libsqlite3-dev 		make 		patch 	; 	rm -rf /var/lib/apt/lists/*; 		bundle install --without development test; 	for adapter in mysql2 postgresql sqlserver sqlite3; do 		echo "$RAILS_ENV:" > ./config/database.yml; 		echo "  adapter: $adapter" >> ./config/database.yml; 		bundle install --without development test; 		cp Gemfile.lock "Gemfile.lock.${adapter}"; 	done; 	rm ./config/database.yml; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| grep -v '^/usr/local/' 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false
# Thu, 21 Jun 2018 11:14:21 GMT
VOLUME [/usr/src/redmine/files]
# Thu, 21 Jun 2018 11:14:21 GMT
COPY file:8064eeba1336402e59165b07c73d0734f58aa7e83e3c0a42b6888098f2e2c11d in / 
# Thu, 21 Jun 2018 11:14:21 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Thu, 21 Jun 2018 11:14:21 GMT
EXPOSE 3000/tcp
# Thu, 21 Jun 2018 11:14:21 GMT
CMD ["rails" "server" "-b" "0.0.0.0"]
```

-	Layers:
	-	`sha256:05b419d667f793c8c2edf0ff0aec14fc4d66733cdb89957ac89e8bfbeaddd0fa`  
		Last Modified: Sat, 28 Apr 2018 10:44:20 GMT  
		Size: 54.5 MB (54486782 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3d6891754f33e4c1f328ba0f4530fdb8383be81d86d518c6967565db3d8a7d3f`  
		Last Modified: Fri, 01 Jun 2018 15:49:54 GMT  
		Size: 14.9 MB (14942131 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:089cb9bb407565a3373144a74a72a2345d043f8423185a11fe236787bfc2d617`  
		Last Modified: Fri, 01 Jun 2018 15:49:47 GMT  
		Size: 208.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8115b1e634948c41f632ab946ef11b82c36946e3400f38fdf3d7dd4859d47d0e`  
		Last Modified: Fri, 01 Jun 2018 15:53:49 GMT  
		Size: 31.2 MB (31159508 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:540caa681d0f094e7be3241a456e97e445472d53b9431fb5e59ade8a71be700f`  
		Last Modified: Fri, 01 Jun 2018 15:53:35 GMT  
		Size: 148.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:07cfdf83ac422932a67b6ed1ce96a3fa7172fdf95d4535c181c37cb05a0260bb`  
		Last Modified: Fri, 01 Jun 2018 17:32:53 GMT  
		Size: 2.1 KB (2089 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:458b6f451d4b864c82c5b14ad4abe587aeaf6c83e221686868b73d9f5bcfb6fb`  
		Last Modified: Fri, 01 Jun 2018 17:32:57 GMT  
		Size: 13.1 MB (13103058 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d217113ffe8b8cfc32044872c625cc67a4cb9c2f5c8942898aba04d724ff9941`  
		Last Modified: Fri, 01 Jun 2018 17:32:50 GMT  
		Size: 480.6 KB (480577 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9574eda8f6842775047763a6a61375169bd3730b604a896917d234e733fdc541`  
		Last Modified: Fri, 01 Jun 2018 17:32:48 GMT  
		Size: 8.6 KB (8568 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8c2654f85f5b7f668e683128adac1f725054af819ea55c6f7bde0e9cbf4f3a9c`  
		Last Modified: Thu, 21 Jun 2018 11:16:33 GMT  
		Size: 60.6 MB (60580201 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:75c5d16d908b5bbb9dc42ac5c42fbcb38e0339a5e8cccdc517d407fc2d9299c3`  
		Last Modified: Thu, 21 Jun 2018 11:16:04 GMT  
		Size: 139.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:54f02cd2bfa1aa35131d3ec3b391ed666e1c005709b4efde7af0c199606201ca`  
		Last Modified: Thu, 21 Jun 2018 11:16:06 GMT  
		Size: 2.4 MB (2394062 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5de0d5a78758a9d99af5f32a815f02e58d8960b1360797b02b0ccc7d614b1383`  
		Last Modified: Thu, 21 Jun 2018 11:16:27 GMT  
		Size: 69.9 MB (69868276 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9cce7d0a9ac71218e5f6253327d12ad23d12b93d2f5ad9aa9cbe763647a28798`  
		Last Modified: Thu, 21 Jun 2018 11:16:05 GMT  
		Size: 1.8 KB (1793 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `redmine:3.3.8` - linux; ppc64le

```console
$ docker pull redmine@sha256:7b3d314b8d89c31112ed2f34d9253010dbae03fb53229956cabd127be0615bde
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **244.0 MB (244005336 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:13ab9e257d92288192fa7cc584c2c2f9a8641dc51f48b6c033165025237cf80e`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["rails","server","-b","0.0.0.0"]`

```dockerfile
# Sat, 28 Apr 2018 08:17:46 GMT
ADD file:6a4bd4ea54f669286e984ecf8178e1fa7c12c8b6fc0f96e4203ae7a6f99a2279 in / 
# Sat, 28 Apr 2018 08:17:47 GMT
CMD ["bash"]
# Sat, 28 Apr 2018 11:24:06 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Sat, 28 Apr 2018 11:24:08 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Sat, 28 Apr 2018 11:47:05 GMT
ENV RUBY_MAJOR=2.3
# Sat, 28 Apr 2018 11:47:06 GMT
ENV RUBY_VERSION=2.3.7
# Sat, 28 Apr 2018 11:47:06 GMT
ENV RUBY_DOWNLOAD_SHA256=c61f8f2b9d3ffff5567e186421fa191f0d5e7c2b189b426bb84498825d548edb
# Thu, 24 May 2018 11:25:04 GMT
ENV RUBYGEMS_VERSION=2.7.7
# Thu, 24 May 2018 11:25:05 GMT
ENV BUNDLER_VERSION=1.16.2
# Thu, 24 May 2018 11:31:17 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		dpkg-dev 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 		xz-utils 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& dpkg-query --show --showformat '${package}\n' 		| grep -P '^libreadline\d+$' 		| xargs apt-mark manual 	&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force 	&& rm -r /root/.gem/
# Thu, 24 May 2018 11:31:19 GMT
ENV GEM_HOME=/usr/local/bundle
# Fri, 25 May 2018 09:22:00 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Fri, 25 May 2018 09:22:19 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/bundle/gems/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 25 May 2018 09:22:33 GMT
RUN mkdir -p "$GEM_HOME" && chmod 777 "$GEM_HOME"
# Fri, 25 May 2018 09:22:38 GMT
CMD ["irb"]
# Sat, 26 May 2018 10:00:11 GMT
RUN groupadd -r redmine && useradd -r -g redmine redmine
# Sat, 26 May 2018 10:01:14 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		wget 	&& rm -rf /var/lib/apt/lists/*
# Sat, 26 May 2018 10:01:18 GMT
ENV GOSU_VERSION=1.10
# Sat, 26 May 2018 10:01:23 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Sat, 26 May 2018 10:01:26 GMT
ENV TINI_VERSION=v0.16.1
# Sat, 26 May 2018 10:01:29 GMT
RUN set -x 	&& wget -O /usr/local/bin/tini "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/tini.asc "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5 	&& gpg --batch --verify /usr/local/bin/tini.asc /usr/local/bin/tini 	&& rm -r "$GNUPGHOME" /usr/local/bin/tini.asc 	&& chmod +x /usr/local/bin/tini 	&& tini -h
# Thu, 21 Jun 2018 10:13:00 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		imagemagick 		mercurial 		openssh-client 		subversion 	&& rm -rf /var/lib/apt/lists/*
# Thu, 21 Jun 2018 10:13:02 GMT
ENV RAILS_ENV=production
# Thu, 21 Jun 2018 10:13:02 GMT
WORKDIR /usr/src/redmine
# Thu, 21 Jun 2018 10:13:03 GMT
ENV REDMINE_VERSION=3.3.8
# Thu, 21 Jun 2018 10:13:04 GMT
ENV REDMINE_DOWNLOAD_MD5=6ca9284fa1c3571f6c83dd0e0d0fec1b
# Thu, 21 Jun 2018 10:13:11 GMT
RUN wget -O redmine.tar.gz "https://www.redmine.org/releases/redmine-${REDMINE_VERSION}.tar.gz" 	&& echo "$REDMINE_DOWNLOAD_MD5 redmine.tar.gz" | md5sum -c - 	&& tar -xvf redmine.tar.gz --strip-components=1 	&& rm redmine.tar.gz files/delete.me log/delete.me 	&& mkdir -p tmp/pdf public/plugin_assets 	&& chown -R redmine:redmine ./
# Thu, 21 Jun 2018 10:23:38 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		freetds-dev 		gcc 		libmagickcore-dev 		libmagickwand-dev 		libmysqlclient-dev 		libpq-dev 		libsqlite3-dev 		make 		patch 	; 	rm -rf /var/lib/apt/lists/*; 		bundle install --without development test; 	for adapter in mysql2 postgresql sqlserver sqlite3; do 		echo "$RAILS_ENV:" > ./config/database.yml; 		echo "  adapter: $adapter" >> ./config/database.yml; 		bundle install --without development test; 		cp Gemfile.lock "Gemfile.lock.${adapter}"; 	done; 	rm ./config/database.yml; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| grep -v '^/usr/local/' 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false
# Thu, 21 Jun 2018 10:23:39 GMT
VOLUME [/usr/src/redmine/files]
# Thu, 21 Jun 2018 10:23:41 GMT
COPY file:8064eeba1336402e59165b07c73d0734f58aa7e83e3c0a42b6888098f2e2c11d in / 
# Thu, 21 Jun 2018 10:23:42 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Thu, 21 Jun 2018 10:23:48 GMT
EXPOSE 3000/tcp
# Thu, 21 Jun 2018 10:23:52 GMT
CMD ["rails" "server" "-b" "0.0.0.0"]
```

-	Layers:
	-	`sha256:2668401c9f940b1d6b03e5f0086fa248cb957610ef9a7c79983d2fb0707ec76c`  
		Last Modified: Sat, 28 Apr 2018 08:24:36 GMT  
		Size: 53.4 MB (53392811 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ab444779be019b7a69946ce8e93e0062d82eedfe747470714b266730847305b0`  
		Last Modified: Sat, 28 Apr 2018 12:15:08 GMT  
		Size: 10.1 MB (10137971 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b6bfab4f27e54de1711e2752ce393ce141c20aef64a8cd42d95a20585d28fa73`  
		Last Modified: Sat, 28 Apr 2018 12:15:04 GMT  
		Size: 207.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:427cea24f278c9fb59c1f03139f4faacc225e025e81c234b072a9be00d7303b9`  
		Last Modified: Thu, 24 May 2018 11:47:28 GMT  
		Size: 35.0 MB (34990674 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8f9b55c0bcd4e1cd34161e4082c080b6406cb9d2a5356f6372aa7aef7419c1fd`  
		Last Modified: Fri, 25 May 2018 09:34:57 GMT  
		Size: 182.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d097d01cbc428cafdec3f56751d05f3cff334f5f8d610985b33656cd96659ce0`  
		Last Modified: Sat, 26 May 2018 10:29:47 GMT  
		Size: 2.1 KB (2102 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e6f5223afc6c5aee4dac4d6916f3de788e99fdaa39e3a3972fcbc563b8b58e85`  
		Last Modified: Sat, 26 May 2018 10:29:49 GMT  
		Size: 13.1 MB (13113543 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:09e2ae7242f7589196ea140019067ffef32ac76d1f22843f1d2427c6dc25044a`  
		Last Modified: Sat, 26 May 2018 10:29:45 GMT  
		Size: 469.8 KB (469848 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:684692c2a7707c733b3abc86089324168108f8e6fc848dcbc75959ecf1fe2b3e`  
		Last Modified: Sat, 26 May 2018 10:29:44 GMT  
		Size: 8.6 KB (8643 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:42c79d69aae34e53499a21afea2693b4bc013077028d74b0b5e30d95c4105f34`  
		Last Modified: Thu, 21 Jun 2018 10:25:20 GMT  
		Size: 58.6 MB (58566683 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9bb1e9e94ddcd0a664c099e296f3fb45d031da33a37bd806e710b1816d91e0c9`  
		Last Modified: Thu, 21 Jun 2018 10:25:04 GMT  
		Size: 172.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e40aeae3af6a508ff0f1e24b567dc752b887f1b87d9a60edb589858ec5222f10`  
		Last Modified: Thu, 21 Jun 2018 10:25:05 GMT  
		Size: 2.4 MB (2394466 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:164e6a8521582589d2cbc4a3909a075fafa9145a5628e972124540e0781d4ab4`  
		Last Modified: Thu, 21 Jun 2018 10:25:18 GMT  
		Size: 70.9 MB (70926240 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:518b0c78f3135cc2397f5518e13c56787bf4a42976bbfd520ec9ef66009e4149`  
		Last Modified: Thu, 21 Jun 2018 10:25:04 GMT  
		Size: 1.8 KB (1794 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `redmine:3.3.8` - linux; s390x

```console
$ docker pull redmine@sha256:028d5b0ca4cf97269aee1871190b401d8228a1927768549ad602c3bf1151b37d
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **251.2 MB (251229131 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:dac71d9197cf213eea8005de46c01f8589f639a2eb5a1b2c73aaefef5ef483ab`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["rails","server","-b","0.0.0.0"]`

```dockerfile
# Sat, 28 Apr 2018 11:42:31 GMT
ADD file:ac1cfec75c7e1898f2c9b7d17653da3684fdda7d14440ce16f1939bb66105cdc in / 
# Sat, 28 Apr 2018 11:42:31 GMT
CMD ["bash"]
# Sat, 28 Apr 2018 15:34:23 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Sat, 28 Apr 2018 15:34:24 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Sat, 28 Apr 2018 15:46:52 GMT
ENV RUBY_MAJOR=2.3
# Sat, 28 Apr 2018 15:46:52 GMT
ENV RUBY_VERSION=2.3.7
# Sat, 28 Apr 2018 15:46:52 GMT
ENV RUBY_DOWNLOAD_SHA256=c61f8f2b9d3ffff5567e186421fa191f0d5e7c2b189b426bb84498825d548edb
# Thu, 24 May 2018 13:34:21 GMT
ENV RUBYGEMS_VERSION=2.7.7
# Thu, 24 May 2018 13:34:21 GMT
ENV BUNDLER_VERSION=1.16.2
# Thu, 24 May 2018 13:36:59 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		dpkg-dev 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 		xz-utils 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& dpkg-query --show --showformat '${package}\n' 		| grep -P '^libreadline\d+$' 		| xargs apt-mark manual 	&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force 	&& rm -r /root/.gem/
# Thu, 24 May 2018 13:36:59 GMT
ENV GEM_HOME=/usr/local/bundle
# Fri, 25 May 2018 11:59:37 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Fri, 25 May 2018 11:59:37 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/bundle/gems/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 25 May 2018 11:59:38 GMT
RUN mkdir -p "$GEM_HOME" && chmod 777 "$GEM_HOME"
# Fri, 25 May 2018 11:59:38 GMT
CMD ["irb"]
# Sat, 26 May 2018 13:30:39 GMT
RUN groupadd -r redmine && useradd -r -g redmine redmine
# Sat, 26 May 2018 13:30:50 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		wget 	&& rm -rf /var/lib/apt/lists/*
# Sat, 26 May 2018 13:30:50 GMT
ENV GOSU_VERSION=1.10
# Sat, 26 May 2018 13:30:52 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Sat, 26 May 2018 13:30:52 GMT
ENV TINI_VERSION=v0.16.1
# Sat, 26 May 2018 13:30:53 GMT
RUN set -x 	&& wget -O /usr/local/bin/tini "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/tini.asc "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5 	&& gpg --batch --verify /usr/local/bin/tini.asc /usr/local/bin/tini 	&& rm -r "$GNUPGHOME" /usr/local/bin/tini.asc 	&& chmod +x /usr/local/bin/tini 	&& tini -h
# Thu, 21 Jun 2018 13:44:33 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		imagemagick 		mercurial 		openssh-client 		subversion 	&& rm -rf /var/lib/apt/lists/*
# Thu, 21 Jun 2018 13:44:34 GMT
ENV RAILS_ENV=production
# Thu, 21 Jun 2018 13:44:34 GMT
WORKDIR /usr/src/redmine
# Thu, 21 Jun 2018 13:44:34 GMT
ENV REDMINE_VERSION=3.3.8
# Thu, 21 Jun 2018 13:44:35 GMT
ENV REDMINE_DOWNLOAD_MD5=6ca9284fa1c3571f6c83dd0e0d0fec1b
# Thu, 21 Jun 2018 13:44:38 GMT
RUN wget -O redmine.tar.gz "https://www.redmine.org/releases/redmine-${REDMINE_VERSION}.tar.gz" 	&& echo "$REDMINE_DOWNLOAD_MD5 redmine.tar.gz" | md5sum -c - 	&& tar -xvf redmine.tar.gz --strip-components=1 	&& rm redmine.tar.gz files/delete.me log/delete.me 	&& mkdir -p tmp/pdf public/plugin_assets 	&& chown -R redmine:redmine ./
# Thu, 21 Jun 2018 13:47:09 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		freetds-dev 		gcc 		libmagickcore-dev 		libmagickwand-dev 		libmysqlclient-dev 		libpq-dev 		libsqlite3-dev 		make 		patch 	; 	rm -rf /var/lib/apt/lists/*; 		bundle install --without development test; 	for adapter in mysql2 postgresql sqlserver sqlite3; do 		echo "$RAILS_ENV:" > ./config/database.yml; 		echo "  adapter: $adapter" >> ./config/database.yml; 		bundle install --without development test; 		cp Gemfile.lock "Gemfile.lock.${adapter}"; 	done; 	rm ./config/database.yml; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| grep -v '^/usr/local/' 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false
# Thu, 21 Jun 2018 13:47:12 GMT
VOLUME [/usr/src/redmine/files]
# Thu, 21 Jun 2018 13:47:13 GMT
COPY file:8064eeba1336402e59165b07c73d0734f58aa7e83e3c0a42b6888098f2e2c11d in / 
# Thu, 21 Jun 2018 13:47:14 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Thu, 21 Jun 2018 13:47:14 GMT
EXPOSE 3000/tcp
# Thu, 21 Jun 2018 13:47:14 GMT
CMD ["rails" "server" "-b" "0.0.0.0"]
```

-	Layers:
	-	`sha256:e0524893a6d25f3e36c190fea678ecf1845e7c0d2ba833b077a429d64b943e0a`  
		Last Modified: Sat, 28 Apr 2018 11:47:52 GMT  
		Size: 54.5 MB (54465857 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:61347f1daff97305b17924679d0a40043c3c68c04ecd38580c03a9f5f14cc025`  
		Last Modified: Sat, 28 Apr 2018 16:00:45 GMT  
		Size: 10.0 MB (9963110 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4516576626d0afc4ce307a23343efc17d8fa199788465d6fb1966c6e38405270`  
		Last Modified: Sat, 28 Apr 2018 16:00:42 GMT  
		Size: 205.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:688703125c86a49bcd0cb37f53b8cac626f9955a87e6b53ea276458c812556a5`  
		Last Modified: Thu, 24 May 2018 13:53:06 GMT  
		Size: 37.8 MB (37834362 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:efaa249cd8ff410a3388bda85a23d5cbb433c832a6d8d48f9ea2657e4bf3fc74`  
		Last Modified: Fri, 25 May 2018 12:11:35 GMT  
		Size: 148.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:94de6c1f93af7a53a7462885f531826d15d58754eb2331e74481ca1feb375240`  
		Last Modified: Sat, 26 May 2018 13:35:04 GMT  
		Size: 2.1 KB (2108 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:99f7717f21c5fe51d9b4a0431eb42177a38a55ce86b8a91baf6844a2494316fc`  
		Last Modified: Sat, 26 May 2018 13:35:06 GMT  
		Size: 13.1 MB (13130026 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:801facac889b0875723265ee31a416dd8d2ebe6319baa73274d5e95735f61768`  
		Last Modified: Sat, 26 May 2018 13:35:03 GMT  
		Size: 486.8 KB (486830 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cfcfe324efe956c80846c306ea43e06cd3a7ecae28bd7083b7ffd7164f74a6b0`  
		Last Modified: Sat, 26 May 2018 13:35:03 GMT  
		Size: 8.6 KB (8629 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:eadd5af9bd5bd5e656cec7e9a9b27e84d8b168bbad3e06d90f5e18b1b7f71aff`  
		Last Modified: Thu, 21 Jun 2018 13:48:18 GMT  
		Size: 59.5 MB (59533442 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:72e764ca1a11cc27db3156d1dff72273d8e154ac5e070d472388d461ae4f0a93`  
		Last Modified: Thu, 21 Jun 2018 13:48:01 GMT  
		Size: 140.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7dd7e5240971a254b02cde3d738278621464164066f0f44fc13df12d4753d41e`  
		Last Modified: Thu, 21 Jun 2018 13:48:02 GMT  
		Size: 2.4 MB (2394068 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2d8c82c24194cfc982368473f00ebb8ab401c4ac53c7d36d9cf339250812dd45`  
		Last Modified: Thu, 21 Jun 2018 13:48:18 GMT  
		Size: 73.4 MB (73408413 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:69ba76ad79cc8fb20b6bb09792cfb6e98126a9e63f108db51c97d67bcf079c24`  
		Last Modified: Thu, 21 Jun 2018 13:48:01 GMT  
		Size: 1.8 KB (1793 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `redmine:3.3.8-passenger`

```console
$ docker pull redmine@sha256:7e6f1be5e860f83c63e5feb87aac085a71326708911b2888eac55c8b010d0f27
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `redmine:3.3.8-passenger` - linux; amd64

```console
$ docker pull redmine@sha256:1d2f77e6cecf92afec1e0882575815fef6d93d44f985d91cd65789b9fdd97734
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **267.9 MB (267924827 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:b43660742028e9ab5bf70686221a1062357ff9a1c7f9ed298454a916825af264`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["passenger","start"]`

```dockerfile
# Sat, 28 Apr 2018 06:44:15 GMT
ADD file:3e6141c0c9cb74b14a281eb3ab7aaf162a625733e652c3948b323bb2ec8b4343 in / 
# Sat, 28 Apr 2018 06:44:16 GMT
CMD ["bash"]
# Sun, 29 Apr 2018 16:52:40 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Sun, 29 Apr 2018 16:52:41 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Sun, 29 Apr 2018 17:58:22 GMT
ENV RUBY_MAJOR=2.3
# Sun, 29 Apr 2018 17:58:22 GMT
ENV RUBY_VERSION=2.3.7
# Sun, 29 Apr 2018 17:58:22 GMT
ENV RUBY_DOWNLOAD_SHA256=c61f8f2b9d3ffff5567e186421fa191f0d5e7c2b189b426bb84498825d548edb
# Thu, 24 May 2018 01:47:00 GMT
ENV RUBYGEMS_VERSION=2.7.7
# Thu, 24 May 2018 01:47:00 GMT
ENV BUNDLER_VERSION=1.16.2
# Thu, 24 May 2018 01:49:52 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		dpkg-dev 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 		xz-utils 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& dpkg-query --show --showformat '${package}\n' 		| grep -P '^libreadline\d+$' 		| xargs apt-mark manual 	&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force 	&& rm -r /root/.gem/
# Thu, 24 May 2018 01:49:52 GMT
ENV GEM_HOME=/usr/local/bundle
# Thu, 24 May 2018 21:08:58 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Thu, 24 May 2018 21:08:58 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/bundle/gems/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Thu, 24 May 2018 21:08:59 GMT
RUN mkdir -p "$GEM_HOME" && chmod 777 "$GEM_HOME"
# Thu, 24 May 2018 21:08:59 GMT
CMD ["irb"]
# Fri, 25 May 2018 22:48:33 GMT
RUN groupadd -r redmine && useradd -r -g redmine redmine
# Fri, 25 May 2018 22:48:49 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		wget 	&& rm -rf /var/lib/apt/lists/*
# Fri, 25 May 2018 22:48:49 GMT
ENV GOSU_VERSION=1.10
# Fri, 25 May 2018 22:48:53 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Fri, 25 May 2018 22:48:53 GMT
ENV TINI_VERSION=v0.16.1
# Fri, 25 May 2018 22:48:55 GMT
RUN set -x 	&& wget -O /usr/local/bin/tini "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/tini.asc "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5 	&& gpg --batch --verify /usr/local/bin/tini.asc /usr/local/bin/tini 	&& rm -r "$GNUPGHOME" /usr/local/bin/tini.asc 	&& chmod +x /usr/local/bin/tini 	&& tini -h
# Wed, 20 Jun 2018 21:39:59 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		imagemagick 		mercurial 		openssh-client 		subversion 	&& rm -rf /var/lib/apt/lists/*
# Wed, 20 Jun 2018 21:40:00 GMT
ENV RAILS_ENV=production
# Wed, 20 Jun 2018 21:40:00 GMT
WORKDIR /usr/src/redmine
# Wed, 20 Jun 2018 21:40:00 GMT
ENV REDMINE_VERSION=3.3.8
# Wed, 20 Jun 2018 21:40:00 GMT
ENV REDMINE_DOWNLOAD_MD5=6ca9284fa1c3571f6c83dd0e0d0fec1b
# Wed, 20 Jun 2018 21:40:05 GMT
RUN wget -O redmine.tar.gz "https://www.redmine.org/releases/redmine-${REDMINE_VERSION}.tar.gz" 	&& echo "$REDMINE_DOWNLOAD_MD5 redmine.tar.gz" | md5sum -c - 	&& tar -xvf redmine.tar.gz --strip-components=1 	&& rm redmine.tar.gz files/delete.me log/delete.me 	&& mkdir -p tmp/pdf public/plugin_assets 	&& chown -R redmine:redmine ./
# Wed, 20 Jun 2018 21:42:41 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		freetds-dev 		gcc 		libmagickcore-dev 		libmagickwand-dev 		libmysqlclient-dev 		libpq-dev 		libsqlite3-dev 		make 		patch 	; 	rm -rf /var/lib/apt/lists/*; 		bundle install --without development test; 	for adapter in mysql2 postgresql sqlserver sqlite3; do 		echo "$RAILS_ENV:" > ./config/database.yml; 		echo "  adapter: $adapter" >> ./config/database.yml; 		bundle install --without development test; 		cp Gemfile.lock "Gemfile.lock.${adapter}"; 	done; 	rm ./config/database.yml; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| grep -v '^/usr/local/' 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false
# Wed, 20 Jun 2018 21:42:42 GMT
VOLUME [/usr/src/redmine/files]
# Wed, 20 Jun 2018 21:42:42 GMT
COPY file:8064eeba1336402e59165b07c73d0734f58aa7e83e3c0a42b6888098f2e2c11d in / 
# Wed, 20 Jun 2018 21:42:42 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Wed, 20 Jun 2018 21:42:43 GMT
EXPOSE 3000/tcp
# Wed, 20 Jun 2018 21:42:43 GMT
CMD ["rails" "server" "-b" "0.0.0.0"]
# Wed, 20 Jun 2018 21:48:26 GMT
ENV PASSENGER_VERSION=5.3.2
# Wed, 20 Jun 2018 21:48:52 GMT
RUN buildDeps=' 		make 	' 	&& set -x 	&& apt-get update && apt-get install -y --no-install-recommends $buildDeps && rm -rf /var/lib/apt/lists/* 	&& gem install passenger --version "$PASSENGER_VERSION" 	&& apt-get purge -y --auto-remove $buildDeps
# Wed, 20 Jun 2018 21:48:53 GMT
RUN set -x 	&& passenger-config install-agent 	&& passenger-config download-nginx-engine
# Wed, 20 Jun 2018 21:48:53 GMT
CMD ["passenger" "start"]
```

-	Layers:
	-	`sha256:3d77ce4481b119f00e53bee9b4a443469c42c224db954ddaa2e6b74cd73cd5d0`  
		Last Modified: Sat, 28 Apr 2018 08:24:47 GMT  
		Size: 54.3 MB (54262566 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:05a78650ca91970038096c478f5bc7b8155cf0226db13c86ccf40e0e476e23d5`  
		Last Modified: Sun, 29 Apr 2018 19:33:59 GMT  
		Size: 10.2 MB (10168983 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:860996a55f7fba99ae60e7be5fc25d885d982031d74467b9bcfc84f96e72def6`  
		Last Modified: Sun, 29 Apr 2018 19:33:57 GMT  
		Size: 205.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4b80dc12656f673e52960efe49e4f711be35249c76bd015018e7af9b261f65b9`  
		Last Modified: Thu, 24 May 2018 02:06:58 GMT  
		Size: 33.9 MB (33927309 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:608515211c40a538c0165044109a887c946268f6836b7a0486f709e1e1259ae1`  
		Last Modified: Thu, 24 May 2018 21:19:34 GMT  
		Size: 148.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1bc2ef993469835c8b5e39e0fdf1357175ab9b0c5558dc0414417a806cb06c50`  
		Last Modified: Fri, 25 May 2018 22:54:40 GMT  
		Size: 2.1 KB (2106 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:39a9802640b3283085a975cdd520f7885f034b870e41c195867aa9dbf7d432f2`  
		Last Modified: Fri, 25 May 2018 22:54:41 GMT  
		Size: 13.0 MB (12967854 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:01fa73fc0f4c5f19de0704b75842838d7e89f9900b9680dfedb39079c48c90cd`  
		Last Modified: Fri, 25 May 2018 22:54:38 GMT  
		Size: 500.7 KB (500674 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:11dd6ceb02ca6b57f8bdacbf04a2b26d8b28bfc691b961e9d5ca75ce90e65630`  
		Last Modified: Fri, 25 May 2018 22:54:37 GMT  
		Size: 8.5 KB (8510 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4bbed35f8bbe747dfc26c7ecda6a7dd05b490ecb9f1a66732e27fdf249e1e13e`  
		Last Modified: Wed, 20 Jun 2018 21:51:32 GMT  
		Size: 59.7 MB (59701163 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:66fb5daf0fa81dd94ce0c137679f0d0ddd03d68cd756cf9bef4809b7b07f2e53`  
		Last Modified: Wed, 20 Jun 2018 21:51:15 GMT  
		Size: 141.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8f72a72d48f560a273b47fa716ca9fed3828c5ed7be3462882f55bf02edb3c4c`  
		Last Modified: Wed, 20 Jun 2018 21:51:16 GMT  
		Size: 2.4 MB (2394059 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d28265a8c4bce8ed41c9ce7e5bc6eab27c2c9272ba835e52da389bd2a418c14e`  
		Last Modified: Wed, 20 Jun 2018 21:51:24 GMT  
		Size: 70.7 MB (70734145 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0c7ae25302669301e0ba8398fe0561a195cd5e8303c31bc3fab9c17cbe84c918`  
		Last Modified: Wed, 20 Jun 2018 21:51:15 GMT  
		Size: 1.8 KB (1793 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:02fb142c81b7e69512fbaf6de2a3bf14044071875058c23391f0a8a5e0eff7d9`  
		Last Modified: Wed, 20 Jun 2018 21:52:05 GMT  
		Size: 18.8 MB (18770413 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c263f9ad8d7e9c25e2d8a5914ffc2de59a36368d025dc5c9f9d651051a0e6ef3`  
		Last Modified: Wed, 20 Jun 2018 21:51:59 GMT  
		Size: 4.5 MB (4484758 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `redmine:3.3-passenger`

```console
$ docker pull redmine@sha256:7e6f1be5e860f83c63e5feb87aac085a71326708911b2888eac55c8b010d0f27
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `redmine:3.3-passenger` - linux; amd64

```console
$ docker pull redmine@sha256:1d2f77e6cecf92afec1e0882575815fef6d93d44f985d91cd65789b9fdd97734
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **267.9 MB (267924827 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:b43660742028e9ab5bf70686221a1062357ff9a1c7f9ed298454a916825af264`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["passenger","start"]`

```dockerfile
# Sat, 28 Apr 2018 06:44:15 GMT
ADD file:3e6141c0c9cb74b14a281eb3ab7aaf162a625733e652c3948b323bb2ec8b4343 in / 
# Sat, 28 Apr 2018 06:44:16 GMT
CMD ["bash"]
# Sun, 29 Apr 2018 16:52:40 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Sun, 29 Apr 2018 16:52:41 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Sun, 29 Apr 2018 17:58:22 GMT
ENV RUBY_MAJOR=2.3
# Sun, 29 Apr 2018 17:58:22 GMT
ENV RUBY_VERSION=2.3.7
# Sun, 29 Apr 2018 17:58:22 GMT
ENV RUBY_DOWNLOAD_SHA256=c61f8f2b9d3ffff5567e186421fa191f0d5e7c2b189b426bb84498825d548edb
# Thu, 24 May 2018 01:47:00 GMT
ENV RUBYGEMS_VERSION=2.7.7
# Thu, 24 May 2018 01:47:00 GMT
ENV BUNDLER_VERSION=1.16.2
# Thu, 24 May 2018 01:49:52 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		dpkg-dev 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 		xz-utils 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& dpkg-query --show --showformat '${package}\n' 		| grep -P '^libreadline\d+$' 		| xargs apt-mark manual 	&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force 	&& rm -r /root/.gem/
# Thu, 24 May 2018 01:49:52 GMT
ENV GEM_HOME=/usr/local/bundle
# Thu, 24 May 2018 21:08:58 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Thu, 24 May 2018 21:08:58 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/bundle/gems/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Thu, 24 May 2018 21:08:59 GMT
RUN mkdir -p "$GEM_HOME" && chmod 777 "$GEM_HOME"
# Thu, 24 May 2018 21:08:59 GMT
CMD ["irb"]
# Fri, 25 May 2018 22:48:33 GMT
RUN groupadd -r redmine && useradd -r -g redmine redmine
# Fri, 25 May 2018 22:48:49 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		wget 	&& rm -rf /var/lib/apt/lists/*
# Fri, 25 May 2018 22:48:49 GMT
ENV GOSU_VERSION=1.10
# Fri, 25 May 2018 22:48:53 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Fri, 25 May 2018 22:48:53 GMT
ENV TINI_VERSION=v0.16.1
# Fri, 25 May 2018 22:48:55 GMT
RUN set -x 	&& wget -O /usr/local/bin/tini "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/tini.asc "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5 	&& gpg --batch --verify /usr/local/bin/tini.asc /usr/local/bin/tini 	&& rm -r "$GNUPGHOME" /usr/local/bin/tini.asc 	&& chmod +x /usr/local/bin/tini 	&& tini -h
# Wed, 20 Jun 2018 21:39:59 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		imagemagick 		mercurial 		openssh-client 		subversion 	&& rm -rf /var/lib/apt/lists/*
# Wed, 20 Jun 2018 21:40:00 GMT
ENV RAILS_ENV=production
# Wed, 20 Jun 2018 21:40:00 GMT
WORKDIR /usr/src/redmine
# Wed, 20 Jun 2018 21:40:00 GMT
ENV REDMINE_VERSION=3.3.8
# Wed, 20 Jun 2018 21:40:00 GMT
ENV REDMINE_DOWNLOAD_MD5=6ca9284fa1c3571f6c83dd0e0d0fec1b
# Wed, 20 Jun 2018 21:40:05 GMT
RUN wget -O redmine.tar.gz "https://www.redmine.org/releases/redmine-${REDMINE_VERSION}.tar.gz" 	&& echo "$REDMINE_DOWNLOAD_MD5 redmine.tar.gz" | md5sum -c - 	&& tar -xvf redmine.tar.gz --strip-components=1 	&& rm redmine.tar.gz files/delete.me log/delete.me 	&& mkdir -p tmp/pdf public/plugin_assets 	&& chown -R redmine:redmine ./
# Wed, 20 Jun 2018 21:42:41 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		freetds-dev 		gcc 		libmagickcore-dev 		libmagickwand-dev 		libmysqlclient-dev 		libpq-dev 		libsqlite3-dev 		make 		patch 	; 	rm -rf /var/lib/apt/lists/*; 		bundle install --without development test; 	for adapter in mysql2 postgresql sqlserver sqlite3; do 		echo "$RAILS_ENV:" > ./config/database.yml; 		echo "  adapter: $adapter" >> ./config/database.yml; 		bundle install --without development test; 		cp Gemfile.lock "Gemfile.lock.${adapter}"; 	done; 	rm ./config/database.yml; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| grep -v '^/usr/local/' 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false
# Wed, 20 Jun 2018 21:42:42 GMT
VOLUME [/usr/src/redmine/files]
# Wed, 20 Jun 2018 21:42:42 GMT
COPY file:8064eeba1336402e59165b07c73d0734f58aa7e83e3c0a42b6888098f2e2c11d in / 
# Wed, 20 Jun 2018 21:42:42 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Wed, 20 Jun 2018 21:42:43 GMT
EXPOSE 3000/tcp
# Wed, 20 Jun 2018 21:42:43 GMT
CMD ["rails" "server" "-b" "0.0.0.0"]
# Wed, 20 Jun 2018 21:48:26 GMT
ENV PASSENGER_VERSION=5.3.2
# Wed, 20 Jun 2018 21:48:52 GMT
RUN buildDeps=' 		make 	' 	&& set -x 	&& apt-get update && apt-get install -y --no-install-recommends $buildDeps && rm -rf /var/lib/apt/lists/* 	&& gem install passenger --version "$PASSENGER_VERSION" 	&& apt-get purge -y --auto-remove $buildDeps
# Wed, 20 Jun 2018 21:48:53 GMT
RUN set -x 	&& passenger-config install-agent 	&& passenger-config download-nginx-engine
# Wed, 20 Jun 2018 21:48:53 GMT
CMD ["passenger" "start"]
```

-	Layers:
	-	`sha256:3d77ce4481b119f00e53bee9b4a443469c42c224db954ddaa2e6b74cd73cd5d0`  
		Last Modified: Sat, 28 Apr 2018 08:24:47 GMT  
		Size: 54.3 MB (54262566 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:05a78650ca91970038096c478f5bc7b8155cf0226db13c86ccf40e0e476e23d5`  
		Last Modified: Sun, 29 Apr 2018 19:33:59 GMT  
		Size: 10.2 MB (10168983 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:860996a55f7fba99ae60e7be5fc25d885d982031d74467b9bcfc84f96e72def6`  
		Last Modified: Sun, 29 Apr 2018 19:33:57 GMT  
		Size: 205.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4b80dc12656f673e52960efe49e4f711be35249c76bd015018e7af9b261f65b9`  
		Last Modified: Thu, 24 May 2018 02:06:58 GMT  
		Size: 33.9 MB (33927309 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:608515211c40a538c0165044109a887c946268f6836b7a0486f709e1e1259ae1`  
		Last Modified: Thu, 24 May 2018 21:19:34 GMT  
		Size: 148.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1bc2ef993469835c8b5e39e0fdf1357175ab9b0c5558dc0414417a806cb06c50`  
		Last Modified: Fri, 25 May 2018 22:54:40 GMT  
		Size: 2.1 KB (2106 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:39a9802640b3283085a975cdd520f7885f034b870e41c195867aa9dbf7d432f2`  
		Last Modified: Fri, 25 May 2018 22:54:41 GMT  
		Size: 13.0 MB (12967854 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:01fa73fc0f4c5f19de0704b75842838d7e89f9900b9680dfedb39079c48c90cd`  
		Last Modified: Fri, 25 May 2018 22:54:38 GMT  
		Size: 500.7 KB (500674 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:11dd6ceb02ca6b57f8bdacbf04a2b26d8b28bfc691b961e9d5ca75ce90e65630`  
		Last Modified: Fri, 25 May 2018 22:54:37 GMT  
		Size: 8.5 KB (8510 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4bbed35f8bbe747dfc26c7ecda6a7dd05b490ecb9f1a66732e27fdf249e1e13e`  
		Last Modified: Wed, 20 Jun 2018 21:51:32 GMT  
		Size: 59.7 MB (59701163 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:66fb5daf0fa81dd94ce0c137679f0d0ddd03d68cd756cf9bef4809b7b07f2e53`  
		Last Modified: Wed, 20 Jun 2018 21:51:15 GMT  
		Size: 141.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8f72a72d48f560a273b47fa716ca9fed3828c5ed7be3462882f55bf02edb3c4c`  
		Last Modified: Wed, 20 Jun 2018 21:51:16 GMT  
		Size: 2.4 MB (2394059 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d28265a8c4bce8ed41c9ce7e5bc6eab27c2c9272ba835e52da389bd2a418c14e`  
		Last Modified: Wed, 20 Jun 2018 21:51:24 GMT  
		Size: 70.7 MB (70734145 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0c7ae25302669301e0ba8398fe0561a195cd5e8303c31bc3fab9c17cbe84c918`  
		Last Modified: Wed, 20 Jun 2018 21:51:15 GMT  
		Size: 1.8 KB (1793 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:02fb142c81b7e69512fbaf6de2a3bf14044071875058c23391f0a8a5e0eff7d9`  
		Last Modified: Wed, 20 Jun 2018 21:52:05 GMT  
		Size: 18.8 MB (18770413 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c263f9ad8d7e9c25e2d8a5914ffc2de59a36368d025dc5c9f9d651051a0e6ef3`  
		Last Modified: Wed, 20 Jun 2018 21:51:59 GMT  
		Size: 4.5 MB (4484758 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `redmine:3.4`

```console
$ docker pull redmine@sha256:7439dde0eae47d823c35e7f2e4c47d7cbb8b55dbf29844a2579fbd982421d3d3
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm variant v5
	-	linux; arm variant v7
	-	linux; arm64 variant v8
	-	linux; 386
	-	linux; ppc64le
	-	linux; s390x

### `redmine:3.4` - linux; amd64

```console
$ docker pull redmine@sha256:8dce5627271a3f21cd6ce5a3a29c6fbc11fcc99a0ca69d6e6e5882d8ecf4f196
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **250.7 MB (250669098 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:ebd79f5f9bc1c650b0f487dec3b167164c2c36f649ba15d25dbde5ddaae76fe0`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["rails","server","-b","0.0.0.0"]`

```dockerfile
# Sat, 28 Apr 2018 06:44:15 GMT
ADD file:3e6141c0c9cb74b14a281eb3ab7aaf162a625733e652c3948b323bb2ec8b4343 in / 
# Sat, 28 Apr 2018 06:44:16 GMT
CMD ["bash"]
# Sun, 29 Apr 2018 16:52:40 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Sun, 29 Apr 2018 16:52:41 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Sun, 29 Apr 2018 16:52:42 GMT
ENV RUBY_MAJOR=2.4
# Sun, 29 Apr 2018 16:52:42 GMT
ENV RUBY_VERSION=2.4.4
# Sun, 29 Apr 2018 16:52:42 GMT
ENV RUBY_DOWNLOAD_SHA256=1d0034071d675193ca769f64c91827e5f54cb3a7962316a41d5217c7bc6949f0
# Thu, 24 May 2018 01:25:52 GMT
ENV RUBYGEMS_VERSION=2.7.7
# Thu, 24 May 2018 01:25:52 GMT
ENV BUNDLER_VERSION=1.16.2
# Thu, 24 May 2018 01:29:14 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		dpkg-dev 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 		xz-utils 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& dpkg-query --show --showformat '${package}\n' 		| grep -P '^libreadline\d+$' 		| xargs apt-mark manual 	&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force 	&& rm -r /root/.gem/
# Thu, 24 May 2018 01:29:14 GMT
ENV GEM_HOME=/usr/local/bundle
# Thu, 24 May 2018 21:08:01 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Thu, 24 May 2018 21:08:02 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/bundle/gems/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Thu, 24 May 2018 21:08:02 GMT
RUN mkdir -p "$GEM_HOME" && chmod 777 "$GEM_HOME"
# Thu, 24 May 2018 21:08:03 GMT
CMD ["irb"]
# Fri, 25 May 2018 22:37:54 GMT
RUN groupadd -r redmine && useradd -r -g redmine redmine
# Fri, 25 May 2018 22:38:14 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		wget 	&& rm -rf /var/lib/apt/lists/*
# Fri, 25 May 2018 22:38:14 GMT
ENV GOSU_VERSION=1.10
# Fri, 25 May 2018 22:38:18 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Fri, 25 May 2018 22:38:18 GMT
ENV TINI_VERSION=v0.16.1
# Fri, 25 May 2018 22:38:20 GMT
RUN set -x 	&& wget -O /usr/local/bin/tini "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/tini.asc "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5 	&& gpg --batch --verify /usr/local/bin/tini.asc /usr/local/bin/tini 	&& rm -r "$GNUPGHOME" /usr/local/bin/tini.asc 	&& chmod +x /usr/local/bin/tini 	&& tini -h
# Wed, 20 Jun 2018 21:28:18 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		imagemagick 		mercurial 		openssh-client 		subversion 	&& rm -rf /var/lib/apt/lists/*
# Wed, 20 Jun 2018 21:28:18 GMT
ENV RAILS_ENV=production
# Wed, 20 Jun 2018 21:28:19 GMT
WORKDIR /usr/src/redmine
# Wed, 20 Jun 2018 21:28:19 GMT
ENV REDMINE_VERSION=3.4.6
# Wed, 20 Jun 2018 21:28:19 GMT
ENV REDMINE_DOWNLOAD_MD5=5f4993446ecf25782f469763c0d32ea1
# Wed, 20 Jun 2018 21:28:23 GMT
RUN wget -O redmine.tar.gz "https://www.redmine.org/releases/redmine-${REDMINE_VERSION}.tar.gz" 	&& echo "$REDMINE_DOWNLOAD_MD5 redmine.tar.gz" | md5sum -c - 	&& tar -xvf redmine.tar.gz --strip-components=1 	&& rm redmine.tar.gz files/delete.me log/delete.me 	&& mkdir -p tmp/pdf public/plugin_assets 	&& chown -R redmine:redmine ./
# Wed, 20 Jun 2018 21:31:54 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		freetds-dev 		gcc 		libmagickcore-dev 		libmagickwand-dev 		libmysqlclient-dev 		libpq-dev 		libsqlite3-dev 		make 		patch 	; 	rm -rf /var/lib/apt/lists/*; 		bundle install --without development test; 	for adapter in mysql2 postgresql sqlserver sqlite3; do 		echo "$RAILS_ENV:" > ./config/database.yml; 		echo "  adapter: $adapter" >> ./config/database.yml; 		bundle install --without development test; 		cp Gemfile.lock "Gemfile.lock.${adapter}"; 	done; 	rm ./config/database.yml; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| grep -v '^/usr/local/' 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false
# Wed, 20 Jun 2018 21:31:54 GMT
VOLUME [/usr/src/redmine/files]
# Wed, 20 Jun 2018 21:31:54 GMT
COPY file:8064eeba1336402e59165b07c73d0734f58aa7e83e3c0a42b6888098f2e2c11d in / 
# Wed, 20 Jun 2018 21:31:55 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Wed, 20 Jun 2018 21:31:55 GMT
EXPOSE 3000/tcp
# Wed, 20 Jun 2018 21:31:55 GMT
CMD ["rails" "server" "-b" "0.0.0.0"]
```

-	Layers:
	-	`sha256:3d77ce4481b119f00e53bee9b4a443469c42c224db954ddaa2e6b74cd73cd5d0`  
		Last Modified: Sat, 28 Apr 2018 08:24:47 GMT  
		Size: 54.3 MB (54262566 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:05a78650ca91970038096c478f5bc7b8155cf0226db13c86ccf40e0e476e23d5`  
		Last Modified: Sun, 29 Apr 2018 19:33:59 GMT  
		Size: 10.2 MB (10168983 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:860996a55f7fba99ae60e7be5fc25d885d982031d74467b9bcfc84f96e72def6`  
		Last Modified: Sun, 29 Apr 2018 19:33:57 GMT  
		Size: 205.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0af7e9644f308307bcbf19ad9eea243ce5dd469c0211039f47b3120cabdfc99c`  
		Last Modified: Thu, 24 May 2018 02:02:57 GMT  
		Size: 21.3 MB (21305911 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3c2741f1d4c75227c788ea0d4f97b9d842c26908b326b7341255dc08df8c2ff0`  
		Last Modified: Thu, 24 May 2018 21:16:41 GMT  
		Size: 149.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:085bf055e4f7fca4100b86db549ca65dbd113d5633f293b7d60c64580e40fc9c`  
		Last Modified: Fri, 25 May 2018 22:53:00 GMT  
		Size: 2.1 KB (2100 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:02757c5b4f758477ace554b047238004f1ba80dd0253f13e4afde2cff60c8fe2`  
		Last Modified: Fri, 25 May 2018 22:53:02 GMT  
		Size: 13.0 MB (12967769 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0b812d52f0b76913f780e051066b0aec46d9f1a2bc758a19b4872c304bf83525`  
		Last Modified: Fri, 25 May 2018 22:52:57 GMT  
		Size: 500.7 KB (500671 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a1ee2b52aad93348e461129e48f8cb4e4cbc9418e7363ce6ed71b679ed0da25e`  
		Last Modified: Fri, 25 May 2018 22:52:58 GMT  
		Size: 8.5 KB (8506 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:50ec0628480d6092f4ac1c09226941258eaa856ae2b192f54b82351b8147c5a2`  
		Last Modified: Wed, 20 Jun 2018 21:49:29 GMT  
		Size: 59.7 MB (59702353 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d7d52a5fdbb89bea397274ff00985194056ee68db884b686daa2e63575fa3730`  
		Last Modified: Wed, 20 Jun 2018 21:49:09 GMT  
		Size: 140.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:079a05a37d0bc8ec6e3819f8806a9ff391a4c3ff38e3c35679acabccd7281ed1`  
		Last Modified: Wed, 20 Jun 2018 21:49:11 GMT  
		Size: 2.5 MB (2456917 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:828f67b9c47148252d063a4e719ca8ed0be6c8a2487a5ac84f2bade3fd5e83ae`  
		Last Modified: Wed, 20 Jun 2018 21:49:35 GMT  
		Size: 89.3 MB (89291037 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d4660d39964eb0750734643da738a9352ccb35da2e28172ac5340f00f0cd40ea`  
		Last Modified: Wed, 20 Jun 2018 21:49:09 GMT  
		Size: 1.8 KB (1791 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `redmine:3.4` - linux; arm variant v5

```console
$ docker pull redmine@sha256:6d3319e8e0caf66469e15cba6f9b18da2b9994eaae19de97012d1aa9bf8c0402
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **244.2 MB (244218136 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:6b0e3d8938719b59edef5744897ff446a575e4be6543a6de3b33e801b768a7fc`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["rails","server","-b","0.0.0.0"]`

```dockerfile
# Sat, 28 Apr 2018 08:49:23 GMT
ADD file:2d2cd360e66aeff5557c7e7117985a00d109278c3f456ee970afcc9a46483264 in / 
# Sat, 28 Apr 2018 08:49:23 GMT
CMD ["bash"]
# Sat, 28 Apr 2018 11:50:09 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Sat, 28 Apr 2018 11:50:10 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Sat, 28 Apr 2018 11:50:11 GMT
ENV RUBY_MAJOR=2.4
# Sat, 28 Apr 2018 11:50:11 GMT
ENV RUBY_VERSION=2.4.4
# Sat, 28 Apr 2018 11:50:11 GMT
ENV RUBY_DOWNLOAD_SHA256=1d0034071d675193ca769f64c91827e5f54cb3a7962316a41d5217c7bc6949f0
# Thu, 24 May 2018 10:56:19 GMT
ENV RUBYGEMS_VERSION=2.7.7
# Thu, 24 May 2018 10:56:19 GMT
ENV BUNDLER_VERSION=1.16.2
# Thu, 24 May 2018 11:02:19 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		dpkg-dev 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 		xz-utils 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& dpkg-query --show --showformat '${package}\n' 		| grep -P '^libreadline\d+$' 		| xargs apt-mark manual 	&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force 	&& rm -r /root/.gem/
# Thu, 24 May 2018 11:02:20 GMT
ENV GEM_HOME=/usr/local/bundle
# Fri, 25 May 2018 09:09:45 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Fri, 25 May 2018 09:09:45 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/bundle/gems/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 25 May 2018 09:09:46 GMT
RUN mkdir -p "$GEM_HOME" && chmod 777 "$GEM_HOME"
# Fri, 25 May 2018 09:09:47 GMT
CMD ["irb"]
# Sat, 26 May 2018 10:03:35 GMT
RUN groupadd -r redmine && useradd -r -g redmine redmine
# Sat, 26 May 2018 10:04:04 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		wget 	&& rm -rf /var/lib/apt/lists/*
# Sat, 26 May 2018 10:04:04 GMT
ENV GOSU_VERSION=1.10
# Sat, 26 May 2018 10:04:06 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Sat, 26 May 2018 10:04:06 GMT
ENV TINI_VERSION=v0.16.1
# Sat, 26 May 2018 10:04:08 GMT
RUN set -x 	&& wget -O /usr/local/bin/tini "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/tini.asc "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5 	&& gpg --batch --verify /usr/local/bin/tini.asc /usr/local/bin/tini 	&& rm -r "$GNUPGHOME" /usr/local/bin/tini.asc 	&& chmod +x /usr/local/bin/tini 	&& tini -h
# Thu, 21 Jun 2018 09:33:55 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		imagemagick 		mercurial 		openssh-client 		subversion 	&& rm -rf /var/lib/apt/lists/*
# Thu, 21 Jun 2018 09:33:55 GMT
ENV RAILS_ENV=production
# Thu, 21 Jun 2018 09:33:56 GMT
WORKDIR /usr/src/redmine
# Thu, 21 Jun 2018 09:33:56 GMT
ENV REDMINE_VERSION=3.4.6
# Thu, 21 Jun 2018 09:33:56 GMT
ENV REDMINE_DOWNLOAD_MD5=5f4993446ecf25782f469763c0d32ea1
# Thu, 21 Jun 2018 09:34:00 GMT
RUN wget -O redmine.tar.gz "https://www.redmine.org/releases/redmine-${REDMINE_VERSION}.tar.gz" 	&& echo "$REDMINE_DOWNLOAD_MD5 redmine.tar.gz" | md5sum -c - 	&& tar -xvf redmine.tar.gz --strip-components=1 	&& rm redmine.tar.gz files/delete.me log/delete.me 	&& mkdir -p tmp/pdf public/plugin_assets 	&& chown -R redmine:redmine ./
# Thu, 21 Jun 2018 09:40:16 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		freetds-dev 		gcc 		libmagickcore-dev 		libmagickwand-dev 		libmysqlclient-dev 		libpq-dev 		libsqlite3-dev 		make 		patch 	; 	rm -rf /var/lib/apt/lists/*; 		bundle install --without development test; 	for adapter in mysql2 postgresql sqlserver sqlite3; do 		echo "$RAILS_ENV:" > ./config/database.yml; 		echo "  adapter: $adapter" >> ./config/database.yml; 		bundle install --without development test; 		cp Gemfile.lock "Gemfile.lock.${adapter}"; 	done; 	rm ./config/database.yml; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| grep -v '^/usr/local/' 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false
# Thu, 21 Jun 2018 09:40:17 GMT
VOLUME [/usr/src/redmine/files]
# Thu, 21 Jun 2018 09:40:17 GMT
COPY file:8064eeba1336402e59165b07c73d0734f58aa7e83e3c0a42b6888098f2e2c11d in / 
# Thu, 21 Jun 2018 09:40:17 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Thu, 21 Jun 2018 09:40:17 GMT
EXPOSE 3000/tcp
# Thu, 21 Jun 2018 09:40:18 GMT
CMD ["rails" "server" "-b" "0.0.0.0"]
```

-	Layers:
	-	`sha256:81fc0826192f72abe617753d378af4047dbce89faf17cdab9166877006a25d8e`  
		Last Modified: Sat, 28 Apr 2018 08:57:10 GMT  
		Size: 52.5 MB (52456037 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2119f18fa6f270436c891e0c459923ae24657bf4a8be20cfcfe964e7aa64b7b2`  
		Last Modified: Sat, 28 Apr 2018 12:31:30 GMT  
		Size: 9.1 MB (9119888 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:51757db9404a98c26c96cb6b65e8c7893c1e1b5ea9774a5786abe9ec88468cf3`  
		Last Modified: Sat, 28 Apr 2018 12:31:26 GMT  
		Size: 206.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:09fe38be652b02d310bce0a19598fe366080a17713f114eeb33355e15f6bf8c0`  
		Last Modified: Thu, 24 May 2018 11:29:31 GMT  
		Size: 21.1 MB (21074760 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:63fc7f9b6584b1727a86e7d2130c3f4129978990791d89d6af0f9950997cc782`  
		Last Modified: Fri, 25 May 2018 09:17:51 GMT  
		Size: 182.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bdbf4bf93be2e977124205e4f60ae3ba2a2f880c269a494237a056a419343587`  
		Last Modified: Sat, 26 May 2018 10:18:09 GMT  
		Size: 2.1 KB (2090 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:98b6a7f079c3c2475a4ae64a2f970ab18867099384ac59e88b28b14c37d777fc`  
		Last Modified: Sat, 26 May 2018 10:18:11 GMT  
		Size: 12.8 MB (12772572 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:33fbc82bebefed415e0d99d95c2199ccefd11254cfbefe0cb44e5c4235a80dbc`  
		Last Modified: Sat, 26 May 2018 10:18:06 GMT  
		Size: 491.1 KB (491125 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:494ed27bef31be226f9bb0b7dde7a3de53fee37d4a9defca95c65999a45bf288`  
		Last Modified: Sat, 26 May 2018 10:18:06 GMT  
		Size: 7.8 KB (7850 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:260011ea13c12e7f76c6ef3f3b6ac329067d5d62b1c3ea2e1438fc4d24c6e9f2`  
		Last Modified: Thu, 21 Jun 2018 09:46:58 GMT  
		Size: 57.1 MB (57055867 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7682be80ee6471502bcde4c8a3d03401fe0f247174899f7a298ea324b24bbaf8`  
		Last Modified: Thu, 21 Jun 2018 09:46:39 GMT  
		Size: 172.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e64810335b2932687826690900537543be72f782fbeb739f26c18c27c3f1a048`  
		Last Modified: Thu, 21 Jun 2018 09:46:41 GMT  
		Size: 2.5 MB (2457560 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:12da0e4bca312d2c2db7b5c9dc56916f4b56b158b309d62ae947b273fd04b8db`  
		Last Modified: Thu, 21 Jun 2018 09:47:03 GMT  
		Size: 88.8 MB (88778036 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b0398911b75ac4341523e8856acb1f5668b263bc57152d9ec5abda35b5ee15bd`  
		Last Modified: Thu, 21 Jun 2018 09:46:40 GMT  
		Size: 1.8 KB (1791 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `redmine:3.4` - linux; arm variant v7

```console
$ docker pull redmine@sha256:df7144a1137742adc5e4e11125da5e4d18e517fe491950489f2f97452b2522bf
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **238.4 MB (238431615 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:f661101282a8e3e492241307b1e3a098dbc6f66588f65c554e6267e3fa781492`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["rails","server","-b","0.0.0.0"]`

```dockerfile
# Sat, 28 Apr 2018 11:59:05 GMT
ADD file:4e9c283075c120ce66f83bf541b0aeaa8a46f74c21d38e4ab1578e7f1b892823 in / 
# Sat, 28 Apr 2018 11:59:05 GMT
CMD ["bash"]
# Sat, 28 Apr 2018 15:40:52 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Sat, 28 Apr 2018 15:40:56 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Sat, 28 Apr 2018 15:40:56 GMT
ENV RUBY_MAJOR=2.4
# Sat, 28 Apr 2018 15:40:57 GMT
ENV RUBY_VERSION=2.4.4
# Sat, 28 Apr 2018 15:40:57 GMT
ENV RUBY_DOWNLOAD_SHA256=1d0034071d675193ca769f64c91827e5f54cb3a7962316a41d5217c7bc6949f0
# Thu, 24 May 2018 13:13:30 GMT
ENV RUBYGEMS_VERSION=2.7.7
# Thu, 24 May 2018 13:13:31 GMT
ENV BUNDLER_VERSION=1.16.2
# Thu, 24 May 2018 13:18:52 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		dpkg-dev 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 		xz-utils 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& dpkg-query --show --showformat '${package}\n' 		| grep -P '^libreadline\d+$' 		| xargs apt-mark manual 	&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force 	&& rm -r /root/.gem/
# Thu, 24 May 2018 13:18:53 GMT
ENV GEM_HOME=/usr/local/bundle
# Fri, 25 May 2018 12:27:41 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Fri, 25 May 2018 12:27:42 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/bundle/gems/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 25 May 2018 12:27:43 GMT
RUN mkdir -p "$GEM_HOME" && chmod 777 "$GEM_HOME"
# Fri, 25 May 2018 12:27:43 GMT
CMD ["irb"]
# Sat, 26 May 2018 12:23:55 GMT
RUN groupadd -r redmine && useradd -r -g redmine redmine
# Sat, 26 May 2018 12:24:22 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		wget 	&& rm -rf /var/lib/apt/lists/*
# Sat, 26 May 2018 12:24:22 GMT
ENV GOSU_VERSION=1.10
# Sat, 26 May 2018 12:24:24 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Sat, 26 May 2018 12:24:24 GMT
ENV TINI_VERSION=v0.16.1
# Sat, 26 May 2018 12:24:26 GMT
RUN set -x 	&& wget -O /usr/local/bin/tini "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/tini.asc "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5 	&& gpg --batch --verify /usr/local/bin/tini.asc /usr/local/bin/tini 	&& rm -r "$GNUPGHOME" /usr/local/bin/tini.asc 	&& chmod +x /usr/local/bin/tini 	&& tini -h
# Thu, 21 Jun 2018 12:06:34 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		imagemagick 		mercurial 		openssh-client 		subversion 	&& rm -rf /var/lib/apt/lists/*
# Thu, 21 Jun 2018 12:06:34 GMT
ENV RAILS_ENV=production
# Thu, 21 Jun 2018 12:06:34 GMT
WORKDIR /usr/src/redmine
# Thu, 21 Jun 2018 12:06:35 GMT
ENV REDMINE_VERSION=3.4.6
# Thu, 21 Jun 2018 12:06:35 GMT
ENV REDMINE_DOWNLOAD_MD5=5f4993446ecf25782f469763c0d32ea1
# Thu, 21 Jun 2018 12:06:39 GMT
RUN wget -O redmine.tar.gz "https://www.redmine.org/releases/redmine-${REDMINE_VERSION}.tar.gz" 	&& echo "$REDMINE_DOWNLOAD_MD5 redmine.tar.gz" | md5sum -c - 	&& tar -xvf redmine.tar.gz --strip-components=1 	&& rm redmine.tar.gz files/delete.me log/delete.me 	&& mkdir -p tmp/pdf public/plugin_assets 	&& chown -R redmine:redmine ./
# Thu, 21 Jun 2018 12:12:24 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		freetds-dev 		gcc 		libmagickcore-dev 		libmagickwand-dev 		libmysqlclient-dev 		libpq-dev 		libsqlite3-dev 		make 		patch 	; 	rm -rf /var/lib/apt/lists/*; 		bundle install --without development test; 	for adapter in mysql2 postgresql sqlserver sqlite3; do 		echo "$RAILS_ENV:" > ./config/database.yml; 		echo "  adapter: $adapter" >> ./config/database.yml; 		bundle install --without development test; 		cp Gemfile.lock "Gemfile.lock.${adapter}"; 	done; 	rm ./config/database.yml; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| grep -v '^/usr/local/' 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false
# Thu, 21 Jun 2018 12:12:25 GMT
VOLUME [/usr/src/redmine/files]
# Thu, 21 Jun 2018 12:12:25 GMT
COPY file:8064eeba1336402e59165b07c73d0734f58aa7e83e3c0a42b6888098f2e2c11d in / 
# Thu, 21 Jun 2018 12:12:25 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Thu, 21 Jun 2018 12:12:26 GMT
EXPOSE 3000/tcp
# Thu, 21 Jun 2018 12:12:26 GMT
CMD ["rails" "server" "-b" "0.0.0.0"]
```

-	Layers:
	-	`sha256:5c478157e28e3c26a0209484edb518799e1c21863d4700579c010b7203e0537f`  
		Last Modified: Sat, 28 Apr 2018 12:10:24 GMT  
		Size: 50.2 MB (50195697 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:57cc82e3a61290e4bfc39b7ec615f84e7782d645852ff04b0f1077ba3a8d6c85`  
		Last Modified: Sat, 28 Apr 2018 16:21:20 GMT  
		Size: 8.8 MB (8777726 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e60d4b7c236d855ddd6a1f286ece09d909ea721b8959a806142de215e84ad242`  
		Last Modified: Sat, 28 Apr 2018 16:21:17 GMT  
		Size: 207.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fd714148500451500a2957112b77e7e1feb9b7fa3095266d84623a097aa9935b`  
		Last Modified: Thu, 24 May 2018 13:51:44 GMT  
		Size: 20.9 MB (20939873 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:15b699e7e8d225b3c8087b29914345882f41c75520d205595171039ab1e0c856`  
		Last Modified: Fri, 25 May 2018 12:40:08 GMT  
		Size: 182.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0e957186fb243adf5019585383bf19defaa1d82b4636998b537528235dd777f2`  
		Last Modified: Sat, 26 May 2018 12:37:45 GMT  
		Size: 2.1 KB (2092 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:11e22cb6dff3aef6e6185c86a85889793c9f7fff65d461c749557bc8884b9624`  
		Last Modified: Sat, 26 May 2018 12:37:50 GMT  
		Size: 12.6 MB (12629462 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9726b5b13c21e003fe07315e1e1f21db27480310aa0606a5699f7435f62801cf`  
		Last Modified: Sat, 26 May 2018 12:37:45 GMT  
		Size: 475.3 KB (475267 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3784a11f9e4def9da3250391267c9bcffd3edd695febdb607895c2fa1524e923`  
		Last Modified: Sat, 26 May 2018 12:37:44 GMT  
		Size: 7.3 KB (7313 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1374393c860f34b65841b3158be787bc2df985c718b0bd332c8d8c7428a83e52`  
		Last Modified: Thu, 21 Jun 2018 12:18:49 GMT  
		Size: 54.7 MB (54698588 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:42db57f6861effae6af53fac1d6db5790da8afb4d14f64a0f0f22aba5649080e`  
		Last Modified: Thu, 21 Jun 2018 12:18:32 GMT  
		Size: 172.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:590497ab77d278095f81c2e419971e26ef0d6483e14a0b97ed13f8ec94a76f83`  
		Last Modified: Thu, 21 Jun 2018 12:18:34 GMT  
		Size: 2.5 MB (2457572 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d3918493345313d19d0cbd4c26bd6142b71be53be71d3976bbd956e00a1c7da8`  
		Last Modified: Thu, 21 Jun 2018 12:18:57 GMT  
		Size: 88.2 MB (88245671 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e118f56902617fa8db9f49493a8d0039c3a90976f6506cf6df565557e09560af`  
		Last Modified: Thu, 21 Jun 2018 12:18:32 GMT  
		Size: 1.8 KB (1793 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `redmine:3.4` - linux; arm64 variant v8

```console
$ docker pull redmine@sha256:988df7496fea7b7cc53d5210dd1bd832b8d22cbf82fb0b9f6a7d61c366de95c4
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **243.2 MB (243226684 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:795f00ab797d1fb1e0e03e8ea4d2c01f3f953b9df56a7da35adfd390546f65a6`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["rails","server","-b","0.0.0.0"]`

```dockerfile
# Mon, 30 Apr 2018 23:21:38 GMT
ADD file:387c83918422a6546379c4d84818ca3949fcd63aec058da562b08c947a9ed571 in / 
# Mon, 30 Apr 2018 23:21:40 GMT
CMD ["bash"]
# Tue, 01 May 2018 08:41:36 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Tue, 01 May 2018 08:41:41 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Tue, 01 May 2018 08:41:42 GMT
ENV RUBY_MAJOR=2.4
# Tue, 01 May 2018 08:41:44 GMT
ENV RUBY_VERSION=2.4.4
# Tue, 01 May 2018 08:41:46 GMT
ENV RUBY_DOWNLOAD_SHA256=1d0034071d675193ca769f64c91827e5f54cb3a7962316a41d5217c7bc6949f0
# Fri, 25 May 2018 16:57:16 GMT
ENV RUBYGEMS_VERSION=2.7.7
# Fri, 25 May 2018 16:57:17 GMT
ENV BUNDLER_VERSION=1.16.2
# Fri, 25 May 2018 17:06:32 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		dpkg-dev 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 		xz-utils 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& dpkg-query --show --showformat '${package}\n' 		| grep -P '^libreadline\d+$' 		| xargs apt-mark manual 	&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force 	&& rm -r /root/.gem/
# Fri, 25 May 2018 17:06:33 GMT
ENV GEM_HOME=/usr/local/bundle
# Fri, 25 May 2018 17:06:34 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Fri, 25 May 2018 17:06:34 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/bundle/gems/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 25 May 2018 17:06:36 GMT
RUN mkdir -p "$GEM_HOME" && chmod 777 "$GEM_HOME"
# Fri, 25 May 2018 17:06:37 GMT
CMD ["irb"]
# Fri, 25 May 2018 21:43:13 GMT
RUN groupadd -r redmine && useradd -r -g redmine redmine
# Fri, 25 May 2018 21:43:38 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		wget 	&& rm -rf /var/lib/apt/lists/*
# Fri, 25 May 2018 21:43:38 GMT
ENV GOSU_VERSION=1.10
# Fri, 25 May 2018 21:43:43 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Fri, 25 May 2018 21:43:44 GMT
ENV TINI_VERSION=v0.16.1
# Fri, 25 May 2018 21:43:46 GMT
RUN set -x 	&& wget -O /usr/local/bin/tini "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/tini.asc "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5 	&& gpg --batch --verify /usr/local/bin/tini.asc /usr/local/bin/tini 	&& rm -r "$GNUPGHOME" /usr/local/bin/tini.asc 	&& chmod +x /usr/local/bin/tini 	&& tini -h
# Thu, 21 Jun 2018 16:59:11 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		imagemagick 		mercurial 		openssh-client 		subversion 	&& rm -rf /var/lib/apt/lists/*
# Thu, 21 Jun 2018 16:59:12 GMT
ENV RAILS_ENV=production
# Thu, 21 Jun 2018 16:59:13 GMT
WORKDIR /usr/src/redmine
# Thu, 21 Jun 2018 16:59:13 GMT
ENV REDMINE_VERSION=3.4.6
# Thu, 21 Jun 2018 16:59:14 GMT
ENV REDMINE_DOWNLOAD_MD5=5f4993446ecf25782f469763c0d32ea1
# Thu, 21 Jun 2018 16:59:20 GMT
RUN wget -O redmine.tar.gz "https://www.redmine.org/releases/redmine-${REDMINE_VERSION}.tar.gz" 	&& echo "$REDMINE_DOWNLOAD_MD5 redmine.tar.gz" | md5sum -c - 	&& tar -xvf redmine.tar.gz --strip-components=1 	&& rm redmine.tar.gz files/delete.me log/delete.me 	&& mkdir -p tmp/pdf public/plugin_assets 	&& chown -R redmine:redmine ./
# Thu, 21 Jun 2018 17:12:12 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		freetds-dev 		gcc 		libmagickcore-dev 		libmagickwand-dev 		libmysqlclient-dev 		libpq-dev 		libsqlite3-dev 		make 		patch 	; 	rm -rf /var/lib/apt/lists/*; 		bundle install --without development test; 	for adapter in mysql2 postgresql sqlserver sqlite3; do 		echo "$RAILS_ENV:" > ./config/database.yml; 		echo "  adapter: $adapter" >> ./config/database.yml; 		bundle install --without development test; 		cp Gemfile.lock "Gemfile.lock.${adapter}"; 	done; 	rm ./config/database.yml; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| grep -v '^/usr/local/' 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false
# Thu, 21 Jun 2018 17:12:14 GMT
VOLUME [/usr/src/redmine/files]
# Thu, 21 Jun 2018 17:12:14 GMT
COPY file:8064eeba1336402e59165b07c73d0734f58aa7e83e3c0a42b6888098f2e2c11d in / 
# Thu, 21 Jun 2018 17:12:15 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Thu, 21 Jun 2018 17:12:16 GMT
EXPOSE 3000/tcp
# Thu, 21 Jun 2018 17:12:17 GMT
CMD ["rails" "server" "-b" "0.0.0.0"]
```

-	Layers:
	-	`sha256:363cfded2ef3921ef972c85cafc77cf16cdcfddfd49782ad4540cb73fd5e57a2`  
		Last Modified: Mon, 30 Apr 2018 23:41:06 GMT  
		Size: 51.4 MB (51446854 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6aeaeeebfa7e2a1e6c69a484a7648b6313aff4bf219767667e43bbfc42bb40d9`  
		Last Modified: Tue, 01 May 2018 09:53:45 GMT  
		Size: 9.3 MB (9343083 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3b78cb3f4882a2b3bf1ecb4fdbe1e145a3ddb80ce1fde62a33ada1beaf12daf8`  
		Last Modified: Tue, 01 May 2018 09:53:41 GMT  
		Size: 205.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:18547e3cbea8ccf1a7ca22515077049b202d0f12cac441573f4edf1f9b567209`  
		Last Modified: Fri, 25 May 2018 18:07:21 GMT  
		Size: 21.3 MB (21265153 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1d6d550606a490752c05952acf272ef8a1e4df8e3a8be58f37f50260160a5b11`  
		Last Modified: Fri, 25 May 2018 18:07:10 GMT  
		Size: 148.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:548893d753de4a74e5a64d26225a85691cfd2ad2b0546591161f46916ea1229f`  
		Last Modified: Fri, 25 May 2018 22:12:00 GMT  
		Size: 2.1 KB (2113 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a5ecd4fc430347071a2c164435746340e018f58d8037eabf8dd5665ad1b0dff6`  
		Last Modified: Fri, 25 May 2018 22:12:03 GMT  
		Size: 12.9 MB (12940690 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bfc6b9486743d7946d7922a4c47f0cc78876f91c3db011553f4f9a25a1dc96e2`  
		Last Modified: Fri, 25 May 2018 22:11:58 GMT  
		Size: 468.7 KB (468701 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e8f19d3b246e0490714656220e538767a6b0f47ae8f43c10cc32017687ae3114`  
		Last Modified: Fri, 25 May 2018 22:11:58 GMT  
		Size: 8.2 KB (8154 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:33f179dd0cce7b503211ff6d22a331d47169a234442ac5b0f6d11519eb3ead53`  
		Last Modified: Thu, 21 Jun 2018 17:27:27 GMT  
		Size: 56.2 MB (56166767 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b00c8c2de88468ac5d8b2af1848ffa502eded4adfd3a7e8e3859a57018eaace6`  
		Last Modified: Thu, 21 Jun 2018 17:27:04 GMT  
		Size: 140.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:95eb29922954e0efbb03fb3ca6512c8ce0d257303fc9a551e8d52455bef6d5b1`  
		Last Modified: Thu, 21 Jun 2018 17:27:07 GMT  
		Size: 2.5 MB (2456916 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f2bfa5dcbc83e5d3cd044dfbc3d81faa5b22a07684e60e5ca7cc0c8f4c76a57f`  
		Last Modified: Thu, 21 Jun 2018 17:27:35 GMT  
		Size: 89.1 MB (89125967 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:51f3ad7cc3086c71f467f0eee89ca821bc6f3aae7bd05ce85b8eb78d72e15a94`  
		Last Modified: Thu, 21 Jun 2018 17:27:04 GMT  
		Size: 1.8 KB (1793 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `redmine:3.4` - linux; 386

```console
$ docker pull redmine@sha256:d87c7c46bff353bc7e6f129b084607c93da5931f3d61a8ab52a1a2e6895bf371
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **253.9 MB (253912619 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:f17b65464fff83d872964798559dc27680b6902daaba36df7306c9fa0a810e9d`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["rails","server","-b","0.0.0.0"]`

```dockerfile
# Sat, 28 Apr 2018 10:39:32 GMT
ADD file:ce5174f2b2c155a2421fac3ff37a02d9551d5d79e31a541189bcfd2416a6903a in / 
# Sat, 28 Apr 2018 10:39:32 GMT
CMD ["bash"]
# Fri, 01 Jun 2018 14:56:41 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Fri, 01 Jun 2018 14:56:42 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Fri, 01 Jun 2018 14:56:42 GMT
ENV RUBY_MAJOR=2.4
# Fri, 01 Jun 2018 14:56:42 GMT
ENV RUBY_VERSION=2.4.4
# Fri, 01 Jun 2018 14:56:42 GMT
ENV RUBY_DOWNLOAD_SHA256=1d0034071d675193ca769f64c91827e5f54cb3a7962316a41d5217c7bc6949f0
# Fri, 01 Jun 2018 14:56:42 GMT
ENV RUBYGEMS_VERSION=2.7.7
# Fri, 01 Jun 2018 14:56:42 GMT
ENV BUNDLER_VERSION=1.16.2
# Fri, 01 Jun 2018 15:04:05 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		dpkg-dev 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 		xz-utils 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& dpkg-query --show --showformat '${package}\n' 		| grep -P '^libreadline\d+$' 		| xargs apt-mark manual 	&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force 	&& rm -r /root/.gem/
# Fri, 01 Jun 2018 15:04:06 GMT
ENV GEM_HOME=/usr/local/bundle
# Fri, 01 Jun 2018 15:04:06 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Fri, 01 Jun 2018 15:04:06 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/bundle/gems/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 01 Jun 2018 15:04:07 GMT
RUN mkdir -p "$GEM_HOME" && chmod 777 "$GEM_HOME"
# Fri, 01 Jun 2018 15:04:07 GMT
CMD ["irb"]
# Fri, 01 Jun 2018 17:09:55 GMT
RUN groupadd -r redmine && useradd -r -g redmine redmine
# Fri, 01 Jun 2018 17:10:49 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		wget 	&& rm -rf /var/lib/apt/lists/*
# Fri, 01 Jun 2018 17:10:49 GMT
ENV GOSU_VERSION=1.10
# Fri, 01 Jun 2018 17:10:56 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Fri, 01 Jun 2018 17:10:56 GMT
ENV TINI_VERSION=v0.16.1
# Fri, 01 Jun 2018 17:10:59 GMT
RUN set -x 	&& wget -O /usr/local/bin/tini "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/tini.asc "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5 	&& gpg --batch --verify /usr/local/bin/tini.asc /usr/local/bin/tini 	&& rm -r "$GNUPGHOME" /usr/local/bin/tini.asc 	&& chmod +x /usr/local/bin/tini 	&& tini -h
# Thu, 21 Jun 2018 11:00:37 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		imagemagick 		mercurial 		openssh-client 		subversion 	&& rm -rf /var/lib/apt/lists/*
# Thu, 21 Jun 2018 11:00:38 GMT
ENV RAILS_ENV=production
# Thu, 21 Jun 2018 11:00:38 GMT
WORKDIR /usr/src/redmine
# Thu, 21 Jun 2018 11:00:38 GMT
ENV REDMINE_VERSION=3.4.6
# Thu, 21 Jun 2018 11:00:39 GMT
ENV REDMINE_DOWNLOAD_MD5=5f4993446ecf25782f469763c0d32ea1
# Thu, 21 Jun 2018 11:00:43 GMT
RUN wget -O redmine.tar.gz "https://www.redmine.org/releases/redmine-${REDMINE_VERSION}.tar.gz" 	&& echo "$REDMINE_DOWNLOAD_MD5 redmine.tar.gz" | md5sum -c - 	&& tar -xvf redmine.tar.gz --strip-components=1 	&& rm redmine.tar.gz files/delete.me log/delete.me 	&& mkdir -p tmp/pdf public/plugin_assets 	&& chown -R redmine:redmine ./
# Thu, 21 Jun 2018 11:07:27 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		freetds-dev 		gcc 		libmagickcore-dev 		libmagickwand-dev 		libmysqlclient-dev 		libpq-dev 		libsqlite3-dev 		make 		patch 	; 	rm -rf /var/lib/apt/lists/*; 		bundle install --without development test; 	for adapter in mysql2 postgresql sqlserver sqlite3; do 		echo "$RAILS_ENV:" > ./config/database.yml; 		echo "  adapter: $adapter" >> ./config/database.yml; 		bundle install --without development test; 		cp Gemfile.lock "Gemfile.lock.${adapter}"; 	done; 	rm ./config/database.yml; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| grep -v '^/usr/local/' 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false
# Thu, 21 Jun 2018 11:07:28 GMT
VOLUME [/usr/src/redmine/files]
# Thu, 21 Jun 2018 11:07:35 GMT
COPY file:8064eeba1336402e59165b07c73d0734f58aa7e83e3c0a42b6888098f2e2c11d in / 
# Thu, 21 Jun 2018 11:07:36 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Thu, 21 Jun 2018 11:07:36 GMT
EXPOSE 3000/tcp
# Thu, 21 Jun 2018 11:07:36 GMT
CMD ["rails" "server" "-b" "0.0.0.0"]
```

-	Layers:
	-	`sha256:05b419d667f793c8c2edf0ff0aec14fc4d66733cdb89957ac89e8bfbeaddd0fa`  
		Last Modified: Sat, 28 Apr 2018 10:44:20 GMT  
		Size: 54.5 MB (54486782 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3d6891754f33e4c1f328ba0f4530fdb8383be81d86d518c6967565db3d8a7d3f`  
		Last Modified: Fri, 01 Jun 2018 15:49:54 GMT  
		Size: 14.9 MB (14942131 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:089cb9bb407565a3373144a74a72a2345d043f8423185a11fe236787bfc2d617`  
		Last Modified: Fri, 01 Jun 2018 15:49:47 GMT  
		Size: 208.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b853b205add0f75c6d80bbdfcfd40d09d2435262eb1076c603fd5a6ffff58a15`  
		Last Modified: Fri, 01 Jun 2018 15:49:56 GMT  
		Size: 20.3 MB (20303639 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7911295bc17916b28653d7cd6782d5eaede8fbbd7814f157a445829de1488cc8`  
		Last Modified: Fri, 01 Jun 2018 15:49:47 GMT  
		Size: 148.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2f80ba1db311f9d427a674563c28a8673d1b2941bcf25116f71c8446c382a3b4`  
		Last Modified: Fri, 01 Jun 2018 17:31:18 GMT  
		Size: 2.1 KB (2090 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ff801544c3611060c1d01382b678c4ae46af418e380369f5ebe1d34b0f29d77e`  
		Last Modified: Fri, 01 Jun 2018 17:31:27 GMT  
		Size: 13.1 MB (13103088 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a8e57a3fcd9a49a1c8880a39b935633a3041926c55a56be8bd38c07adff2c4fa`  
		Last Modified: Fri, 01 Jun 2018 17:31:16 GMT  
		Size: 480.6 KB (480563 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0351ff4ecba98d1064a87e597d3a72a277f456c7c8c5ca2c5d3232ee7d9ac7a5`  
		Last Modified: Fri, 01 Jun 2018 17:31:14 GMT  
		Size: 8.6 KB (8565 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a6451afdfb1e0e39ceba0ae2d333f8b7517af15e4c692a597d1b54293e304bb1`  
		Last Modified: Thu, 21 Jun 2018 11:15:18 GMT  
		Size: 60.6 MB (60580239 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bf645102966d197165f4e7e583a568f06ddf47daafd8fb4d473042543a2cac26`  
		Last Modified: Thu, 21 Jun 2018 11:14:48 GMT  
		Size: 140.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ce01371909c6db5cdb9d92de323d2973c0dd219f9f8daba9055a9dc8195ec003`  
		Last Modified: Thu, 21 Jun 2018 11:14:50 GMT  
		Size: 2.5 MB (2456909 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:95d4b6248a4676e50ab8bbfe182fb99d5dd0caff607308555d3f8d9147948743`  
		Last Modified: Thu, 21 Jun 2018 11:15:20 GMT  
		Size: 87.5 MB (87546324 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:114fe7ad48c3d506f86cfc90e19d21acbd0d6f6f8686ffd8c241234719076c80`  
		Last Modified: Thu, 21 Jun 2018 11:14:48 GMT  
		Size: 1.8 KB (1793 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `redmine:3.4` - linux; ppc64le

```console
$ docker pull redmine@sha256:907c86f110cb9245f282d9daeb30d2fef6fe5073bc1c78cea57bc0f4c745dc1a
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **249.9 MB (249907098 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:b0de66b8b9f108221b0d577f34253c4482d759cf811a688bfc94660b4c03cb28`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["rails","server","-b","0.0.0.0"]`

```dockerfile
# Sat, 28 Apr 2018 08:17:46 GMT
ADD file:6a4bd4ea54f669286e984ecf8178e1fa7c12c8b6fc0f96e4203ae7a6f99a2279 in / 
# Sat, 28 Apr 2018 08:17:47 GMT
CMD ["bash"]
# Sat, 28 Apr 2018 11:24:06 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Sat, 28 Apr 2018 11:24:08 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Sat, 28 Apr 2018 11:24:08 GMT
ENV RUBY_MAJOR=2.4
# Sat, 28 Apr 2018 11:24:08 GMT
ENV RUBY_VERSION=2.4.4
# Sat, 28 Apr 2018 11:24:09 GMT
ENV RUBY_DOWNLOAD_SHA256=1d0034071d675193ca769f64c91827e5f54cb3a7962316a41d5217c7bc6949f0
# Thu, 24 May 2018 10:50:48 GMT
ENV RUBYGEMS_VERSION=2.7.7
# Thu, 24 May 2018 10:50:50 GMT
ENV BUNDLER_VERSION=1.16.2
# Thu, 24 May 2018 10:58:50 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		dpkg-dev 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 		xz-utils 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& dpkg-query --show --showformat '${package}\n' 		| grep -P '^libreadline\d+$' 		| xargs apt-mark manual 	&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force 	&& rm -r /root/.gem/
# Thu, 24 May 2018 10:58:51 GMT
ENV GEM_HOME=/usr/local/bundle
# Fri, 25 May 2018 09:19:08 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Fri, 25 May 2018 09:19:09 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/bundle/gems/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 25 May 2018 09:19:10 GMT
RUN mkdir -p "$GEM_HOME" && chmod 777 "$GEM_HOME"
# Fri, 25 May 2018 09:19:11 GMT
CMD ["irb"]
# Sat, 26 May 2018 09:41:15 GMT
RUN groupadd -r redmine && useradd -r -g redmine redmine
# Sat, 26 May 2018 09:42:45 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		wget 	&& rm -rf /var/lib/apt/lists/*
# Sat, 26 May 2018 09:42:51 GMT
ENV GOSU_VERSION=1.10
# Sat, 26 May 2018 09:43:05 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Sat, 26 May 2018 09:43:11 GMT
ENV TINI_VERSION=v0.16.1
# Sat, 26 May 2018 09:43:19 GMT
RUN set -x 	&& wget -O /usr/local/bin/tini "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/tini.asc "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5 	&& gpg --batch --verify /usr/local/bin/tini.asc /usr/local/bin/tini 	&& rm -r "$GNUPGHOME" /usr/local/bin/tini.asc 	&& chmod +x /usr/local/bin/tini 	&& tini -h
# Thu, 21 Jun 2018 09:57:56 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		imagemagick 		mercurial 		openssh-client 		subversion 	&& rm -rf /var/lib/apt/lists/*
# Thu, 21 Jun 2018 09:57:57 GMT
ENV RAILS_ENV=production
# Thu, 21 Jun 2018 09:57:58 GMT
WORKDIR /usr/src/redmine
# Thu, 21 Jun 2018 09:57:58 GMT
ENV REDMINE_VERSION=3.4.6
# Thu, 21 Jun 2018 09:57:59 GMT
ENV REDMINE_DOWNLOAD_MD5=5f4993446ecf25782f469763c0d32ea1
# Thu, 21 Jun 2018 09:58:05 GMT
RUN wget -O redmine.tar.gz "https://www.redmine.org/releases/redmine-${REDMINE_VERSION}.tar.gz" 	&& echo "$REDMINE_DOWNLOAD_MD5 redmine.tar.gz" | md5sum -c - 	&& tar -xvf redmine.tar.gz --strip-components=1 	&& rm redmine.tar.gz files/delete.me log/delete.me 	&& mkdir -p tmp/pdf public/plugin_assets 	&& chown -R redmine:redmine ./
# Thu, 21 Jun 2018 10:09:09 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		freetds-dev 		gcc 		libmagickcore-dev 		libmagickwand-dev 		libmysqlclient-dev 		libpq-dev 		libsqlite3-dev 		make 		patch 	; 	rm -rf /var/lib/apt/lists/*; 		bundle install --without development test; 	for adapter in mysql2 postgresql sqlserver sqlite3; do 		echo "$RAILS_ENV:" > ./config/database.yml; 		echo "  adapter: $adapter" >> ./config/database.yml; 		bundle install --without development test; 		cp Gemfile.lock "Gemfile.lock.${adapter}"; 	done; 	rm ./config/database.yml; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| grep -v '^/usr/local/' 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false
# Thu, 21 Jun 2018 10:09:12 GMT
VOLUME [/usr/src/redmine/files]
# Thu, 21 Jun 2018 10:09:12 GMT
COPY file:8064eeba1336402e59165b07c73d0734f58aa7e83e3c0a42b6888098f2e2c11d in / 
# Thu, 21 Jun 2018 10:09:14 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Thu, 21 Jun 2018 10:09:15 GMT
EXPOSE 3000/tcp
# Thu, 21 Jun 2018 10:09:19 GMT
CMD ["rails" "server" "-b" "0.0.0.0"]
```

-	Layers:
	-	`sha256:2668401c9f940b1d6b03e5f0086fa248cb957610ef9a7c79983d2fb0707ec76c`  
		Last Modified: Sat, 28 Apr 2018 08:24:36 GMT  
		Size: 53.4 MB (53392811 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ab444779be019b7a69946ce8e93e0062d82eedfe747470714b266730847305b0`  
		Last Modified: Sat, 28 Apr 2018 12:15:08 GMT  
		Size: 10.1 MB (10137971 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b6bfab4f27e54de1711e2752ce393ce141c20aef64a8cd42d95a20585d28fa73`  
		Last Modified: Sat, 28 Apr 2018 12:15:04 GMT  
		Size: 207.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8b15968d0ad41cd76cb81ece13f4d2ca5a0d8d6e4579ae1e619f8ddd2ad295c2`  
		Last Modified: Thu, 24 May 2018 11:43:15 GMT  
		Size: 21.8 MB (21757239 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:351a7ed5b215a7bd4c196ac77237a20aec73a9a6665d2224deead4283218f7d6`  
		Last Modified: Fri, 25 May 2018 09:32:02 GMT  
		Size: 183.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6bd39d3e6422d52b16dfac40b0f9fd915fe70de5266ff6e1c6a545538a617171`  
		Last Modified: Sat, 26 May 2018 10:28:52 GMT  
		Size: 2.1 KB (2122 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b890c32c8a35b49718465b739aa29851ea5d09645363047bcfd2646d0c7e59d2`  
		Last Modified: Sat, 26 May 2018 10:28:53 GMT  
		Size: 13.1 MB (13113602 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4a2678fca66b07491a24dbcff3ff476be318e02d27a9fa400cad6b5f547dd076`  
		Last Modified: Sat, 26 May 2018 10:28:49 GMT  
		Size: 469.8 KB (469848 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c4a046b512a788097cb981ae07112f3acf9a3a7e482327497e84752c042b0e3d`  
		Last Modified: Sat, 26 May 2018 10:28:49 GMT  
		Size: 8.6 KB (8645 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bbb5e064795a21c6fe2b678532828599dfeca38475f384ae401a3452917112a2`  
		Last Modified: Thu, 21 Jun 2018 10:24:26 GMT  
		Size: 58.6 MB (58565791 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8a889f049e1545e24c2d4646d29bf7b0a3e0f72f2d286d8c219dbe346c08efb9`  
		Last Modified: Thu, 21 Jun 2018 10:24:09 GMT  
		Size: 172.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7da14007fe0da424adf4a75292ded9fae229448fbca2f31fd9be25d875290f85`  
		Last Modified: Thu, 21 Jun 2018 10:24:10 GMT  
		Size: 2.5 MB (2457580 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ccc76284d5a2c5b70dc71348dd65954b145b82b10252ae4c34b4960f37e90b86`  
		Last Modified: Thu, 21 Jun 2018 10:24:30 GMT  
		Size: 90.0 MB (89999138 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f957288162825d819debf1f6f7c10ee1f44c5bd0d99f411380a51626910bda76`  
		Last Modified: Thu, 21 Jun 2018 10:24:10 GMT  
		Size: 1.8 KB (1789 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `redmine:3.4` - linux; s390x

```console
$ docker pull redmine@sha256:30b50ca230b2b96668f067c3aa64f4ab650c5d0f58b705b9475e8eb036d65f63
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **254.9 MB (254937140 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:924bf921e4b13986dd1234309bc076c1a40bf4134fc02b23ec26aac9448fc0e1`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["rails","server","-b","0.0.0.0"]`

```dockerfile
# Sat, 28 Apr 2018 11:42:31 GMT
ADD file:ac1cfec75c7e1898f2c9b7d17653da3684fdda7d14440ce16f1939bb66105cdc in / 
# Sat, 28 Apr 2018 11:42:31 GMT
CMD ["bash"]
# Sat, 28 Apr 2018 15:34:23 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Sat, 28 Apr 2018 15:34:24 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Sat, 28 Apr 2018 15:34:24 GMT
ENV RUBY_MAJOR=2.4
# Sat, 28 Apr 2018 15:34:24 GMT
ENV RUBY_VERSION=2.4.4
# Sat, 28 Apr 2018 15:34:24 GMT
ENV RUBY_DOWNLOAD_SHA256=1d0034071d675193ca769f64c91827e5f54cb3a7962316a41d5217c7bc6949f0
# Thu, 24 May 2018 13:16:30 GMT
ENV RUBYGEMS_VERSION=2.7.7
# Thu, 24 May 2018 13:16:30 GMT
ENV BUNDLER_VERSION=1.16.2
# Thu, 24 May 2018 13:19:35 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		dpkg-dev 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 		xz-utils 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& dpkg-query --show --showformat '${package}\n' 		| grep -P '^libreadline\d+$' 		| xargs apt-mark manual 	&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force 	&& rm -r /root/.gem/
# Thu, 24 May 2018 13:19:35 GMT
ENV GEM_HOME=/usr/local/bundle
# Fri, 25 May 2018 11:58:16 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Fri, 25 May 2018 11:58:17 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/bundle/gems/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 25 May 2018 11:58:17 GMT
RUN mkdir -p "$GEM_HOME" && chmod 777 "$GEM_HOME"
# Fri, 25 May 2018 11:58:18 GMT
CMD ["irb"]
# Sat, 26 May 2018 13:25:59 GMT
RUN groupadd -r redmine && useradd -r -g redmine redmine
# Sat, 26 May 2018 13:26:09 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		wget 	&& rm -rf /var/lib/apt/lists/*
# Sat, 26 May 2018 13:26:09 GMT
ENV GOSU_VERSION=1.10
# Sat, 26 May 2018 13:26:11 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Sat, 26 May 2018 13:26:12 GMT
ENV TINI_VERSION=v0.16.1
# Sat, 26 May 2018 13:26:14 GMT
RUN set -x 	&& wget -O /usr/local/bin/tini "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/tini.asc "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5 	&& gpg --batch --verify /usr/local/bin/tini.asc /usr/local/bin/tini 	&& rm -r "$GNUPGHOME" /usr/local/bin/tini.asc 	&& chmod +x /usr/local/bin/tini 	&& tini -h
# Thu, 21 Jun 2018 13:40:18 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		imagemagick 		mercurial 		openssh-client 		subversion 	&& rm -rf /var/lib/apt/lists/*
# Thu, 21 Jun 2018 13:40:20 GMT
ENV RAILS_ENV=production
# Thu, 21 Jun 2018 13:40:20 GMT
WORKDIR /usr/src/redmine
# Thu, 21 Jun 2018 13:40:20 GMT
ENV REDMINE_VERSION=3.4.6
# Thu, 21 Jun 2018 13:40:20 GMT
ENV REDMINE_DOWNLOAD_MD5=5f4993446ecf25782f469763c0d32ea1
# Thu, 21 Jun 2018 13:40:23 GMT
RUN wget -O redmine.tar.gz "https://www.redmine.org/releases/redmine-${REDMINE_VERSION}.tar.gz" 	&& echo "$REDMINE_DOWNLOAD_MD5 redmine.tar.gz" | md5sum -c - 	&& tar -xvf redmine.tar.gz --strip-components=1 	&& rm redmine.tar.gz files/delete.me log/delete.me 	&& mkdir -p tmp/pdf public/plugin_assets 	&& chown -R redmine:redmine ./
# Thu, 21 Jun 2018 13:43:55 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		freetds-dev 		gcc 		libmagickcore-dev 		libmagickwand-dev 		libmysqlclient-dev 		libpq-dev 		libsqlite3-dev 		make 		patch 	; 	rm -rf /var/lib/apt/lists/*; 		bundle install --without development test; 	for adapter in mysql2 postgresql sqlserver sqlite3; do 		echo "$RAILS_ENV:" > ./config/database.yml; 		echo "  adapter: $adapter" >> ./config/database.yml; 		bundle install --without development test; 		cp Gemfile.lock "Gemfile.lock.${adapter}"; 	done; 	rm ./config/database.yml; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| grep -v '^/usr/local/' 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false
# Thu, 21 Jun 2018 13:43:56 GMT
VOLUME [/usr/src/redmine/files]
# Thu, 21 Jun 2018 13:43:56 GMT
COPY file:8064eeba1336402e59165b07c73d0734f58aa7e83e3c0a42b6888098f2e2c11d in / 
# Thu, 21 Jun 2018 13:43:57 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Thu, 21 Jun 2018 13:43:57 GMT
EXPOSE 3000/tcp
# Thu, 21 Jun 2018 13:43:57 GMT
CMD ["rails" "server" "-b" "0.0.0.0"]
```

-	Layers:
	-	`sha256:e0524893a6d25f3e36c190fea678ecf1845e7c0d2ba833b077a429d64b943e0a`  
		Last Modified: Sat, 28 Apr 2018 11:47:52 GMT  
		Size: 54.5 MB (54465857 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:61347f1daff97305b17924679d0a40043c3c68c04ecd38580c03a9f5f14cc025`  
		Last Modified: Sat, 28 Apr 2018 16:00:45 GMT  
		Size: 10.0 MB (9963110 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4516576626d0afc4ce307a23343efc17d8fa199788465d6fb1966c6e38405270`  
		Last Modified: Sat, 28 Apr 2018 16:00:42 GMT  
		Size: 205.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5db3c4bbb862bf979405dbf70d32620b3868872a06f125c0636aa2ca5d9a8118`  
		Last Modified: Thu, 24 May 2018 13:48:49 GMT  
		Size: 21.7 MB (21709046 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cc118bcf2202904ad8addf51827feb3eb0be972ee9912cfef0c03d939af4af5d`  
		Last Modified: Fri, 25 May 2018 12:08:37 GMT  
		Size: 148.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0bedd5671d7bb05f77a136f485548dd94b826bcaeca59790f44d37972cac966c`  
		Last Modified: Sat, 26 May 2018 13:34:13 GMT  
		Size: 2.1 KB (2107 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:df0ad57d1afd283e6ea7a12a3fdb17282925a2ac6c8fc1e0b18594b70f4860d8`  
		Last Modified: Sat, 26 May 2018 13:34:15 GMT  
		Size: 13.1 MB (13130009 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:38f941c2e8a178296eb5ef00af421a44bd40170e8b4535faf85b8c0f669e4127`  
		Last Modified: Sat, 26 May 2018 13:34:13 GMT  
		Size: 486.8 KB (486831 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2b65703d4fed12215b832fd6eb431e15ec6df3ea624470903495fa95675645b2`  
		Last Modified: Sat, 26 May 2018 13:34:11 GMT  
		Size: 8.6 KB (8628 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:147ee1fc1b1a421958c0c5f1e52aa1fcd3bb3db7c6b68f6c4c69b8daa4356bdd`  
		Last Modified: Thu, 21 Jun 2018 13:47:39 GMT  
		Size: 59.5 MB (59533196 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:33fc24964afaca53a8f69b089f296f90016a97249c28644192e99669d94ca950`  
		Last Modified: Thu, 21 Jun 2018 13:47:26 GMT  
		Size: 139.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:95937785bb16f99b2d94476fe49fab2418fd81f458a9214d61406057d60561f7`  
		Last Modified: Thu, 21 Jun 2018 13:47:27 GMT  
		Size: 2.5 MB (2456908 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5621a26308c9d8073f8ef0d18bc14689e45b96da0d71fe09658c0311b4578690`  
		Last Modified: Thu, 21 Jun 2018 13:47:43 GMT  
		Size: 93.2 MB (93179163 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1ff10f665c615aa7ed26b1dd97eec9db4674eb2affa120fb7b23dc95d1b52b7c`  
		Last Modified: Thu, 21 Jun 2018 13:47:26 GMT  
		Size: 1.8 KB (1793 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `redmine:3.4.6`

```console
$ docker pull redmine@sha256:7439dde0eae47d823c35e7f2e4c47d7cbb8b55dbf29844a2579fbd982421d3d3
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm variant v5
	-	linux; arm variant v7
	-	linux; arm64 variant v8
	-	linux; 386
	-	linux; ppc64le
	-	linux; s390x

### `redmine:3.4.6` - linux; amd64

```console
$ docker pull redmine@sha256:8dce5627271a3f21cd6ce5a3a29c6fbc11fcc99a0ca69d6e6e5882d8ecf4f196
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **250.7 MB (250669098 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:ebd79f5f9bc1c650b0f487dec3b167164c2c36f649ba15d25dbde5ddaae76fe0`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["rails","server","-b","0.0.0.0"]`

```dockerfile
# Sat, 28 Apr 2018 06:44:15 GMT
ADD file:3e6141c0c9cb74b14a281eb3ab7aaf162a625733e652c3948b323bb2ec8b4343 in / 
# Sat, 28 Apr 2018 06:44:16 GMT
CMD ["bash"]
# Sun, 29 Apr 2018 16:52:40 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Sun, 29 Apr 2018 16:52:41 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Sun, 29 Apr 2018 16:52:42 GMT
ENV RUBY_MAJOR=2.4
# Sun, 29 Apr 2018 16:52:42 GMT
ENV RUBY_VERSION=2.4.4
# Sun, 29 Apr 2018 16:52:42 GMT
ENV RUBY_DOWNLOAD_SHA256=1d0034071d675193ca769f64c91827e5f54cb3a7962316a41d5217c7bc6949f0
# Thu, 24 May 2018 01:25:52 GMT
ENV RUBYGEMS_VERSION=2.7.7
# Thu, 24 May 2018 01:25:52 GMT
ENV BUNDLER_VERSION=1.16.2
# Thu, 24 May 2018 01:29:14 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		dpkg-dev 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 		xz-utils 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& dpkg-query --show --showformat '${package}\n' 		| grep -P '^libreadline\d+$' 		| xargs apt-mark manual 	&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force 	&& rm -r /root/.gem/
# Thu, 24 May 2018 01:29:14 GMT
ENV GEM_HOME=/usr/local/bundle
# Thu, 24 May 2018 21:08:01 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Thu, 24 May 2018 21:08:02 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/bundle/gems/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Thu, 24 May 2018 21:08:02 GMT
RUN mkdir -p "$GEM_HOME" && chmod 777 "$GEM_HOME"
# Thu, 24 May 2018 21:08:03 GMT
CMD ["irb"]
# Fri, 25 May 2018 22:37:54 GMT
RUN groupadd -r redmine && useradd -r -g redmine redmine
# Fri, 25 May 2018 22:38:14 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		wget 	&& rm -rf /var/lib/apt/lists/*
# Fri, 25 May 2018 22:38:14 GMT
ENV GOSU_VERSION=1.10
# Fri, 25 May 2018 22:38:18 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Fri, 25 May 2018 22:38:18 GMT
ENV TINI_VERSION=v0.16.1
# Fri, 25 May 2018 22:38:20 GMT
RUN set -x 	&& wget -O /usr/local/bin/tini "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/tini.asc "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5 	&& gpg --batch --verify /usr/local/bin/tini.asc /usr/local/bin/tini 	&& rm -r "$GNUPGHOME" /usr/local/bin/tini.asc 	&& chmod +x /usr/local/bin/tini 	&& tini -h
# Wed, 20 Jun 2018 21:28:18 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		imagemagick 		mercurial 		openssh-client 		subversion 	&& rm -rf /var/lib/apt/lists/*
# Wed, 20 Jun 2018 21:28:18 GMT
ENV RAILS_ENV=production
# Wed, 20 Jun 2018 21:28:19 GMT
WORKDIR /usr/src/redmine
# Wed, 20 Jun 2018 21:28:19 GMT
ENV REDMINE_VERSION=3.4.6
# Wed, 20 Jun 2018 21:28:19 GMT
ENV REDMINE_DOWNLOAD_MD5=5f4993446ecf25782f469763c0d32ea1
# Wed, 20 Jun 2018 21:28:23 GMT
RUN wget -O redmine.tar.gz "https://www.redmine.org/releases/redmine-${REDMINE_VERSION}.tar.gz" 	&& echo "$REDMINE_DOWNLOAD_MD5 redmine.tar.gz" | md5sum -c - 	&& tar -xvf redmine.tar.gz --strip-components=1 	&& rm redmine.tar.gz files/delete.me log/delete.me 	&& mkdir -p tmp/pdf public/plugin_assets 	&& chown -R redmine:redmine ./
# Wed, 20 Jun 2018 21:31:54 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		freetds-dev 		gcc 		libmagickcore-dev 		libmagickwand-dev 		libmysqlclient-dev 		libpq-dev 		libsqlite3-dev 		make 		patch 	; 	rm -rf /var/lib/apt/lists/*; 		bundle install --without development test; 	for adapter in mysql2 postgresql sqlserver sqlite3; do 		echo "$RAILS_ENV:" > ./config/database.yml; 		echo "  adapter: $adapter" >> ./config/database.yml; 		bundle install --without development test; 		cp Gemfile.lock "Gemfile.lock.${adapter}"; 	done; 	rm ./config/database.yml; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| grep -v '^/usr/local/' 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false
# Wed, 20 Jun 2018 21:31:54 GMT
VOLUME [/usr/src/redmine/files]
# Wed, 20 Jun 2018 21:31:54 GMT
COPY file:8064eeba1336402e59165b07c73d0734f58aa7e83e3c0a42b6888098f2e2c11d in / 
# Wed, 20 Jun 2018 21:31:55 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Wed, 20 Jun 2018 21:31:55 GMT
EXPOSE 3000/tcp
# Wed, 20 Jun 2018 21:31:55 GMT
CMD ["rails" "server" "-b" "0.0.0.0"]
```

-	Layers:
	-	`sha256:3d77ce4481b119f00e53bee9b4a443469c42c224db954ddaa2e6b74cd73cd5d0`  
		Last Modified: Sat, 28 Apr 2018 08:24:47 GMT  
		Size: 54.3 MB (54262566 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:05a78650ca91970038096c478f5bc7b8155cf0226db13c86ccf40e0e476e23d5`  
		Last Modified: Sun, 29 Apr 2018 19:33:59 GMT  
		Size: 10.2 MB (10168983 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:860996a55f7fba99ae60e7be5fc25d885d982031d74467b9bcfc84f96e72def6`  
		Last Modified: Sun, 29 Apr 2018 19:33:57 GMT  
		Size: 205.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0af7e9644f308307bcbf19ad9eea243ce5dd469c0211039f47b3120cabdfc99c`  
		Last Modified: Thu, 24 May 2018 02:02:57 GMT  
		Size: 21.3 MB (21305911 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3c2741f1d4c75227c788ea0d4f97b9d842c26908b326b7341255dc08df8c2ff0`  
		Last Modified: Thu, 24 May 2018 21:16:41 GMT  
		Size: 149.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:085bf055e4f7fca4100b86db549ca65dbd113d5633f293b7d60c64580e40fc9c`  
		Last Modified: Fri, 25 May 2018 22:53:00 GMT  
		Size: 2.1 KB (2100 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:02757c5b4f758477ace554b047238004f1ba80dd0253f13e4afde2cff60c8fe2`  
		Last Modified: Fri, 25 May 2018 22:53:02 GMT  
		Size: 13.0 MB (12967769 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0b812d52f0b76913f780e051066b0aec46d9f1a2bc758a19b4872c304bf83525`  
		Last Modified: Fri, 25 May 2018 22:52:57 GMT  
		Size: 500.7 KB (500671 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a1ee2b52aad93348e461129e48f8cb4e4cbc9418e7363ce6ed71b679ed0da25e`  
		Last Modified: Fri, 25 May 2018 22:52:58 GMT  
		Size: 8.5 KB (8506 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:50ec0628480d6092f4ac1c09226941258eaa856ae2b192f54b82351b8147c5a2`  
		Last Modified: Wed, 20 Jun 2018 21:49:29 GMT  
		Size: 59.7 MB (59702353 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d7d52a5fdbb89bea397274ff00985194056ee68db884b686daa2e63575fa3730`  
		Last Modified: Wed, 20 Jun 2018 21:49:09 GMT  
		Size: 140.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:079a05a37d0bc8ec6e3819f8806a9ff391a4c3ff38e3c35679acabccd7281ed1`  
		Last Modified: Wed, 20 Jun 2018 21:49:11 GMT  
		Size: 2.5 MB (2456917 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:828f67b9c47148252d063a4e719ca8ed0be6c8a2487a5ac84f2bade3fd5e83ae`  
		Last Modified: Wed, 20 Jun 2018 21:49:35 GMT  
		Size: 89.3 MB (89291037 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d4660d39964eb0750734643da738a9352ccb35da2e28172ac5340f00f0cd40ea`  
		Last Modified: Wed, 20 Jun 2018 21:49:09 GMT  
		Size: 1.8 KB (1791 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `redmine:3.4.6` - linux; arm variant v5

```console
$ docker pull redmine@sha256:6d3319e8e0caf66469e15cba6f9b18da2b9994eaae19de97012d1aa9bf8c0402
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **244.2 MB (244218136 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:6b0e3d8938719b59edef5744897ff446a575e4be6543a6de3b33e801b768a7fc`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["rails","server","-b","0.0.0.0"]`

```dockerfile
# Sat, 28 Apr 2018 08:49:23 GMT
ADD file:2d2cd360e66aeff5557c7e7117985a00d109278c3f456ee970afcc9a46483264 in / 
# Sat, 28 Apr 2018 08:49:23 GMT
CMD ["bash"]
# Sat, 28 Apr 2018 11:50:09 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Sat, 28 Apr 2018 11:50:10 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Sat, 28 Apr 2018 11:50:11 GMT
ENV RUBY_MAJOR=2.4
# Sat, 28 Apr 2018 11:50:11 GMT
ENV RUBY_VERSION=2.4.4
# Sat, 28 Apr 2018 11:50:11 GMT
ENV RUBY_DOWNLOAD_SHA256=1d0034071d675193ca769f64c91827e5f54cb3a7962316a41d5217c7bc6949f0
# Thu, 24 May 2018 10:56:19 GMT
ENV RUBYGEMS_VERSION=2.7.7
# Thu, 24 May 2018 10:56:19 GMT
ENV BUNDLER_VERSION=1.16.2
# Thu, 24 May 2018 11:02:19 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		dpkg-dev 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 		xz-utils 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& dpkg-query --show --showformat '${package}\n' 		| grep -P '^libreadline\d+$' 		| xargs apt-mark manual 	&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force 	&& rm -r /root/.gem/
# Thu, 24 May 2018 11:02:20 GMT
ENV GEM_HOME=/usr/local/bundle
# Fri, 25 May 2018 09:09:45 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Fri, 25 May 2018 09:09:45 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/bundle/gems/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 25 May 2018 09:09:46 GMT
RUN mkdir -p "$GEM_HOME" && chmod 777 "$GEM_HOME"
# Fri, 25 May 2018 09:09:47 GMT
CMD ["irb"]
# Sat, 26 May 2018 10:03:35 GMT
RUN groupadd -r redmine && useradd -r -g redmine redmine
# Sat, 26 May 2018 10:04:04 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		wget 	&& rm -rf /var/lib/apt/lists/*
# Sat, 26 May 2018 10:04:04 GMT
ENV GOSU_VERSION=1.10
# Sat, 26 May 2018 10:04:06 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Sat, 26 May 2018 10:04:06 GMT
ENV TINI_VERSION=v0.16.1
# Sat, 26 May 2018 10:04:08 GMT
RUN set -x 	&& wget -O /usr/local/bin/tini "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/tini.asc "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5 	&& gpg --batch --verify /usr/local/bin/tini.asc /usr/local/bin/tini 	&& rm -r "$GNUPGHOME" /usr/local/bin/tini.asc 	&& chmod +x /usr/local/bin/tini 	&& tini -h
# Thu, 21 Jun 2018 09:33:55 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		imagemagick 		mercurial 		openssh-client 		subversion 	&& rm -rf /var/lib/apt/lists/*
# Thu, 21 Jun 2018 09:33:55 GMT
ENV RAILS_ENV=production
# Thu, 21 Jun 2018 09:33:56 GMT
WORKDIR /usr/src/redmine
# Thu, 21 Jun 2018 09:33:56 GMT
ENV REDMINE_VERSION=3.4.6
# Thu, 21 Jun 2018 09:33:56 GMT
ENV REDMINE_DOWNLOAD_MD5=5f4993446ecf25782f469763c0d32ea1
# Thu, 21 Jun 2018 09:34:00 GMT
RUN wget -O redmine.tar.gz "https://www.redmine.org/releases/redmine-${REDMINE_VERSION}.tar.gz" 	&& echo "$REDMINE_DOWNLOAD_MD5 redmine.tar.gz" | md5sum -c - 	&& tar -xvf redmine.tar.gz --strip-components=1 	&& rm redmine.tar.gz files/delete.me log/delete.me 	&& mkdir -p tmp/pdf public/plugin_assets 	&& chown -R redmine:redmine ./
# Thu, 21 Jun 2018 09:40:16 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		freetds-dev 		gcc 		libmagickcore-dev 		libmagickwand-dev 		libmysqlclient-dev 		libpq-dev 		libsqlite3-dev 		make 		patch 	; 	rm -rf /var/lib/apt/lists/*; 		bundle install --without development test; 	for adapter in mysql2 postgresql sqlserver sqlite3; do 		echo "$RAILS_ENV:" > ./config/database.yml; 		echo "  adapter: $adapter" >> ./config/database.yml; 		bundle install --without development test; 		cp Gemfile.lock "Gemfile.lock.${adapter}"; 	done; 	rm ./config/database.yml; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| grep -v '^/usr/local/' 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false
# Thu, 21 Jun 2018 09:40:17 GMT
VOLUME [/usr/src/redmine/files]
# Thu, 21 Jun 2018 09:40:17 GMT
COPY file:8064eeba1336402e59165b07c73d0734f58aa7e83e3c0a42b6888098f2e2c11d in / 
# Thu, 21 Jun 2018 09:40:17 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Thu, 21 Jun 2018 09:40:17 GMT
EXPOSE 3000/tcp
# Thu, 21 Jun 2018 09:40:18 GMT
CMD ["rails" "server" "-b" "0.0.0.0"]
```

-	Layers:
	-	`sha256:81fc0826192f72abe617753d378af4047dbce89faf17cdab9166877006a25d8e`  
		Last Modified: Sat, 28 Apr 2018 08:57:10 GMT  
		Size: 52.5 MB (52456037 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2119f18fa6f270436c891e0c459923ae24657bf4a8be20cfcfe964e7aa64b7b2`  
		Last Modified: Sat, 28 Apr 2018 12:31:30 GMT  
		Size: 9.1 MB (9119888 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:51757db9404a98c26c96cb6b65e8c7893c1e1b5ea9774a5786abe9ec88468cf3`  
		Last Modified: Sat, 28 Apr 2018 12:31:26 GMT  
		Size: 206.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:09fe38be652b02d310bce0a19598fe366080a17713f114eeb33355e15f6bf8c0`  
		Last Modified: Thu, 24 May 2018 11:29:31 GMT  
		Size: 21.1 MB (21074760 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:63fc7f9b6584b1727a86e7d2130c3f4129978990791d89d6af0f9950997cc782`  
		Last Modified: Fri, 25 May 2018 09:17:51 GMT  
		Size: 182.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bdbf4bf93be2e977124205e4f60ae3ba2a2f880c269a494237a056a419343587`  
		Last Modified: Sat, 26 May 2018 10:18:09 GMT  
		Size: 2.1 KB (2090 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:98b6a7f079c3c2475a4ae64a2f970ab18867099384ac59e88b28b14c37d777fc`  
		Last Modified: Sat, 26 May 2018 10:18:11 GMT  
		Size: 12.8 MB (12772572 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:33fbc82bebefed415e0d99d95c2199ccefd11254cfbefe0cb44e5c4235a80dbc`  
		Last Modified: Sat, 26 May 2018 10:18:06 GMT  
		Size: 491.1 KB (491125 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:494ed27bef31be226f9bb0b7dde7a3de53fee37d4a9defca95c65999a45bf288`  
		Last Modified: Sat, 26 May 2018 10:18:06 GMT  
		Size: 7.8 KB (7850 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:260011ea13c12e7f76c6ef3f3b6ac329067d5d62b1c3ea2e1438fc4d24c6e9f2`  
		Last Modified: Thu, 21 Jun 2018 09:46:58 GMT  
		Size: 57.1 MB (57055867 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7682be80ee6471502bcde4c8a3d03401fe0f247174899f7a298ea324b24bbaf8`  
		Last Modified: Thu, 21 Jun 2018 09:46:39 GMT  
		Size: 172.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e64810335b2932687826690900537543be72f782fbeb739f26c18c27c3f1a048`  
		Last Modified: Thu, 21 Jun 2018 09:46:41 GMT  
		Size: 2.5 MB (2457560 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:12da0e4bca312d2c2db7b5c9dc56916f4b56b158b309d62ae947b273fd04b8db`  
		Last Modified: Thu, 21 Jun 2018 09:47:03 GMT  
		Size: 88.8 MB (88778036 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b0398911b75ac4341523e8856acb1f5668b263bc57152d9ec5abda35b5ee15bd`  
		Last Modified: Thu, 21 Jun 2018 09:46:40 GMT  
		Size: 1.8 KB (1791 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `redmine:3.4.6` - linux; arm variant v7

```console
$ docker pull redmine@sha256:df7144a1137742adc5e4e11125da5e4d18e517fe491950489f2f97452b2522bf
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **238.4 MB (238431615 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:f661101282a8e3e492241307b1e3a098dbc6f66588f65c554e6267e3fa781492`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["rails","server","-b","0.0.0.0"]`

```dockerfile
# Sat, 28 Apr 2018 11:59:05 GMT
ADD file:4e9c283075c120ce66f83bf541b0aeaa8a46f74c21d38e4ab1578e7f1b892823 in / 
# Sat, 28 Apr 2018 11:59:05 GMT
CMD ["bash"]
# Sat, 28 Apr 2018 15:40:52 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Sat, 28 Apr 2018 15:40:56 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Sat, 28 Apr 2018 15:40:56 GMT
ENV RUBY_MAJOR=2.4
# Sat, 28 Apr 2018 15:40:57 GMT
ENV RUBY_VERSION=2.4.4
# Sat, 28 Apr 2018 15:40:57 GMT
ENV RUBY_DOWNLOAD_SHA256=1d0034071d675193ca769f64c91827e5f54cb3a7962316a41d5217c7bc6949f0
# Thu, 24 May 2018 13:13:30 GMT
ENV RUBYGEMS_VERSION=2.7.7
# Thu, 24 May 2018 13:13:31 GMT
ENV BUNDLER_VERSION=1.16.2
# Thu, 24 May 2018 13:18:52 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		dpkg-dev 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 		xz-utils 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& dpkg-query --show --showformat '${package}\n' 		| grep -P '^libreadline\d+$' 		| xargs apt-mark manual 	&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force 	&& rm -r /root/.gem/
# Thu, 24 May 2018 13:18:53 GMT
ENV GEM_HOME=/usr/local/bundle
# Fri, 25 May 2018 12:27:41 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Fri, 25 May 2018 12:27:42 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/bundle/gems/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 25 May 2018 12:27:43 GMT
RUN mkdir -p "$GEM_HOME" && chmod 777 "$GEM_HOME"
# Fri, 25 May 2018 12:27:43 GMT
CMD ["irb"]
# Sat, 26 May 2018 12:23:55 GMT
RUN groupadd -r redmine && useradd -r -g redmine redmine
# Sat, 26 May 2018 12:24:22 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		wget 	&& rm -rf /var/lib/apt/lists/*
# Sat, 26 May 2018 12:24:22 GMT
ENV GOSU_VERSION=1.10
# Sat, 26 May 2018 12:24:24 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Sat, 26 May 2018 12:24:24 GMT
ENV TINI_VERSION=v0.16.1
# Sat, 26 May 2018 12:24:26 GMT
RUN set -x 	&& wget -O /usr/local/bin/tini "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/tini.asc "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5 	&& gpg --batch --verify /usr/local/bin/tini.asc /usr/local/bin/tini 	&& rm -r "$GNUPGHOME" /usr/local/bin/tini.asc 	&& chmod +x /usr/local/bin/tini 	&& tini -h
# Thu, 21 Jun 2018 12:06:34 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		imagemagick 		mercurial 		openssh-client 		subversion 	&& rm -rf /var/lib/apt/lists/*
# Thu, 21 Jun 2018 12:06:34 GMT
ENV RAILS_ENV=production
# Thu, 21 Jun 2018 12:06:34 GMT
WORKDIR /usr/src/redmine
# Thu, 21 Jun 2018 12:06:35 GMT
ENV REDMINE_VERSION=3.4.6
# Thu, 21 Jun 2018 12:06:35 GMT
ENV REDMINE_DOWNLOAD_MD5=5f4993446ecf25782f469763c0d32ea1
# Thu, 21 Jun 2018 12:06:39 GMT
RUN wget -O redmine.tar.gz "https://www.redmine.org/releases/redmine-${REDMINE_VERSION}.tar.gz" 	&& echo "$REDMINE_DOWNLOAD_MD5 redmine.tar.gz" | md5sum -c - 	&& tar -xvf redmine.tar.gz --strip-components=1 	&& rm redmine.tar.gz files/delete.me log/delete.me 	&& mkdir -p tmp/pdf public/plugin_assets 	&& chown -R redmine:redmine ./
# Thu, 21 Jun 2018 12:12:24 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		freetds-dev 		gcc 		libmagickcore-dev 		libmagickwand-dev 		libmysqlclient-dev 		libpq-dev 		libsqlite3-dev 		make 		patch 	; 	rm -rf /var/lib/apt/lists/*; 		bundle install --without development test; 	for adapter in mysql2 postgresql sqlserver sqlite3; do 		echo "$RAILS_ENV:" > ./config/database.yml; 		echo "  adapter: $adapter" >> ./config/database.yml; 		bundle install --without development test; 		cp Gemfile.lock "Gemfile.lock.${adapter}"; 	done; 	rm ./config/database.yml; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| grep -v '^/usr/local/' 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false
# Thu, 21 Jun 2018 12:12:25 GMT
VOLUME [/usr/src/redmine/files]
# Thu, 21 Jun 2018 12:12:25 GMT
COPY file:8064eeba1336402e59165b07c73d0734f58aa7e83e3c0a42b6888098f2e2c11d in / 
# Thu, 21 Jun 2018 12:12:25 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Thu, 21 Jun 2018 12:12:26 GMT
EXPOSE 3000/tcp
# Thu, 21 Jun 2018 12:12:26 GMT
CMD ["rails" "server" "-b" "0.0.0.0"]
```

-	Layers:
	-	`sha256:5c478157e28e3c26a0209484edb518799e1c21863d4700579c010b7203e0537f`  
		Last Modified: Sat, 28 Apr 2018 12:10:24 GMT  
		Size: 50.2 MB (50195697 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:57cc82e3a61290e4bfc39b7ec615f84e7782d645852ff04b0f1077ba3a8d6c85`  
		Last Modified: Sat, 28 Apr 2018 16:21:20 GMT  
		Size: 8.8 MB (8777726 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e60d4b7c236d855ddd6a1f286ece09d909ea721b8959a806142de215e84ad242`  
		Last Modified: Sat, 28 Apr 2018 16:21:17 GMT  
		Size: 207.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fd714148500451500a2957112b77e7e1feb9b7fa3095266d84623a097aa9935b`  
		Last Modified: Thu, 24 May 2018 13:51:44 GMT  
		Size: 20.9 MB (20939873 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:15b699e7e8d225b3c8087b29914345882f41c75520d205595171039ab1e0c856`  
		Last Modified: Fri, 25 May 2018 12:40:08 GMT  
		Size: 182.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0e957186fb243adf5019585383bf19defaa1d82b4636998b537528235dd777f2`  
		Last Modified: Sat, 26 May 2018 12:37:45 GMT  
		Size: 2.1 KB (2092 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:11e22cb6dff3aef6e6185c86a85889793c9f7fff65d461c749557bc8884b9624`  
		Last Modified: Sat, 26 May 2018 12:37:50 GMT  
		Size: 12.6 MB (12629462 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9726b5b13c21e003fe07315e1e1f21db27480310aa0606a5699f7435f62801cf`  
		Last Modified: Sat, 26 May 2018 12:37:45 GMT  
		Size: 475.3 KB (475267 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3784a11f9e4def9da3250391267c9bcffd3edd695febdb607895c2fa1524e923`  
		Last Modified: Sat, 26 May 2018 12:37:44 GMT  
		Size: 7.3 KB (7313 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1374393c860f34b65841b3158be787bc2df985c718b0bd332c8d8c7428a83e52`  
		Last Modified: Thu, 21 Jun 2018 12:18:49 GMT  
		Size: 54.7 MB (54698588 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:42db57f6861effae6af53fac1d6db5790da8afb4d14f64a0f0f22aba5649080e`  
		Last Modified: Thu, 21 Jun 2018 12:18:32 GMT  
		Size: 172.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:590497ab77d278095f81c2e419971e26ef0d6483e14a0b97ed13f8ec94a76f83`  
		Last Modified: Thu, 21 Jun 2018 12:18:34 GMT  
		Size: 2.5 MB (2457572 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d3918493345313d19d0cbd4c26bd6142b71be53be71d3976bbd956e00a1c7da8`  
		Last Modified: Thu, 21 Jun 2018 12:18:57 GMT  
		Size: 88.2 MB (88245671 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e118f56902617fa8db9f49493a8d0039c3a90976f6506cf6df565557e09560af`  
		Last Modified: Thu, 21 Jun 2018 12:18:32 GMT  
		Size: 1.8 KB (1793 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `redmine:3.4.6` - linux; arm64 variant v8

```console
$ docker pull redmine@sha256:988df7496fea7b7cc53d5210dd1bd832b8d22cbf82fb0b9f6a7d61c366de95c4
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **243.2 MB (243226684 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:795f00ab797d1fb1e0e03e8ea4d2c01f3f953b9df56a7da35adfd390546f65a6`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["rails","server","-b","0.0.0.0"]`

```dockerfile
# Mon, 30 Apr 2018 23:21:38 GMT
ADD file:387c83918422a6546379c4d84818ca3949fcd63aec058da562b08c947a9ed571 in / 
# Mon, 30 Apr 2018 23:21:40 GMT
CMD ["bash"]
# Tue, 01 May 2018 08:41:36 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Tue, 01 May 2018 08:41:41 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Tue, 01 May 2018 08:41:42 GMT
ENV RUBY_MAJOR=2.4
# Tue, 01 May 2018 08:41:44 GMT
ENV RUBY_VERSION=2.4.4
# Tue, 01 May 2018 08:41:46 GMT
ENV RUBY_DOWNLOAD_SHA256=1d0034071d675193ca769f64c91827e5f54cb3a7962316a41d5217c7bc6949f0
# Fri, 25 May 2018 16:57:16 GMT
ENV RUBYGEMS_VERSION=2.7.7
# Fri, 25 May 2018 16:57:17 GMT
ENV BUNDLER_VERSION=1.16.2
# Fri, 25 May 2018 17:06:32 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		dpkg-dev 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 		xz-utils 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& dpkg-query --show --showformat '${package}\n' 		| grep -P '^libreadline\d+$' 		| xargs apt-mark manual 	&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force 	&& rm -r /root/.gem/
# Fri, 25 May 2018 17:06:33 GMT
ENV GEM_HOME=/usr/local/bundle
# Fri, 25 May 2018 17:06:34 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Fri, 25 May 2018 17:06:34 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/bundle/gems/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 25 May 2018 17:06:36 GMT
RUN mkdir -p "$GEM_HOME" && chmod 777 "$GEM_HOME"
# Fri, 25 May 2018 17:06:37 GMT
CMD ["irb"]
# Fri, 25 May 2018 21:43:13 GMT
RUN groupadd -r redmine && useradd -r -g redmine redmine
# Fri, 25 May 2018 21:43:38 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		wget 	&& rm -rf /var/lib/apt/lists/*
# Fri, 25 May 2018 21:43:38 GMT
ENV GOSU_VERSION=1.10
# Fri, 25 May 2018 21:43:43 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Fri, 25 May 2018 21:43:44 GMT
ENV TINI_VERSION=v0.16.1
# Fri, 25 May 2018 21:43:46 GMT
RUN set -x 	&& wget -O /usr/local/bin/tini "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/tini.asc "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5 	&& gpg --batch --verify /usr/local/bin/tini.asc /usr/local/bin/tini 	&& rm -r "$GNUPGHOME" /usr/local/bin/tini.asc 	&& chmod +x /usr/local/bin/tini 	&& tini -h
# Thu, 21 Jun 2018 16:59:11 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		imagemagick 		mercurial 		openssh-client 		subversion 	&& rm -rf /var/lib/apt/lists/*
# Thu, 21 Jun 2018 16:59:12 GMT
ENV RAILS_ENV=production
# Thu, 21 Jun 2018 16:59:13 GMT
WORKDIR /usr/src/redmine
# Thu, 21 Jun 2018 16:59:13 GMT
ENV REDMINE_VERSION=3.4.6
# Thu, 21 Jun 2018 16:59:14 GMT
ENV REDMINE_DOWNLOAD_MD5=5f4993446ecf25782f469763c0d32ea1
# Thu, 21 Jun 2018 16:59:20 GMT
RUN wget -O redmine.tar.gz "https://www.redmine.org/releases/redmine-${REDMINE_VERSION}.tar.gz" 	&& echo "$REDMINE_DOWNLOAD_MD5 redmine.tar.gz" | md5sum -c - 	&& tar -xvf redmine.tar.gz --strip-components=1 	&& rm redmine.tar.gz files/delete.me log/delete.me 	&& mkdir -p tmp/pdf public/plugin_assets 	&& chown -R redmine:redmine ./
# Thu, 21 Jun 2018 17:12:12 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		freetds-dev 		gcc 		libmagickcore-dev 		libmagickwand-dev 		libmysqlclient-dev 		libpq-dev 		libsqlite3-dev 		make 		patch 	; 	rm -rf /var/lib/apt/lists/*; 		bundle install --without development test; 	for adapter in mysql2 postgresql sqlserver sqlite3; do 		echo "$RAILS_ENV:" > ./config/database.yml; 		echo "  adapter: $adapter" >> ./config/database.yml; 		bundle install --without development test; 		cp Gemfile.lock "Gemfile.lock.${adapter}"; 	done; 	rm ./config/database.yml; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| grep -v '^/usr/local/' 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false
# Thu, 21 Jun 2018 17:12:14 GMT
VOLUME [/usr/src/redmine/files]
# Thu, 21 Jun 2018 17:12:14 GMT
COPY file:8064eeba1336402e59165b07c73d0734f58aa7e83e3c0a42b6888098f2e2c11d in / 
# Thu, 21 Jun 2018 17:12:15 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Thu, 21 Jun 2018 17:12:16 GMT
EXPOSE 3000/tcp
# Thu, 21 Jun 2018 17:12:17 GMT
CMD ["rails" "server" "-b" "0.0.0.0"]
```

-	Layers:
	-	`sha256:363cfded2ef3921ef972c85cafc77cf16cdcfddfd49782ad4540cb73fd5e57a2`  
		Last Modified: Mon, 30 Apr 2018 23:41:06 GMT  
		Size: 51.4 MB (51446854 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6aeaeeebfa7e2a1e6c69a484a7648b6313aff4bf219767667e43bbfc42bb40d9`  
		Last Modified: Tue, 01 May 2018 09:53:45 GMT  
		Size: 9.3 MB (9343083 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3b78cb3f4882a2b3bf1ecb4fdbe1e145a3ddb80ce1fde62a33ada1beaf12daf8`  
		Last Modified: Tue, 01 May 2018 09:53:41 GMT  
		Size: 205.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:18547e3cbea8ccf1a7ca22515077049b202d0f12cac441573f4edf1f9b567209`  
		Last Modified: Fri, 25 May 2018 18:07:21 GMT  
		Size: 21.3 MB (21265153 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1d6d550606a490752c05952acf272ef8a1e4df8e3a8be58f37f50260160a5b11`  
		Last Modified: Fri, 25 May 2018 18:07:10 GMT  
		Size: 148.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:548893d753de4a74e5a64d26225a85691cfd2ad2b0546591161f46916ea1229f`  
		Last Modified: Fri, 25 May 2018 22:12:00 GMT  
		Size: 2.1 KB (2113 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a5ecd4fc430347071a2c164435746340e018f58d8037eabf8dd5665ad1b0dff6`  
		Last Modified: Fri, 25 May 2018 22:12:03 GMT  
		Size: 12.9 MB (12940690 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bfc6b9486743d7946d7922a4c47f0cc78876f91c3db011553f4f9a25a1dc96e2`  
		Last Modified: Fri, 25 May 2018 22:11:58 GMT  
		Size: 468.7 KB (468701 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e8f19d3b246e0490714656220e538767a6b0f47ae8f43c10cc32017687ae3114`  
		Last Modified: Fri, 25 May 2018 22:11:58 GMT  
		Size: 8.2 KB (8154 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:33f179dd0cce7b503211ff6d22a331d47169a234442ac5b0f6d11519eb3ead53`  
		Last Modified: Thu, 21 Jun 2018 17:27:27 GMT  
		Size: 56.2 MB (56166767 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b00c8c2de88468ac5d8b2af1848ffa502eded4adfd3a7e8e3859a57018eaace6`  
		Last Modified: Thu, 21 Jun 2018 17:27:04 GMT  
		Size: 140.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:95eb29922954e0efbb03fb3ca6512c8ce0d257303fc9a551e8d52455bef6d5b1`  
		Last Modified: Thu, 21 Jun 2018 17:27:07 GMT  
		Size: 2.5 MB (2456916 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f2bfa5dcbc83e5d3cd044dfbc3d81faa5b22a07684e60e5ca7cc0c8f4c76a57f`  
		Last Modified: Thu, 21 Jun 2018 17:27:35 GMT  
		Size: 89.1 MB (89125967 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:51f3ad7cc3086c71f467f0eee89ca821bc6f3aae7bd05ce85b8eb78d72e15a94`  
		Last Modified: Thu, 21 Jun 2018 17:27:04 GMT  
		Size: 1.8 KB (1793 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `redmine:3.4.6` - linux; 386

```console
$ docker pull redmine@sha256:d87c7c46bff353bc7e6f129b084607c93da5931f3d61a8ab52a1a2e6895bf371
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **253.9 MB (253912619 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:f17b65464fff83d872964798559dc27680b6902daaba36df7306c9fa0a810e9d`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["rails","server","-b","0.0.0.0"]`

```dockerfile
# Sat, 28 Apr 2018 10:39:32 GMT
ADD file:ce5174f2b2c155a2421fac3ff37a02d9551d5d79e31a541189bcfd2416a6903a in / 
# Sat, 28 Apr 2018 10:39:32 GMT
CMD ["bash"]
# Fri, 01 Jun 2018 14:56:41 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Fri, 01 Jun 2018 14:56:42 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Fri, 01 Jun 2018 14:56:42 GMT
ENV RUBY_MAJOR=2.4
# Fri, 01 Jun 2018 14:56:42 GMT
ENV RUBY_VERSION=2.4.4
# Fri, 01 Jun 2018 14:56:42 GMT
ENV RUBY_DOWNLOAD_SHA256=1d0034071d675193ca769f64c91827e5f54cb3a7962316a41d5217c7bc6949f0
# Fri, 01 Jun 2018 14:56:42 GMT
ENV RUBYGEMS_VERSION=2.7.7
# Fri, 01 Jun 2018 14:56:42 GMT
ENV BUNDLER_VERSION=1.16.2
# Fri, 01 Jun 2018 15:04:05 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		dpkg-dev 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 		xz-utils 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& dpkg-query --show --showformat '${package}\n' 		| grep -P '^libreadline\d+$' 		| xargs apt-mark manual 	&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force 	&& rm -r /root/.gem/
# Fri, 01 Jun 2018 15:04:06 GMT
ENV GEM_HOME=/usr/local/bundle
# Fri, 01 Jun 2018 15:04:06 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Fri, 01 Jun 2018 15:04:06 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/bundle/gems/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 01 Jun 2018 15:04:07 GMT
RUN mkdir -p "$GEM_HOME" && chmod 777 "$GEM_HOME"
# Fri, 01 Jun 2018 15:04:07 GMT
CMD ["irb"]
# Fri, 01 Jun 2018 17:09:55 GMT
RUN groupadd -r redmine && useradd -r -g redmine redmine
# Fri, 01 Jun 2018 17:10:49 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		wget 	&& rm -rf /var/lib/apt/lists/*
# Fri, 01 Jun 2018 17:10:49 GMT
ENV GOSU_VERSION=1.10
# Fri, 01 Jun 2018 17:10:56 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Fri, 01 Jun 2018 17:10:56 GMT
ENV TINI_VERSION=v0.16.1
# Fri, 01 Jun 2018 17:10:59 GMT
RUN set -x 	&& wget -O /usr/local/bin/tini "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/tini.asc "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5 	&& gpg --batch --verify /usr/local/bin/tini.asc /usr/local/bin/tini 	&& rm -r "$GNUPGHOME" /usr/local/bin/tini.asc 	&& chmod +x /usr/local/bin/tini 	&& tini -h
# Thu, 21 Jun 2018 11:00:37 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		imagemagick 		mercurial 		openssh-client 		subversion 	&& rm -rf /var/lib/apt/lists/*
# Thu, 21 Jun 2018 11:00:38 GMT
ENV RAILS_ENV=production
# Thu, 21 Jun 2018 11:00:38 GMT
WORKDIR /usr/src/redmine
# Thu, 21 Jun 2018 11:00:38 GMT
ENV REDMINE_VERSION=3.4.6
# Thu, 21 Jun 2018 11:00:39 GMT
ENV REDMINE_DOWNLOAD_MD5=5f4993446ecf25782f469763c0d32ea1
# Thu, 21 Jun 2018 11:00:43 GMT
RUN wget -O redmine.tar.gz "https://www.redmine.org/releases/redmine-${REDMINE_VERSION}.tar.gz" 	&& echo "$REDMINE_DOWNLOAD_MD5 redmine.tar.gz" | md5sum -c - 	&& tar -xvf redmine.tar.gz --strip-components=1 	&& rm redmine.tar.gz files/delete.me log/delete.me 	&& mkdir -p tmp/pdf public/plugin_assets 	&& chown -R redmine:redmine ./
# Thu, 21 Jun 2018 11:07:27 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		freetds-dev 		gcc 		libmagickcore-dev 		libmagickwand-dev 		libmysqlclient-dev 		libpq-dev 		libsqlite3-dev 		make 		patch 	; 	rm -rf /var/lib/apt/lists/*; 		bundle install --without development test; 	for adapter in mysql2 postgresql sqlserver sqlite3; do 		echo "$RAILS_ENV:" > ./config/database.yml; 		echo "  adapter: $adapter" >> ./config/database.yml; 		bundle install --without development test; 		cp Gemfile.lock "Gemfile.lock.${adapter}"; 	done; 	rm ./config/database.yml; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| grep -v '^/usr/local/' 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false
# Thu, 21 Jun 2018 11:07:28 GMT
VOLUME [/usr/src/redmine/files]
# Thu, 21 Jun 2018 11:07:35 GMT
COPY file:8064eeba1336402e59165b07c73d0734f58aa7e83e3c0a42b6888098f2e2c11d in / 
# Thu, 21 Jun 2018 11:07:36 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Thu, 21 Jun 2018 11:07:36 GMT
EXPOSE 3000/tcp
# Thu, 21 Jun 2018 11:07:36 GMT
CMD ["rails" "server" "-b" "0.0.0.0"]
```

-	Layers:
	-	`sha256:05b419d667f793c8c2edf0ff0aec14fc4d66733cdb89957ac89e8bfbeaddd0fa`  
		Last Modified: Sat, 28 Apr 2018 10:44:20 GMT  
		Size: 54.5 MB (54486782 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3d6891754f33e4c1f328ba0f4530fdb8383be81d86d518c6967565db3d8a7d3f`  
		Last Modified: Fri, 01 Jun 2018 15:49:54 GMT  
		Size: 14.9 MB (14942131 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:089cb9bb407565a3373144a74a72a2345d043f8423185a11fe236787bfc2d617`  
		Last Modified: Fri, 01 Jun 2018 15:49:47 GMT  
		Size: 208.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b853b205add0f75c6d80bbdfcfd40d09d2435262eb1076c603fd5a6ffff58a15`  
		Last Modified: Fri, 01 Jun 2018 15:49:56 GMT  
		Size: 20.3 MB (20303639 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7911295bc17916b28653d7cd6782d5eaede8fbbd7814f157a445829de1488cc8`  
		Last Modified: Fri, 01 Jun 2018 15:49:47 GMT  
		Size: 148.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2f80ba1db311f9d427a674563c28a8673d1b2941bcf25116f71c8446c382a3b4`  
		Last Modified: Fri, 01 Jun 2018 17:31:18 GMT  
		Size: 2.1 KB (2090 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ff801544c3611060c1d01382b678c4ae46af418e380369f5ebe1d34b0f29d77e`  
		Last Modified: Fri, 01 Jun 2018 17:31:27 GMT  
		Size: 13.1 MB (13103088 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a8e57a3fcd9a49a1c8880a39b935633a3041926c55a56be8bd38c07adff2c4fa`  
		Last Modified: Fri, 01 Jun 2018 17:31:16 GMT  
		Size: 480.6 KB (480563 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0351ff4ecba98d1064a87e597d3a72a277f456c7c8c5ca2c5d3232ee7d9ac7a5`  
		Last Modified: Fri, 01 Jun 2018 17:31:14 GMT  
		Size: 8.6 KB (8565 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a6451afdfb1e0e39ceba0ae2d333f8b7517af15e4c692a597d1b54293e304bb1`  
		Last Modified: Thu, 21 Jun 2018 11:15:18 GMT  
		Size: 60.6 MB (60580239 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bf645102966d197165f4e7e583a568f06ddf47daafd8fb4d473042543a2cac26`  
		Last Modified: Thu, 21 Jun 2018 11:14:48 GMT  
		Size: 140.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ce01371909c6db5cdb9d92de323d2973c0dd219f9f8daba9055a9dc8195ec003`  
		Last Modified: Thu, 21 Jun 2018 11:14:50 GMT  
		Size: 2.5 MB (2456909 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:95d4b6248a4676e50ab8bbfe182fb99d5dd0caff607308555d3f8d9147948743`  
		Last Modified: Thu, 21 Jun 2018 11:15:20 GMT  
		Size: 87.5 MB (87546324 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:114fe7ad48c3d506f86cfc90e19d21acbd0d6f6f8686ffd8c241234719076c80`  
		Last Modified: Thu, 21 Jun 2018 11:14:48 GMT  
		Size: 1.8 KB (1793 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `redmine:3.4.6` - linux; ppc64le

```console
$ docker pull redmine@sha256:907c86f110cb9245f282d9daeb30d2fef6fe5073bc1c78cea57bc0f4c745dc1a
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **249.9 MB (249907098 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:b0de66b8b9f108221b0d577f34253c4482d759cf811a688bfc94660b4c03cb28`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["rails","server","-b","0.0.0.0"]`

```dockerfile
# Sat, 28 Apr 2018 08:17:46 GMT
ADD file:6a4bd4ea54f669286e984ecf8178e1fa7c12c8b6fc0f96e4203ae7a6f99a2279 in / 
# Sat, 28 Apr 2018 08:17:47 GMT
CMD ["bash"]
# Sat, 28 Apr 2018 11:24:06 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Sat, 28 Apr 2018 11:24:08 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Sat, 28 Apr 2018 11:24:08 GMT
ENV RUBY_MAJOR=2.4
# Sat, 28 Apr 2018 11:24:08 GMT
ENV RUBY_VERSION=2.4.4
# Sat, 28 Apr 2018 11:24:09 GMT
ENV RUBY_DOWNLOAD_SHA256=1d0034071d675193ca769f64c91827e5f54cb3a7962316a41d5217c7bc6949f0
# Thu, 24 May 2018 10:50:48 GMT
ENV RUBYGEMS_VERSION=2.7.7
# Thu, 24 May 2018 10:50:50 GMT
ENV BUNDLER_VERSION=1.16.2
# Thu, 24 May 2018 10:58:50 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		dpkg-dev 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 		xz-utils 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& dpkg-query --show --showformat '${package}\n' 		| grep -P '^libreadline\d+$' 		| xargs apt-mark manual 	&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force 	&& rm -r /root/.gem/
# Thu, 24 May 2018 10:58:51 GMT
ENV GEM_HOME=/usr/local/bundle
# Fri, 25 May 2018 09:19:08 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Fri, 25 May 2018 09:19:09 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/bundle/gems/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 25 May 2018 09:19:10 GMT
RUN mkdir -p "$GEM_HOME" && chmod 777 "$GEM_HOME"
# Fri, 25 May 2018 09:19:11 GMT
CMD ["irb"]
# Sat, 26 May 2018 09:41:15 GMT
RUN groupadd -r redmine && useradd -r -g redmine redmine
# Sat, 26 May 2018 09:42:45 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		wget 	&& rm -rf /var/lib/apt/lists/*
# Sat, 26 May 2018 09:42:51 GMT
ENV GOSU_VERSION=1.10
# Sat, 26 May 2018 09:43:05 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Sat, 26 May 2018 09:43:11 GMT
ENV TINI_VERSION=v0.16.1
# Sat, 26 May 2018 09:43:19 GMT
RUN set -x 	&& wget -O /usr/local/bin/tini "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/tini.asc "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5 	&& gpg --batch --verify /usr/local/bin/tini.asc /usr/local/bin/tini 	&& rm -r "$GNUPGHOME" /usr/local/bin/tini.asc 	&& chmod +x /usr/local/bin/tini 	&& tini -h
# Thu, 21 Jun 2018 09:57:56 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		imagemagick 		mercurial 		openssh-client 		subversion 	&& rm -rf /var/lib/apt/lists/*
# Thu, 21 Jun 2018 09:57:57 GMT
ENV RAILS_ENV=production
# Thu, 21 Jun 2018 09:57:58 GMT
WORKDIR /usr/src/redmine
# Thu, 21 Jun 2018 09:57:58 GMT
ENV REDMINE_VERSION=3.4.6
# Thu, 21 Jun 2018 09:57:59 GMT
ENV REDMINE_DOWNLOAD_MD5=5f4993446ecf25782f469763c0d32ea1
# Thu, 21 Jun 2018 09:58:05 GMT
RUN wget -O redmine.tar.gz "https://www.redmine.org/releases/redmine-${REDMINE_VERSION}.tar.gz" 	&& echo "$REDMINE_DOWNLOAD_MD5 redmine.tar.gz" | md5sum -c - 	&& tar -xvf redmine.tar.gz --strip-components=1 	&& rm redmine.tar.gz files/delete.me log/delete.me 	&& mkdir -p tmp/pdf public/plugin_assets 	&& chown -R redmine:redmine ./
# Thu, 21 Jun 2018 10:09:09 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		freetds-dev 		gcc 		libmagickcore-dev 		libmagickwand-dev 		libmysqlclient-dev 		libpq-dev 		libsqlite3-dev 		make 		patch 	; 	rm -rf /var/lib/apt/lists/*; 		bundle install --without development test; 	for adapter in mysql2 postgresql sqlserver sqlite3; do 		echo "$RAILS_ENV:" > ./config/database.yml; 		echo "  adapter: $adapter" >> ./config/database.yml; 		bundle install --without development test; 		cp Gemfile.lock "Gemfile.lock.${adapter}"; 	done; 	rm ./config/database.yml; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| grep -v '^/usr/local/' 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false
# Thu, 21 Jun 2018 10:09:12 GMT
VOLUME [/usr/src/redmine/files]
# Thu, 21 Jun 2018 10:09:12 GMT
COPY file:8064eeba1336402e59165b07c73d0734f58aa7e83e3c0a42b6888098f2e2c11d in / 
# Thu, 21 Jun 2018 10:09:14 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Thu, 21 Jun 2018 10:09:15 GMT
EXPOSE 3000/tcp
# Thu, 21 Jun 2018 10:09:19 GMT
CMD ["rails" "server" "-b" "0.0.0.0"]
```

-	Layers:
	-	`sha256:2668401c9f940b1d6b03e5f0086fa248cb957610ef9a7c79983d2fb0707ec76c`  
		Last Modified: Sat, 28 Apr 2018 08:24:36 GMT  
		Size: 53.4 MB (53392811 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ab444779be019b7a69946ce8e93e0062d82eedfe747470714b266730847305b0`  
		Last Modified: Sat, 28 Apr 2018 12:15:08 GMT  
		Size: 10.1 MB (10137971 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b6bfab4f27e54de1711e2752ce393ce141c20aef64a8cd42d95a20585d28fa73`  
		Last Modified: Sat, 28 Apr 2018 12:15:04 GMT  
		Size: 207.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8b15968d0ad41cd76cb81ece13f4d2ca5a0d8d6e4579ae1e619f8ddd2ad295c2`  
		Last Modified: Thu, 24 May 2018 11:43:15 GMT  
		Size: 21.8 MB (21757239 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:351a7ed5b215a7bd4c196ac77237a20aec73a9a6665d2224deead4283218f7d6`  
		Last Modified: Fri, 25 May 2018 09:32:02 GMT  
		Size: 183.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6bd39d3e6422d52b16dfac40b0f9fd915fe70de5266ff6e1c6a545538a617171`  
		Last Modified: Sat, 26 May 2018 10:28:52 GMT  
		Size: 2.1 KB (2122 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b890c32c8a35b49718465b739aa29851ea5d09645363047bcfd2646d0c7e59d2`  
		Last Modified: Sat, 26 May 2018 10:28:53 GMT  
		Size: 13.1 MB (13113602 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4a2678fca66b07491a24dbcff3ff476be318e02d27a9fa400cad6b5f547dd076`  
		Last Modified: Sat, 26 May 2018 10:28:49 GMT  
		Size: 469.8 KB (469848 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c4a046b512a788097cb981ae07112f3acf9a3a7e482327497e84752c042b0e3d`  
		Last Modified: Sat, 26 May 2018 10:28:49 GMT  
		Size: 8.6 KB (8645 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bbb5e064795a21c6fe2b678532828599dfeca38475f384ae401a3452917112a2`  
		Last Modified: Thu, 21 Jun 2018 10:24:26 GMT  
		Size: 58.6 MB (58565791 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8a889f049e1545e24c2d4646d29bf7b0a3e0f72f2d286d8c219dbe346c08efb9`  
		Last Modified: Thu, 21 Jun 2018 10:24:09 GMT  
		Size: 172.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7da14007fe0da424adf4a75292ded9fae229448fbca2f31fd9be25d875290f85`  
		Last Modified: Thu, 21 Jun 2018 10:24:10 GMT  
		Size: 2.5 MB (2457580 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ccc76284d5a2c5b70dc71348dd65954b145b82b10252ae4c34b4960f37e90b86`  
		Last Modified: Thu, 21 Jun 2018 10:24:30 GMT  
		Size: 90.0 MB (89999138 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f957288162825d819debf1f6f7c10ee1f44c5bd0d99f411380a51626910bda76`  
		Last Modified: Thu, 21 Jun 2018 10:24:10 GMT  
		Size: 1.8 KB (1789 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `redmine:3.4.6` - linux; s390x

```console
$ docker pull redmine@sha256:30b50ca230b2b96668f067c3aa64f4ab650c5d0f58b705b9475e8eb036d65f63
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **254.9 MB (254937140 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:924bf921e4b13986dd1234309bc076c1a40bf4134fc02b23ec26aac9448fc0e1`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["rails","server","-b","0.0.0.0"]`

```dockerfile
# Sat, 28 Apr 2018 11:42:31 GMT
ADD file:ac1cfec75c7e1898f2c9b7d17653da3684fdda7d14440ce16f1939bb66105cdc in / 
# Sat, 28 Apr 2018 11:42:31 GMT
CMD ["bash"]
# Sat, 28 Apr 2018 15:34:23 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Sat, 28 Apr 2018 15:34:24 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Sat, 28 Apr 2018 15:34:24 GMT
ENV RUBY_MAJOR=2.4
# Sat, 28 Apr 2018 15:34:24 GMT
ENV RUBY_VERSION=2.4.4
# Sat, 28 Apr 2018 15:34:24 GMT
ENV RUBY_DOWNLOAD_SHA256=1d0034071d675193ca769f64c91827e5f54cb3a7962316a41d5217c7bc6949f0
# Thu, 24 May 2018 13:16:30 GMT
ENV RUBYGEMS_VERSION=2.7.7
# Thu, 24 May 2018 13:16:30 GMT
ENV BUNDLER_VERSION=1.16.2
# Thu, 24 May 2018 13:19:35 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		dpkg-dev 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 		xz-utils 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& dpkg-query --show --showformat '${package}\n' 		| grep -P '^libreadline\d+$' 		| xargs apt-mark manual 	&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force 	&& rm -r /root/.gem/
# Thu, 24 May 2018 13:19:35 GMT
ENV GEM_HOME=/usr/local/bundle
# Fri, 25 May 2018 11:58:16 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Fri, 25 May 2018 11:58:17 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/bundle/gems/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 25 May 2018 11:58:17 GMT
RUN mkdir -p "$GEM_HOME" && chmod 777 "$GEM_HOME"
# Fri, 25 May 2018 11:58:18 GMT
CMD ["irb"]
# Sat, 26 May 2018 13:25:59 GMT
RUN groupadd -r redmine && useradd -r -g redmine redmine
# Sat, 26 May 2018 13:26:09 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		wget 	&& rm -rf /var/lib/apt/lists/*
# Sat, 26 May 2018 13:26:09 GMT
ENV GOSU_VERSION=1.10
# Sat, 26 May 2018 13:26:11 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Sat, 26 May 2018 13:26:12 GMT
ENV TINI_VERSION=v0.16.1
# Sat, 26 May 2018 13:26:14 GMT
RUN set -x 	&& wget -O /usr/local/bin/tini "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/tini.asc "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5 	&& gpg --batch --verify /usr/local/bin/tini.asc /usr/local/bin/tini 	&& rm -r "$GNUPGHOME" /usr/local/bin/tini.asc 	&& chmod +x /usr/local/bin/tini 	&& tini -h
# Thu, 21 Jun 2018 13:40:18 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		imagemagick 		mercurial 		openssh-client 		subversion 	&& rm -rf /var/lib/apt/lists/*
# Thu, 21 Jun 2018 13:40:20 GMT
ENV RAILS_ENV=production
# Thu, 21 Jun 2018 13:40:20 GMT
WORKDIR /usr/src/redmine
# Thu, 21 Jun 2018 13:40:20 GMT
ENV REDMINE_VERSION=3.4.6
# Thu, 21 Jun 2018 13:40:20 GMT
ENV REDMINE_DOWNLOAD_MD5=5f4993446ecf25782f469763c0d32ea1
# Thu, 21 Jun 2018 13:40:23 GMT
RUN wget -O redmine.tar.gz "https://www.redmine.org/releases/redmine-${REDMINE_VERSION}.tar.gz" 	&& echo "$REDMINE_DOWNLOAD_MD5 redmine.tar.gz" | md5sum -c - 	&& tar -xvf redmine.tar.gz --strip-components=1 	&& rm redmine.tar.gz files/delete.me log/delete.me 	&& mkdir -p tmp/pdf public/plugin_assets 	&& chown -R redmine:redmine ./
# Thu, 21 Jun 2018 13:43:55 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		freetds-dev 		gcc 		libmagickcore-dev 		libmagickwand-dev 		libmysqlclient-dev 		libpq-dev 		libsqlite3-dev 		make 		patch 	; 	rm -rf /var/lib/apt/lists/*; 		bundle install --without development test; 	for adapter in mysql2 postgresql sqlserver sqlite3; do 		echo "$RAILS_ENV:" > ./config/database.yml; 		echo "  adapter: $adapter" >> ./config/database.yml; 		bundle install --without development test; 		cp Gemfile.lock "Gemfile.lock.${adapter}"; 	done; 	rm ./config/database.yml; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| grep -v '^/usr/local/' 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false
# Thu, 21 Jun 2018 13:43:56 GMT
VOLUME [/usr/src/redmine/files]
# Thu, 21 Jun 2018 13:43:56 GMT
COPY file:8064eeba1336402e59165b07c73d0734f58aa7e83e3c0a42b6888098f2e2c11d in / 
# Thu, 21 Jun 2018 13:43:57 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Thu, 21 Jun 2018 13:43:57 GMT
EXPOSE 3000/tcp
# Thu, 21 Jun 2018 13:43:57 GMT
CMD ["rails" "server" "-b" "0.0.0.0"]
```

-	Layers:
	-	`sha256:e0524893a6d25f3e36c190fea678ecf1845e7c0d2ba833b077a429d64b943e0a`  
		Last Modified: Sat, 28 Apr 2018 11:47:52 GMT  
		Size: 54.5 MB (54465857 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:61347f1daff97305b17924679d0a40043c3c68c04ecd38580c03a9f5f14cc025`  
		Last Modified: Sat, 28 Apr 2018 16:00:45 GMT  
		Size: 10.0 MB (9963110 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4516576626d0afc4ce307a23343efc17d8fa199788465d6fb1966c6e38405270`  
		Last Modified: Sat, 28 Apr 2018 16:00:42 GMT  
		Size: 205.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5db3c4bbb862bf979405dbf70d32620b3868872a06f125c0636aa2ca5d9a8118`  
		Last Modified: Thu, 24 May 2018 13:48:49 GMT  
		Size: 21.7 MB (21709046 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cc118bcf2202904ad8addf51827feb3eb0be972ee9912cfef0c03d939af4af5d`  
		Last Modified: Fri, 25 May 2018 12:08:37 GMT  
		Size: 148.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0bedd5671d7bb05f77a136f485548dd94b826bcaeca59790f44d37972cac966c`  
		Last Modified: Sat, 26 May 2018 13:34:13 GMT  
		Size: 2.1 KB (2107 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:df0ad57d1afd283e6ea7a12a3fdb17282925a2ac6c8fc1e0b18594b70f4860d8`  
		Last Modified: Sat, 26 May 2018 13:34:15 GMT  
		Size: 13.1 MB (13130009 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:38f941c2e8a178296eb5ef00af421a44bd40170e8b4535faf85b8c0f669e4127`  
		Last Modified: Sat, 26 May 2018 13:34:13 GMT  
		Size: 486.8 KB (486831 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2b65703d4fed12215b832fd6eb431e15ec6df3ea624470903495fa95675645b2`  
		Last Modified: Sat, 26 May 2018 13:34:11 GMT  
		Size: 8.6 KB (8628 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:147ee1fc1b1a421958c0c5f1e52aa1fcd3bb3db7c6b68f6c4c69b8daa4356bdd`  
		Last Modified: Thu, 21 Jun 2018 13:47:39 GMT  
		Size: 59.5 MB (59533196 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:33fc24964afaca53a8f69b089f296f90016a97249c28644192e99669d94ca950`  
		Last Modified: Thu, 21 Jun 2018 13:47:26 GMT  
		Size: 139.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:95937785bb16f99b2d94476fe49fab2418fd81f458a9214d61406057d60561f7`  
		Last Modified: Thu, 21 Jun 2018 13:47:27 GMT  
		Size: 2.5 MB (2456908 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5621a26308c9d8073f8ef0d18bc14689e45b96da0d71fe09658c0311b4578690`  
		Last Modified: Thu, 21 Jun 2018 13:47:43 GMT  
		Size: 93.2 MB (93179163 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1ff10f665c615aa7ed26b1dd97eec9db4674eb2affa120fb7b23dc95d1b52b7c`  
		Last Modified: Thu, 21 Jun 2018 13:47:26 GMT  
		Size: 1.8 KB (1793 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `redmine:3.4.6-passenger`

```console
$ docker pull redmine@sha256:fcb61c193c1ac787a3bcb36a480f369dc115cee985dbef56bd855aa32869c6b9
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `redmine:3.4.6-passenger` - linux; amd64

```console
$ docker pull redmine@sha256:c5345ca71ca7a09d13827489ff2976b31b6448f942990fe801485222f931efb0
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **273.9 MB (273922952 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:906833a174e69cdf240302ed3eb2ab694bb5536f544fed950d48ff6b55daca3d`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["passenger","start"]`

```dockerfile
# Sat, 28 Apr 2018 06:44:15 GMT
ADD file:3e6141c0c9cb74b14a281eb3ab7aaf162a625733e652c3948b323bb2ec8b4343 in / 
# Sat, 28 Apr 2018 06:44:16 GMT
CMD ["bash"]
# Sun, 29 Apr 2018 16:52:40 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Sun, 29 Apr 2018 16:52:41 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Sun, 29 Apr 2018 16:52:42 GMT
ENV RUBY_MAJOR=2.4
# Sun, 29 Apr 2018 16:52:42 GMT
ENV RUBY_VERSION=2.4.4
# Sun, 29 Apr 2018 16:52:42 GMT
ENV RUBY_DOWNLOAD_SHA256=1d0034071d675193ca769f64c91827e5f54cb3a7962316a41d5217c7bc6949f0
# Thu, 24 May 2018 01:25:52 GMT
ENV RUBYGEMS_VERSION=2.7.7
# Thu, 24 May 2018 01:25:52 GMT
ENV BUNDLER_VERSION=1.16.2
# Thu, 24 May 2018 01:29:14 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		dpkg-dev 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 		xz-utils 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& dpkg-query --show --showformat '${package}\n' 		| grep -P '^libreadline\d+$' 		| xargs apt-mark manual 	&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force 	&& rm -r /root/.gem/
# Thu, 24 May 2018 01:29:14 GMT
ENV GEM_HOME=/usr/local/bundle
# Thu, 24 May 2018 21:08:01 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Thu, 24 May 2018 21:08:02 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/bundle/gems/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Thu, 24 May 2018 21:08:02 GMT
RUN mkdir -p "$GEM_HOME" && chmod 777 "$GEM_HOME"
# Thu, 24 May 2018 21:08:03 GMT
CMD ["irb"]
# Fri, 25 May 2018 22:37:54 GMT
RUN groupadd -r redmine && useradd -r -g redmine redmine
# Fri, 25 May 2018 22:38:14 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		wget 	&& rm -rf /var/lib/apt/lists/*
# Fri, 25 May 2018 22:38:14 GMT
ENV GOSU_VERSION=1.10
# Fri, 25 May 2018 22:38:18 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Fri, 25 May 2018 22:38:18 GMT
ENV TINI_VERSION=v0.16.1
# Fri, 25 May 2018 22:38:20 GMT
RUN set -x 	&& wget -O /usr/local/bin/tini "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/tini.asc "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5 	&& gpg --batch --verify /usr/local/bin/tini.asc /usr/local/bin/tini 	&& rm -r "$GNUPGHOME" /usr/local/bin/tini.asc 	&& chmod +x /usr/local/bin/tini 	&& tini -h
# Wed, 20 Jun 2018 21:28:18 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		imagemagick 		mercurial 		openssh-client 		subversion 	&& rm -rf /var/lib/apt/lists/*
# Wed, 20 Jun 2018 21:28:18 GMT
ENV RAILS_ENV=production
# Wed, 20 Jun 2018 21:28:19 GMT
WORKDIR /usr/src/redmine
# Wed, 20 Jun 2018 21:28:19 GMT
ENV REDMINE_VERSION=3.4.6
# Wed, 20 Jun 2018 21:28:19 GMT
ENV REDMINE_DOWNLOAD_MD5=5f4993446ecf25782f469763c0d32ea1
# Wed, 20 Jun 2018 21:28:23 GMT
RUN wget -O redmine.tar.gz "https://www.redmine.org/releases/redmine-${REDMINE_VERSION}.tar.gz" 	&& echo "$REDMINE_DOWNLOAD_MD5 redmine.tar.gz" | md5sum -c - 	&& tar -xvf redmine.tar.gz --strip-components=1 	&& rm redmine.tar.gz files/delete.me log/delete.me 	&& mkdir -p tmp/pdf public/plugin_assets 	&& chown -R redmine:redmine ./
# Wed, 20 Jun 2018 21:31:54 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		freetds-dev 		gcc 		libmagickcore-dev 		libmagickwand-dev 		libmysqlclient-dev 		libpq-dev 		libsqlite3-dev 		make 		patch 	; 	rm -rf /var/lib/apt/lists/*; 		bundle install --without development test; 	for adapter in mysql2 postgresql sqlserver sqlite3; do 		echo "$RAILS_ENV:" > ./config/database.yml; 		echo "  adapter: $adapter" >> ./config/database.yml; 		bundle install --without development test; 		cp Gemfile.lock "Gemfile.lock.${adapter}"; 	done; 	rm ./config/database.yml; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| grep -v '^/usr/local/' 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false
# Wed, 20 Jun 2018 21:31:54 GMT
VOLUME [/usr/src/redmine/files]
# Wed, 20 Jun 2018 21:31:54 GMT
COPY file:8064eeba1336402e59165b07c73d0734f58aa7e83e3c0a42b6888098f2e2c11d in / 
# Wed, 20 Jun 2018 21:31:55 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Wed, 20 Jun 2018 21:31:55 GMT
EXPOSE 3000/tcp
# Wed, 20 Jun 2018 21:31:55 GMT
CMD ["rails" "server" "-b" "0.0.0.0"]
# Wed, 20 Jun 2018 21:38:41 GMT
ENV PASSENGER_VERSION=5.3.2
# Wed, 20 Jun 2018 21:39:09 GMT
RUN buildDeps=' 		make 	' 	&& set -x 	&& apt-get update && apt-get install -y --no-install-recommends $buildDeps && rm -rf /var/lib/apt/lists/* 	&& gem install passenger --version "$PASSENGER_VERSION" 	&& apt-get purge -y --auto-remove $buildDeps
# Wed, 20 Jun 2018 21:39:10 GMT
RUN set -x 	&& passenger-config install-agent 	&& passenger-config download-nginx-engine
# Wed, 20 Jun 2018 21:39:10 GMT
CMD ["passenger" "start"]
```

-	Layers:
	-	`sha256:3d77ce4481b119f00e53bee9b4a443469c42c224db954ddaa2e6b74cd73cd5d0`  
		Last Modified: Sat, 28 Apr 2018 08:24:47 GMT  
		Size: 54.3 MB (54262566 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:05a78650ca91970038096c478f5bc7b8155cf0226db13c86ccf40e0e476e23d5`  
		Last Modified: Sun, 29 Apr 2018 19:33:59 GMT  
		Size: 10.2 MB (10168983 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:860996a55f7fba99ae60e7be5fc25d885d982031d74467b9bcfc84f96e72def6`  
		Last Modified: Sun, 29 Apr 2018 19:33:57 GMT  
		Size: 205.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0af7e9644f308307bcbf19ad9eea243ce5dd469c0211039f47b3120cabdfc99c`  
		Last Modified: Thu, 24 May 2018 02:02:57 GMT  
		Size: 21.3 MB (21305911 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3c2741f1d4c75227c788ea0d4f97b9d842c26908b326b7341255dc08df8c2ff0`  
		Last Modified: Thu, 24 May 2018 21:16:41 GMT  
		Size: 149.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:085bf055e4f7fca4100b86db549ca65dbd113d5633f293b7d60c64580e40fc9c`  
		Last Modified: Fri, 25 May 2018 22:53:00 GMT  
		Size: 2.1 KB (2100 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:02757c5b4f758477ace554b047238004f1ba80dd0253f13e4afde2cff60c8fe2`  
		Last Modified: Fri, 25 May 2018 22:53:02 GMT  
		Size: 13.0 MB (12967769 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0b812d52f0b76913f780e051066b0aec46d9f1a2bc758a19b4872c304bf83525`  
		Last Modified: Fri, 25 May 2018 22:52:57 GMT  
		Size: 500.7 KB (500671 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a1ee2b52aad93348e461129e48f8cb4e4cbc9418e7363ce6ed71b679ed0da25e`  
		Last Modified: Fri, 25 May 2018 22:52:58 GMT  
		Size: 8.5 KB (8506 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:50ec0628480d6092f4ac1c09226941258eaa856ae2b192f54b82351b8147c5a2`  
		Last Modified: Wed, 20 Jun 2018 21:49:29 GMT  
		Size: 59.7 MB (59702353 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d7d52a5fdbb89bea397274ff00985194056ee68db884b686daa2e63575fa3730`  
		Last Modified: Wed, 20 Jun 2018 21:49:09 GMT  
		Size: 140.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:079a05a37d0bc8ec6e3819f8806a9ff391a4c3ff38e3c35679acabccd7281ed1`  
		Last Modified: Wed, 20 Jun 2018 21:49:11 GMT  
		Size: 2.5 MB (2456917 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:828f67b9c47148252d063a4e719ca8ed0be6c8a2487a5ac84f2bade3fd5e83ae`  
		Last Modified: Wed, 20 Jun 2018 21:49:35 GMT  
		Size: 89.3 MB (89291037 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d4660d39964eb0750734643da738a9352ccb35da2e28172ac5340f00f0cd40ea`  
		Last Modified: Wed, 20 Jun 2018 21:49:09 GMT  
		Size: 1.8 KB (1791 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a168cd64a8c99d11fc203758e12bebe2466c268badacf8a6cf6811c7fde7571e`  
		Last Modified: Wed, 20 Jun 2018 21:50:28 GMT  
		Size: 18.8 MB (18769103 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:adbd7bcd3736ab47fc3557c2ed59316963d6f4bab6f367c31609cbd34f1ce46c`  
		Last Modified: Wed, 20 Jun 2018 21:50:24 GMT  
		Size: 4.5 MB (4484751 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `redmine:3.4-passenger`

```console
$ docker pull redmine@sha256:fcb61c193c1ac787a3bcb36a480f369dc115cee985dbef56bd855aa32869c6b9
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `redmine:3.4-passenger` - linux; amd64

```console
$ docker pull redmine@sha256:c5345ca71ca7a09d13827489ff2976b31b6448f942990fe801485222f931efb0
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **273.9 MB (273922952 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:906833a174e69cdf240302ed3eb2ab694bb5536f544fed950d48ff6b55daca3d`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["passenger","start"]`

```dockerfile
# Sat, 28 Apr 2018 06:44:15 GMT
ADD file:3e6141c0c9cb74b14a281eb3ab7aaf162a625733e652c3948b323bb2ec8b4343 in / 
# Sat, 28 Apr 2018 06:44:16 GMT
CMD ["bash"]
# Sun, 29 Apr 2018 16:52:40 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Sun, 29 Apr 2018 16:52:41 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Sun, 29 Apr 2018 16:52:42 GMT
ENV RUBY_MAJOR=2.4
# Sun, 29 Apr 2018 16:52:42 GMT
ENV RUBY_VERSION=2.4.4
# Sun, 29 Apr 2018 16:52:42 GMT
ENV RUBY_DOWNLOAD_SHA256=1d0034071d675193ca769f64c91827e5f54cb3a7962316a41d5217c7bc6949f0
# Thu, 24 May 2018 01:25:52 GMT
ENV RUBYGEMS_VERSION=2.7.7
# Thu, 24 May 2018 01:25:52 GMT
ENV BUNDLER_VERSION=1.16.2
# Thu, 24 May 2018 01:29:14 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		dpkg-dev 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 		xz-utils 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& dpkg-query --show --showformat '${package}\n' 		| grep -P '^libreadline\d+$' 		| xargs apt-mark manual 	&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force 	&& rm -r /root/.gem/
# Thu, 24 May 2018 01:29:14 GMT
ENV GEM_HOME=/usr/local/bundle
# Thu, 24 May 2018 21:08:01 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Thu, 24 May 2018 21:08:02 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/bundle/gems/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Thu, 24 May 2018 21:08:02 GMT
RUN mkdir -p "$GEM_HOME" && chmod 777 "$GEM_HOME"
# Thu, 24 May 2018 21:08:03 GMT
CMD ["irb"]
# Fri, 25 May 2018 22:37:54 GMT
RUN groupadd -r redmine && useradd -r -g redmine redmine
# Fri, 25 May 2018 22:38:14 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		wget 	&& rm -rf /var/lib/apt/lists/*
# Fri, 25 May 2018 22:38:14 GMT
ENV GOSU_VERSION=1.10
# Fri, 25 May 2018 22:38:18 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Fri, 25 May 2018 22:38:18 GMT
ENV TINI_VERSION=v0.16.1
# Fri, 25 May 2018 22:38:20 GMT
RUN set -x 	&& wget -O /usr/local/bin/tini "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/tini.asc "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5 	&& gpg --batch --verify /usr/local/bin/tini.asc /usr/local/bin/tini 	&& rm -r "$GNUPGHOME" /usr/local/bin/tini.asc 	&& chmod +x /usr/local/bin/tini 	&& tini -h
# Wed, 20 Jun 2018 21:28:18 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		imagemagick 		mercurial 		openssh-client 		subversion 	&& rm -rf /var/lib/apt/lists/*
# Wed, 20 Jun 2018 21:28:18 GMT
ENV RAILS_ENV=production
# Wed, 20 Jun 2018 21:28:19 GMT
WORKDIR /usr/src/redmine
# Wed, 20 Jun 2018 21:28:19 GMT
ENV REDMINE_VERSION=3.4.6
# Wed, 20 Jun 2018 21:28:19 GMT
ENV REDMINE_DOWNLOAD_MD5=5f4993446ecf25782f469763c0d32ea1
# Wed, 20 Jun 2018 21:28:23 GMT
RUN wget -O redmine.tar.gz "https://www.redmine.org/releases/redmine-${REDMINE_VERSION}.tar.gz" 	&& echo "$REDMINE_DOWNLOAD_MD5 redmine.tar.gz" | md5sum -c - 	&& tar -xvf redmine.tar.gz --strip-components=1 	&& rm redmine.tar.gz files/delete.me log/delete.me 	&& mkdir -p tmp/pdf public/plugin_assets 	&& chown -R redmine:redmine ./
# Wed, 20 Jun 2018 21:31:54 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		freetds-dev 		gcc 		libmagickcore-dev 		libmagickwand-dev 		libmysqlclient-dev 		libpq-dev 		libsqlite3-dev 		make 		patch 	; 	rm -rf /var/lib/apt/lists/*; 		bundle install --without development test; 	for adapter in mysql2 postgresql sqlserver sqlite3; do 		echo "$RAILS_ENV:" > ./config/database.yml; 		echo "  adapter: $adapter" >> ./config/database.yml; 		bundle install --without development test; 		cp Gemfile.lock "Gemfile.lock.${adapter}"; 	done; 	rm ./config/database.yml; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| grep -v '^/usr/local/' 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false
# Wed, 20 Jun 2018 21:31:54 GMT
VOLUME [/usr/src/redmine/files]
# Wed, 20 Jun 2018 21:31:54 GMT
COPY file:8064eeba1336402e59165b07c73d0734f58aa7e83e3c0a42b6888098f2e2c11d in / 
# Wed, 20 Jun 2018 21:31:55 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Wed, 20 Jun 2018 21:31:55 GMT
EXPOSE 3000/tcp
# Wed, 20 Jun 2018 21:31:55 GMT
CMD ["rails" "server" "-b" "0.0.0.0"]
# Wed, 20 Jun 2018 21:38:41 GMT
ENV PASSENGER_VERSION=5.3.2
# Wed, 20 Jun 2018 21:39:09 GMT
RUN buildDeps=' 		make 	' 	&& set -x 	&& apt-get update && apt-get install -y --no-install-recommends $buildDeps && rm -rf /var/lib/apt/lists/* 	&& gem install passenger --version "$PASSENGER_VERSION" 	&& apt-get purge -y --auto-remove $buildDeps
# Wed, 20 Jun 2018 21:39:10 GMT
RUN set -x 	&& passenger-config install-agent 	&& passenger-config download-nginx-engine
# Wed, 20 Jun 2018 21:39:10 GMT
CMD ["passenger" "start"]
```

-	Layers:
	-	`sha256:3d77ce4481b119f00e53bee9b4a443469c42c224db954ddaa2e6b74cd73cd5d0`  
		Last Modified: Sat, 28 Apr 2018 08:24:47 GMT  
		Size: 54.3 MB (54262566 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:05a78650ca91970038096c478f5bc7b8155cf0226db13c86ccf40e0e476e23d5`  
		Last Modified: Sun, 29 Apr 2018 19:33:59 GMT  
		Size: 10.2 MB (10168983 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:860996a55f7fba99ae60e7be5fc25d885d982031d74467b9bcfc84f96e72def6`  
		Last Modified: Sun, 29 Apr 2018 19:33:57 GMT  
		Size: 205.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0af7e9644f308307bcbf19ad9eea243ce5dd469c0211039f47b3120cabdfc99c`  
		Last Modified: Thu, 24 May 2018 02:02:57 GMT  
		Size: 21.3 MB (21305911 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3c2741f1d4c75227c788ea0d4f97b9d842c26908b326b7341255dc08df8c2ff0`  
		Last Modified: Thu, 24 May 2018 21:16:41 GMT  
		Size: 149.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:085bf055e4f7fca4100b86db549ca65dbd113d5633f293b7d60c64580e40fc9c`  
		Last Modified: Fri, 25 May 2018 22:53:00 GMT  
		Size: 2.1 KB (2100 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:02757c5b4f758477ace554b047238004f1ba80dd0253f13e4afde2cff60c8fe2`  
		Last Modified: Fri, 25 May 2018 22:53:02 GMT  
		Size: 13.0 MB (12967769 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0b812d52f0b76913f780e051066b0aec46d9f1a2bc758a19b4872c304bf83525`  
		Last Modified: Fri, 25 May 2018 22:52:57 GMT  
		Size: 500.7 KB (500671 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a1ee2b52aad93348e461129e48f8cb4e4cbc9418e7363ce6ed71b679ed0da25e`  
		Last Modified: Fri, 25 May 2018 22:52:58 GMT  
		Size: 8.5 KB (8506 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:50ec0628480d6092f4ac1c09226941258eaa856ae2b192f54b82351b8147c5a2`  
		Last Modified: Wed, 20 Jun 2018 21:49:29 GMT  
		Size: 59.7 MB (59702353 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d7d52a5fdbb89bea397274ff00985194056ee68db884b686daa2e63575fa3730`  
		Last Modified: Wed, 20 Jun 2018 21:49:09 GMT  
		Size: 140.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:079a05a37d0bc8ec6e3819f8806a9ff391a4c3ff38e3c35679acabccd7281ed1`  
		Last Modified: Wed, 20 Jun 2018 21:49:11 GMT  
		Size: 2.5 MB (2456917 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:828f67b9c47148252d063a4e719ca8ed0be6c8a2487a5ac84f2bade3fd5e83ae`  
		Last Modified: Wed, 20 Jun 2018 21:49:35 GMT  
		Size: 89.3 MB (89291037 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d4660d39964eb0750734643da738a9352ccb35da2e28172ac5340f00f0cd40ea`  
		Last Modified: Wed, 20 Jun 2018 21:49:09 GMT  
		Size: 1.8 KB (1791 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a168cd64a8c99d11fc203758e12bebe2466c268badacf8a6cf6811c7fde7571e`  
		Last Modified: Wed, 20 Jun 2018 21:50:28 GMT  
		Size: 18.8 MB (18769103 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:adbd7bcd3736ab47fc3557c2ed59316963d6f4bab6f367c31609cbd34f1ce46c`  
		Last Modified: Wed, 20 Jun 2018 21:50:24 GMT  
		Size: 4.5 MB (4484751 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `redmine:3-passenger`

```console
$ docker pull redmine@sha256:fcb61c193c1ac787a3bcb36a480f369dc115cee985dbef56bd855aa32869c6b9
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `redmine:3-passenger` - linux; amd64

```console
$ docker pull redmine@sha256:c5345ca71ca7a09d13827489ff2976b31b6448f942990fe801485222f931efb0
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **273.9 MB (273922952 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:906833a174e69cdf240302ed3eb2ab694bb5536f544fed950d48ff6b55daca3d`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["passenger","start"]`

```dockerfile
# Sat, 28 Apr 2018 06:44:15 GMT
ADD file:3e6141c0c9cb74b14a281eb3ab7aaf162a625733e652c3948b323bb2ec8b4343 in / 
# Sat, 28 Apr 2018 06:44:16 GMT
CMD ["bash"]
# Sun, 29 Apr 2018 16:52:40 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Sun, 29 Apr 2018 16:52:41 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Sun, 29 Apr 2018 16:52:42 GMT
ENV RUBY_MAJOR=2.4
# Sun, 29 Apr 2018 16:52:42 GMT
ENV RUBY_VERSION=2.4.4
# Sun, 29 Apr 2018 16:52:42 GMT
ENV RUBY_DOWNLOAD_SHA256=1d0034071d675193ca769f64c91827e5f54cb3a7962316a41d5217c7bc6949f0
# Thu, 24 May 2018 01:25:52 GMT
ENV RUBYGEMS_VERSION=2.7.7
# Thu, 24 May 2018 01:25:52 GMT
ENV BUNDLER_VERSION=1.16.2
# Thu, 24 May 2018 01:29:14 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		dpkg-dev 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 		xz-utils 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& dpkg-query --show --showformat '${package}\n' 		| grep -P '^libreadline\d+$' 		| xargs apt-mark manual 	&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force 	&& rm -r /root/.gem/
# Thu, 24 May 2018 01:29:14 GMT
ENV GEM_HOME=/usr/local/bundle
# Thu, 24 May 2018 21:08:01 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Thu, 24 May 2018 21:08:02 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/bundle/gems/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Thu, 24 May 2018 21:08:02 GMT
RUN mkdir -p "$GEM_HOME" && chmod 777 "$GEM_HOME"
# Thu, 24 May 2018 21:08:03 GMT
CMD ["irb"]
# Fri, 25 May 2018 22:37:54 GMT
RUN groupadd -r redmine && useradd -r -g redmine redmine
# Fri, 25 May 2018 22:38:14 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		wget 	&& rm -rf /var/lib/apt/lists/*
# Fri, 25 May 2018 22:38:14 GMT
ENV GOSU_VERSION=1.10
# Fri, 25 May 2018 22:38:18 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Fri, 25 May 2018 22:38:18 GMT
ENV TINI_VERSION=v0.16.1
# Fri, 25 May 2018 22:38:20 GMT
RUN set -x 	&& wget -O /usr/local/bin/tini "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/tini.asc "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5 	&& gpg --batch --verify /usr/local/bin/tini.asc /usr/local/bin/tini 	&& rm -r "$GNUPGHOME" /usr/local/bin/tini.asc 	&& chmod +x /usr/local/bin/tini 	&& tini -h
# Wed, 20 Jun 2018 21:28:18 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		imagemagick 		mercurial 		openssh-client 		subversion 	&& rm -rf /var/lib/apt/lists/*
# Wed, 20 Jun 2018 21:28:18 GMT
ENV RAILS_ENV=production
# Wed, 20 Jun 2018 21:28:19 GMT
WORKDIR /usr/src/redmine
# Wed, 20 Jun 2018 21:28:19 GMT
ENV REDMINE_VERSION=3.4.6
# Wed, 20 Jun 2018 21:28:19 GMT
ENV REDMINE_DOWNLOAD_MD5=5f4993446ecf25782f469763c0d32ea1
# Wed, 20 Jun 2018 21:28:23 GMT
RUN wget -O redmine.tar.gz "https://www.redmine.org/releases/redmine-${REDMINE_VERSION}.tar.gz" 	&& echo "$REDMINE_DOWNLOAD_MD5 redmine.tar.gz" | md5sum -c - 	&& tar -xvf redmine.tar.gz --strip-components=1 	&& rm redmine.tar.gz files/delete.me log/delete.me 	&& mkdir -p tmp/pdf public/plugin_assets 	&& chown -R redmine:redmine ./
# Wed, 20 Jun 2018 21:31:54 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		freetds-dev 		gcc 		libmagickcore-dev 		libmagickwand-dev 		libmysqlclient-dev 		libpq-dev 		libsqlite3-dev 		make 		patch 	; 	rm -rf /var/lib/apt/lists/*; 		bundle install --without development test; 	for adapter in mysql2 postgresql sqlserver sqlite3; do 		echo "$RAILS_ENV:" > ./config/database.yml; 		echo "  adapter: $adapter" >> ./config/database.yml; 		bundle install --without development test; 		cp Gemfile.lock "Gemfile.lock.${adapter}"; 	done; 	rm ./config/database.yml; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| grep -v '^/usr/local/' 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false
# Wed, 20 Jun 2018 21:31:54 GMT
VOLUME [/usr/src/redmine/files]
# Wed, 20 Jun 2018 21:31:54 GMT
COPY file:8064eeba1336402e59165b07c73d0734f58aa7e83e3c0a42b6888098f2e2c11d in / 
# Wed, 20 Jun 2018 21:31:55 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Wed, 20 Jun 2018 21:31:55 GMT
EXPOSE 3000/tcp
# Wed, 20 Jun 2018 21:31:55 GMT
CMD ["rails" "server" "-b" "0.0.0.0"]
# Wed, 20 Jun 2018 21:38:41 GMT
ENV PASSENGER_VERSION=5.3.2
# Wed, 20 Jun 2018 21:39:09 GMT
RUN buildDeps=' 		make 	' 	&& set -x 	&& apt-get update && apt-get install -y --no-install-recommends $buildDeps && rm -rf /var/lib/apt/lists/* 	&& gem install passenger --version "$PASSENGER_VERSION" 	&& apt-get purge -y --auto-remove $buildDeps
# Wed, 20 Jun 2018 21:39:10 GMT
RUN set -x 	&& passenger-config install-agent 	&& passenger-config download-nginx-engine
# Wed, 20 Jun 2018 21:39:10 GMT
CMD ["passenger" "start"]
```

-	Layers:
	-	`sha256:3d77ce4481b119f00e53bee9b4a443469c42c224db954ddaa2e6b74cd73cd5d0`  
		Last Modified: Sat, 28 Apr 2018 08:24:47 GMT  
		Size: 54.3 MB (54262566 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:05a78650ca91970038096c478f5bc7b8155cf0226db13c86ccf40e0e476e23d5`  
		Last Modified: Sun, 29 Apr 2018 19:33:59 GMT  
		Size: 10.2 MB (10168983 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:860996a55f7fba99ae60e7be5fc25d885d982031d74467b9bcfc84f96e72def6`  
		Last Modified: Sun, 29 Apr 2018 19:33:57 GMT  
		Size: 205.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0af7e9644f308307bcbf19ad9eea243ce5dd469c0211039f47b3120cabdfc99c`  
		Last Modified: Thu, 24 May 2018 02:02:57 GMT  
		Size: 21.3 MB (21305911 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3c2741f1d4c75227c788ea0d4f97b9d842c26908b326b7341255dc08df8c2ff0`  
		Last Modified: Thu, 24 May 2018 21:16:41 GMT  
		Size: 149.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:085bf055e4f7fca4100b86db549ca65dbd113d5633f293b7d60c64580e40fc9c`  
		Last Modified: Fri, 25 May 2018 22:53:00 GMT  
		Size: 2.1 KB (2100 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:02757c5b4f758477ace554b047238004f1ba80dd0253f13e4afde2cff60c8fe2`  
		Last Modified: Fri, 25 May 2018 22:53:02 GMT  
		Size: 13.0 MB (12967769 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0b812d52f0b76913f780e051066b0aec46d9f1a2bc758a19b4872c304bf83525`  
		Last Modified: Fri, 25 May 2018 22:52:57 GMT  
		Size: 500.7 KB (500671 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a1ee2b52aad93348e461129e48f8cb4e4cbc9418e7363ce6ed71b679ed0da25e`  
		Last Modified: Fri, 25 May 2018 22:52:58 GMT  
		Size: 8.5 KB (8506 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:50ec0628480d6092f4ac1c09226941258eaa856ae2b192f54b82351b8147c5a2`  
		Last Modified: Wed, 20 Jun 2018 21:49:29 GMT  
		Size: 59.7 MB (59702353 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d7d52a5fdbb89bea397274ff00985194056ee68db884b686daa2e63575fa3730`  
		Last Modified: Wed, 20 Jun 2018 21:49:09 GMT  
		Size: 140.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:079a05a37d0bc8ec6e3819f8806a9ff391a4c3ff38e3c35679acabccd7281ed1`  
		Last Modified: Wed, 20 Jun 2018 21:49:11 GMT  
		Size: 2.5 MB (2456917 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:828f67b9c47148252d063a4e719ca8ed0be6c8a2487a5ac84f2bade3fd5e83ae`  
		Last Modified: Wed, 20 Jun 2018 21:49:35 GMT  
		Size: 89.3 MB (89291037 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d4660d39964eb0750734643da738a9352ccb35da2e28172ac5340f00f0cd40ea`  
		Last Modified: Wed, 20 Jun 2018 21:49:09 GMT  
		Size: 1.8 KB (1791 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a168cd64a8c99d11fc203758e12bebe2466c268badacf8a6cf6811c7fde7571e`  
		Last Modified: Wed, 20 Jun 2018 21:50:28 GMT  
		Size: 18.8 MB (18769103 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:adbd7bcd3736ab47fc3557c2ed59316963d6f4bab6f367c31609cbd34f1ce46c`  
		Last Modified: Wed, 20 Jun 2018 21:50:24 GMT  
		Size: 4.5 MB (4484751 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `redmine:latest`

```console
$ docker pull redmine@sha256:7439dde0eae47d823c35e7f2e4c47d7cbb8b55dbf29844a2579fbd982421d3d3
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm variant v5
	-	linux; arm variant v7
	-	linux; arm64 variant v8
	-	linux; 386
	-	linux; ppc64le
	-	linux; s390x

### `redmine:latest` - linux; amd64

```console
$ docker pull redmine@sha256:8dce5627271a3f21cd6ce5a3a29c6fbc11fcc99a0ca69d6e6e5882d8ecf4f196
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **250.7 MB (250669098 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:ebd79f5f9bc1c650b0f487dec3b167164c2c36f649ba15d25dbde5ddaae76fe0`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["rails","server","-b","0.0.0.0"]`

```dockerfile
# Sat, 28 Apr 2018 06:44:15 GMT
ADD file:3e6141c0c9cb74b14a281eb3ab7aaf162a625733e652c3948b323bb2ec8b4343 in / 
# Sat, 28 Apr 2018 06:44:16 GMT
CMD ["bash"]
# Sun, 29 Apr 2018 16:52:40 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Sun, 29 Apr 2018 16:52:41 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Sun, 29 Apr 2018 16:52:42 GMT
ENV RUBY_MAJOR=2.4
# Sun, 29 Apr 2018 16:52:42 GMT
ENV RUBY_VERSION=2.4.4
# Sun, 29 Apr 2018 16:52:42 GMT
ENV RUBY_DOWNLOAD_SHA256=1d0034071d675193ca769f64c91827e5f54cb3a7962316a41d5217c7bc6949f0
# Thu, 24 May 2018 01:25:52 GMT
ENV RUBYGEMS_VERSION=2.7.7
# Thu, 24 May 2018 01:25:52 GMT
ENV BUNDLER_VERSION=1.16.2
# Thu, 24 May 2018 01:29:14 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		dpkg-dev 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 		xz-utils 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& dpkg-query --show --showformat '${package}\n' 		| grep -P '^libreadline\d+$' 		| xargs apt-mark manual 	&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force 	&& rm -r /root/.gem/
# Thu, 24 May 2018 01:29:14 GMT
ENV GEM_HOME=/usr/local/bundle
# Thu, 24 May 2018 21:08:01 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Thu, 24 May 2018 21:08:02 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/bundle/gems/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Thu, 24 May 2018 21:08:02 GMT
RUN mkdir -p "$GEM_HOME" && chmod 777 "$GEM_HOME"
# Thu, 24 May 2018 21:08:03 GMT
CMD ["irb"]
# Fri, 25 May 2018 22:37:54 GMT
RUN groupadd -r redmine && useradd -r -g redmine redmine
# Fri, 25 May 2018 22:38:14 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		wget 	&& rm -rf /var/lib/apt/lists/*
# Fri, 25 May 2018 22:38:14 GMT
ENV GOSU_VERSION=1.10
# Fri, 25 May 2018 22:38:18 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Fri, 25 May 2018 22:38:18 GMT
ENV TINI_VERSION=v0.16.1
# Fri, 25 May 2018 22:38:20 GMT
RUN set -x 	&& wget -O /usr/local/bin/tini "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/tini.asc "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5 	&& gpg --batch --verify /usr/local/bin/tini.asc /usr/local/bin/tini 	&& rm -r "$GNUPGHOME" /usr/local/bin/tini.asc 	&& chmod +x /usr/local/bin/tini 	&& tini -h
# Wed, 20 Jun 2018 21:28:18 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		imagemagick 		mercurial 		openssh-client 		subversion 	&& rm -rf /var/lib/apt/lists/*
# Wed, 20 Jun 2018 21:28:18 GMT
ENV RAILS_ENV=production
# Wed, 20 Jun 2018 21:28:19 GMT
WORKDIR /usr/src/redmine
# Wed, 20 Jun 2018 21:28:19 GMT
ENV REDMINE_VERSION=3.4.6
# Wed, 20 Jun 2018 21:28:19 GMT
ENV REDMINE_DOWNLOAD_MD5=5f4993446ecf25782f469763c0d32ea1
# Wed, 20 Jun 2018 21:28:23 GMT
RUN wget -O redmine.tar.gz "https://www.redmine.org/releases/redmine-${REDMINE_VERSION}.tar.gz" 	&& echo "$REDMINE_DOWNLOAD_MD5 redmine.tar.gz" | md5sum -c - 	&& tar -xvf redmine.tar.gz --strip-components=1 	&& rm redmine.tar.gz files/delete.me log/delete.me 	&& mkdir -p tmp/pdf public/plugin_assets 	&& chown -R redmine:redmine ./
# Wed, 20 Jun 2018 21:31:54 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		freetds-dev 		gcc 		libmagickcore-dev 		libmagickwand-dev 		libmysqlclient-dev 		libpq-dev 		libsqlite3-dev 		make 		patch 	; 	rm -rf /var/lib/apt/lists/*; 		bundle install --without development test; 	for adapter in mysql2 postgresql sqlserver sqlite3; do 		echo "$RAILS_ENV:" > ./config/database.yml; 		echo "  adapter: $adapter" >> ./config/database.yml; 		bundle install --without development test; 		cp Gemfile.lock "Gemfile.lock.${adapter}"; 	done; 	rm ./config/database.yml; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| grep -v '^/usr/local/' 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false
# Wed, 20 Jun 2018 21:31:54 GMT
VOLUME [/usr/src/redmine/files]
# Wed, 20 Jun 2018 21:31:54 GMT
COPY file:8064eeba1336402e59165b07c73d0734f58aa7e83e3c0a42b6888098f2e2c11d in / 
# Wed, 20 Jun 2018 21:31:55 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Wed, 20 Jun 2018 21:31:55 GMT
EXPOSE 3000/tcp
# Wed, 20 Jun 2018 21:31:55 GMT
CMD ["rails" "server" "-b" "0.0.0.0"]
```

-	Layers:
	-	`sha256:3d77ce4481b119f00e53bee9b4a443469c42c224db954ddaa2e6b74cd73cd5d0`  
		Last Modified: Sat, 28 Apr 2018 08:24:47 GMT  
		Size: 54.3 MB (54262566 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:05a78650ca91970038096c478f5bc7b8155cf0226db13c86ccf40e0e476e23d5`  
		Last Modified: Sun, 29 Apr 2018 19:33:59 GMT  
		Size: 10.2 MB (10168983 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:860996a55f7fba99ae60e7be5fc25d885d982031d74467b9bcfc84f96e72def6`  
		Last Modified: Sun, 29 Apr 2018 19:33:57 GMT  
		Size: 205.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0af7e9644f308307bcbf19ad9eea243ce5dd469c0211039f47b3120cabdfc99c`  
		Last Modified: Thu, 24 May 2018 02:02:57 GMT  
		Size: 21.3 MB (21305911 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3c2741f1d4c75227c788ea0d4f97b9d842c26908b326b7341255dc08df8c2ff0`  
		Last Modified: Thu, 24 May 2018 21:16:41 GMT  
		Size: 149.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:085bf055e4f7fca4100b86db549ca65dbd113d5633f293b7d60c64580e40fc9c`  
		Last Modified: Fri, 25 May 2018 22:53:00 GMT  
		Size: 2.1 KB (2100 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:02757c5b4f758477ace554b047238004f1ba80dd0253f13e4afde2cff60c8fe2`  
		Last Modified: Fri, 25 May 2018 22:53:02 GMT  
		Size: 13.0 MB (12967769 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0b812d52f0b76913f780e051066b0aec46d9f1a2bc758a19b4872c304bf83525`  
		Last Modified: Fri, 25 May 2018 22:52:57 GMT  
		Size: 500.7 KB (500671 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a1ee2b52aad93348e461129e48f8cb4e4cbc9418e7363ce6ed71b679ed0da25e`  
		Last Modified: Fri, 25 May 2018 22:52:58 GMT  
		Size: 8.5 KB (8506 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:50ec0628480d6092f4ac1c09226941258eaa856ae2b192f54b82351b8147c5a2`  
		Last Modified: Wed, 20 Jun 2018 21:49:29 GMT  
		Size: 59.7 MB (59702353 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d7d52a5fdbb89bea397274ff00985194056ee68db884b686daa2e63575fa3730`  
		Last Modified: Wed, 20 Jun 2018 21:49:09 GMT  
		Size: 140.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:079a05a37d0bc8ec6e3819f8806a9ff391a4c3ff38e3c35679acabccd7281ed1`  
		Last Modified: Wed, 20 Jun 2018 21:49:11 GMT  
		Size: 2.5 MB (2456917 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:828f67b9c47148252d063a4e719ca8ed0be6c8a2487a5ac84f2bade3fd5e83ae`  
		Last Modified: Wed, 20 Jun 2018 21:49:35 GMT  
		Size: 89.3 MB (89291037 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d4660d39964eb0750734643da738a9352ccb35da2e28172ac5340f00f0cd40ea`  
		Last Modified: Wed, 20 Jun 2018 21:49:09 GMT  
		Size: 1.8 KB (1791 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `redmine:latest` - linux; arm variant v5

```console
$ docker pull redmine@sha256:6d3319e8e0caf66469e15cba6f9b18da2b9994eaae19de97012d1aa9bf8c0402
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **244.2 MB (244218136 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:6b0e3d8938719b59edef5744897ff446a575e4be6543a6de3b33e801b768a7fc`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["rails","server","-b","0.0.0.0"]`

```dockerfile
# Sat, 28 Apr 2018 08:49:23 GMT
ADD file:2d2cd360e66aeff5557c7e7117985a00d109278c3f456ee970afcc9a46483264 in / 
# Sat, 28 Apr 2018 08:49:23 GMT
CMD ["bash"]
# Sat, 28 Apr 2018 11:50:09 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Sat, 28 Apr 2018 11:50:10 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Sat, 28 Apr 2018 11:50:11 GMT
ENV RUBY_MAJOR=2.4
# Sat, 28 Apr 2018 11:50:11 GMT
ENV RUBY_VERSION=2.4.4
# Sat, 28 Apr 2018 11:50:11 GMT
ENV RUBY_DOWNLOAD_SHA256=1d0034071d675193ca769f64c91827e5f54cb3a7962316a41d5217c7bc6949f0
# Thu, 24 May 2018 10:56:19 GMT
ENV RUBYGEMS_VERSION=2.7.7
# Thu, 24 May 2018 10:56:19 GMT
ENV BUNDLER_VERSION=1.16.2
# Thu, 24 May 2018 11:02:19 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		dpkg-dev 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 		xz-utils 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& dpkg-query --show --showformat '${package}\n' 		| grep -P '^libreadline\d+$' 		| xargs apt-mark manual 	&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force 	&& rm -r /root/.gem/
# Thu, 24 May 2018 11:02:20 GMT
ENV GEM_HOME=/usr/local/bundle
# Fri, 25 May 2018 09:09:45 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Fri, 25 May 2018 09:09:45 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/bundle/gems/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 25 May 2018 09:09:46 GMT
RUN mkdir -p "$GEM_HOME" && chmod 777 "$GEM_HOME"
# Fri, 25 May 2018 09:09:47 GMT
CMD ["irb"]
# Sat, 26 May 2018 10:03:35 GMT
RUN groupadd -r redmine && useradd -r -g redmine redmine
# Sat, 26 May 2018 10:04:04 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		wget 	&& rm -rf /var/lib/apt/lists/*
# Sat, 26 May 2018 10:04:04 GMT
ENV GOSU_VERSION=1.10
# Sat, 26 May 2018 10:04:06 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Sat, 26 May 2018 10:04:06 GMT
ENV TINI_VERSION=v0.16.1
# Sat, 26 May 2018 10:04:08 GMT
RUN set -x 	&& wget -O /usr/local/bin/tini "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/tini.asc "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5 	&& gpg --batch --verify /usr/local/bin/tini.asc /usr/local/bin/tini 	&& rm -r "$GNUPGHOME" /usr/local/bin/tini.asc 	&& chmod +x /usr/local/bin/tini 	&& tini -h
# Thu, 21 Jun 2018 09:33:55 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		imagemagick 		mercurial 		openssh-client 		subversion 	&& rm -rf /var/lib/apt/lists/*
# Thu, 21 Jun 2018 09:33:55 GMT
ENV RAILS_ENV=production
# Thu, 21 Jun 2018 09:33:56 GMT
WORKDIR /usr/src/redmine
# Thu, 21 Jun 2018 09:33:56 GMT
ENV REDMINE_VERSION=3.4.6
# Thu, 21 Jun 2018 09:33:56 GMT
ENV REDMINE_DOWNLOAD_MD5=5f4993446ecf25782f469763c0d32ea1
# Thu, 21 Jun 2018 09:34:00 GMT
RUN wget -O redmine.tar.gz "https://www.redmine.org/releases/redmine-${REDMINE_VERSION}.tar.gz" 	&& echo "$REDMINE_DOWNLOAD_MD5 redmine.tar.gz" | md5sum -c - 	&& tar -xvf redmine.tar.gz --strip-components=1 	&& rm redmine.tar.gz files/delete.me log/delete.me 	&& mkdir -p tmp/pdf public/plugin_assets 	&& chown -R redmine:redmine ./
# Thu, 21 Jun 2018 09:40:16 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		freetds-dev 		gcc 		libmagickcore-dev 		libmagickwand-dev 		libmysqlclient-dev 		libpq-dev 		libsqlite3-dev 		make 		patch 	; 	rm -rf /var/lib/apt/lists/*; 		bundle install --without development test; 	for adapter in mysql2 postgresql sqlserver sqlite3; do 		echo "$RAILS_ENV:" > ./config/database.yml; 		echo "  adapter: $adapter" >> ./config/database.yml; 		bundle install --without development test; 		cp Gemfile.lock "Gemfile.lock.${adapter}"; 	done; 	rm ./config/database.yml; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| grep -v '^/usr/local/' 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false
# Thu, 21 Jun 2018 09:40:17 GMT
VOLUME [/usr/src/redmine/files]
# Thu, 21 Jun 2018 09:40:17 GMT
COPY file:8064eeba1336402e59165b07c73d0734f58aa7e83e3c0a42b6888098f2e2c11d in / 
# Thu, 21 Jun 2018 09:40:17 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Thu, 21 Jun 2018 09:40:17 GMT
EXPOSE 3000/tcp
# Thu, 21 Jun 2018 09:40:18 GMT
CMD ["rails" "server" "-b" "0.0.0.0"]
```

-	Layers:
	-	`sha256:81fc0826192f72abe617753d378af4047dbce89faf17cdab9166877006a25d8e`  
		Last Modified: Sat, 28 Apr 2018 08:57:10 GMT  
		Size: 52.5 MB (52456037 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2119f18fa6f270436c891e0c459923ae24657bf4a8be20cfcfe964e7aa64b7b2`  
		Last Modified: Sat, 28 Apr 2018 12:31:30 GMT  
		Size: 9.1 MB (9119888 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:51757db9404a98c26c96cb6b65e8c7893c1e1b5ea9774a5786abe9ec88468cf3`  
		Last Modified: Sat, 28 Apr 2018 12:31:26 GMT  
		Size: 206.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:09fe38be652b02d310bce0a19598fe366080a17713f114eeb33355e15f6bf8c0`  
		Last Modified: Thu, 24 May 2018 11:29:31 GMT  
		Size: 21.1 MB (21074760 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:63fc7f9b6584b1727a86e7d2130c3f4129978990791d89d6af0f9950997cc782`  
		Last Modified: Fri, 25 May 2018 09:17:51 GMT  
		Size: 182.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bdbf4bf93be2e977124205e4f60ae3ba2a2f880c269a494237a056a419343587`  
		Last Modified: Sat, 26 May 2018 10:18:09 GMT  
		Size: 2.1 KB (2090 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:98b6a7f079c3c2475a4ae64a2f970ab18867099384ac59e88b28b14c37d777fc`  
		Last Modified: Sat, 26 May 2018 10:18:11 GMT  
		Size: 12.8 MB (12772572 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:33fbc82bebefed415e0d99d95c2199ccefd11254cfbefe0cb44e5c4235a80dbc`  
		Last Modified: Sat, 26 May 2018 10:18:06 GMT  
		Size: 491.1 KB (491125 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:494ed27bef31be226f9bb0b7dde7a3de53fee37d4a9defca95c65999a45bf288`  
		Last Modified: Sat, 26 May 2018 10:18:06 GMT  
		Size: 7.8 KB (7850 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:260011ea13c12e7f76c6ef3f3b6ac329067d5d62b1c3ea2e1438fc4d24c6e9f2`  
		Last Modified: Thu, 21 Jun 2018 09:46:58 GMT  
		Size: 57.1 MB (57055867 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7682be80ee6471502bcde4c8a3d03401fe0f247174899f7a298ea324b24bbaf8`  
		Last Modified: Thu, 21 Jun 2018 09:46:39 GMT  
		Size: 172.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e64810335b2932687826690900537543be72f782fbeb739f26c18c27c3f1a048`  
		Last Modified: Thu, 21 Jun 2018 09:46:41 GMT  
		Size: 2.5 MB (2457560 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:12da0e4bca312d2c2db7b5c9dc56916f4b56b158b309d62ae947b273fd04b8db`  
		Last Modified: Thu, 21 Jun 2018 09:47:03 GMT  
		Size: 88.8 MB (88778036 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b0398911b75ac4341523e8856acb1f5668b263bc57152d9ec5abda35b5ee15bd`  
		Last Modified: Thu, 21 Jun 2018 09:46:40 GMT  
		Size: 1.8 KB (1791 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `redmine:latest` - linux; arm variant v7

```console
$ docker pull redmine@sha256:df7144a1137742adc5e4e11125da5e4d18e517fe491950489f2f97452b2522bf
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **238.4 MB (238431615 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:f661101282a8e3e492241307b1e3a098dbc6f66588f65c554e6267e3fa781492`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["rails","server","-b","0.0.0.0"]`

```dockerfile
# Sat, 28 Apr 2018 11:59:05 GMT
ADD file:4e9c283075c120ce66f83bf541b0aeaa8a46f74c21d38e4ab1578e7f1b892823 in / 
# Sat, 28 Apr 2018 11:59:05 GMT
CMD ["bash"]
# Sat, 28 Apr 2018 15:40:52 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Sat, 28 Apr 2018 15:40:56 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Sat, 28 Apr 2018 15:40:56 GMT
ENV RUBY_MAJOR=2.4
# Sat, 28 Apr 2018 15:40:57 GMT
ENV RUBY_VERSION=2.4.4
# Sat, 28 Apr 2018 15:40:57 GMT
ENV RUBY_DOWNLOAD_SHA256=1d0034071d675193ca769f64c91827e5f54cb3a7962316a41d5217c7bc6949f0
# Thu, 24 May 2018 13:13:30 GMT
ENV RUBYGEMS_VERSION=2.7.7
# Thu, 24 May 2018 13:13:31 GMT
ENV BUNDLER_VERSION=1.16.2
# Thu, 24 May 2018 13:18:52 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		dpkg-dev 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 		xz-utils 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& dpkg-query --show --showformat '${package}\n' 		| grep -P '^libreadline\d+$' 		| xargs apt-mark manual 	&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force 	&& rm -r /root/.gem/
# Thu, 24 May 2018 13:18:53 GMT
ENV GEM_HOME=/usr/local/bundle
# Fri, 25 May 2018 12:27:41 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Fri, 25 May 2018 12:27:42 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/bundle/gems/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 25 May 2018 12:27:43 GMT
RUN mkdir -p "$GEM_HOME" && chmod 777 "$GEM_HOME"
# Fri, 25 May 2018 12:27:43 GMT
CMD ["irb"]
# Sat, 26 May 2018 12:23:55 GMT
RUN groupadd -r redmine && useradd -r -g redmine redmine
# Sat, 26 May 2018 12:24:22 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		wget 	&& rm -rf /var/lib/apt/lists/*
# Sat, 26 May 2018 12:24:22 GMT
ENV GOSU_VERSION=1.10
# Sat, 26 May 2018 12:24:24 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Sat, 26 May 2018 12:24:24 GMT
ENV TINI_VERSION=v0.16.1
# Sat, 26 May 2018 12:24:26 GMT
RUN set -x 	&& wget -O /usr/local/bin/tini "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/tini.asc "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5 	&& gpg --batch --verify /usr/local/bin/tini.asc /usr/local/bin/tini 	&& rm -r "$GNUPGHOME" /usr/local/bin/tini.asc 	&& chmod +x /usr/local/bin/tini 	&& tini -h
# Thu, 21 Jun 2018 12:06:34 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		imagemagick 		mercurial 		openssh-client 		subversion 	&& rm -rf /var/lib/apt/lists/*
# Thu, 21 Jun 2018 12:06:34 GMT
ENV RAILS_ENV=production
# Thu, 21 Jun 2018 12:06:34 GMT
WORKDIR /usr/src/redmine
# Thu, 21 Jun 2018 12:06:35 GMT
ENV REDMINE_VERSION=3.4.6
# Thu, 21 Jun 2018 12:06:35 GMT
ENV REDMINE_DOWNLOAD_MD5=5f4993446ecf25782f469763c0d32ea1
# Thu, 21 Jun 2018 12:06:39 GMT
RUN wget -O redmine.tar.gz "https://www.redmine.org/releases/redmine-${REDMINE_VERSION}.tar.gz" 	&& echo "$REDMINE_DOWNLOAD_MD5 redmine.tar.gz" | md5sum -c - 	&& tar -xvf redmine.tar.gz --strip-components=1 	&& rm redmine.tar.gz files/delete.me log/delete.me 	&& mkdir -p tmp/pdf public/plugin_assets 	&& chown -R redmine:redmine ./
# Thu, 21 Jun 2018 12:12:24 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		freetds-dev 		gcc 		libmagickcore-dev 		libmagickwand-dev 		libmysqlclient-dev 		libpq-dev 		libsqlite3-dev 		make 		patch 	; 	rm -rf /var/lib/apt/lists/*; 		bundle install --without development test; 	for adapter in mysql2 postgresql sqlserver sqlite3; do 		echo "$RAILS_ENV:" > ./config/database.yml; 		echo "  adapter: $adapter" >> ./config/database.yml; 		bundle install --without development test; 		cp Gemfile.lock "Gemfile.lock.${adapter}"; 	done; 	rm ./config/database.yml; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| grep -v '^/usr/local/' 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false
# Thu, 21 Jun 2018 12:12:25 GMT
VOLUME [/usr/src/redmine/files]
# Thu, 21 Jun 2018 12:12:25 GMT
COPY file:8064eeba1336402e59165b07c73d0734f58aa7e83e3c0a42b6888098f2e2c11d in / 
# Thu, 21 Jun 2018 12:12:25 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Thu, 21 Jun 2018 12:12:26 GMT
EXPOSE 3000/tcp
# Thu, 21 Jun 2018 12:12:26 GMT
CMD ["rails" "server" "-b" "0.0.0.0"]
```

-	Layers:
	-	`sha256:5c478157e28e3c26a0209484edb518799e1c21863d4700579c010b7203e0537f`  
		Last Modified: Sat, 28 Apr 2018 12:10:24 GMT  
		Size: 50.2 MB (50195697 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:57cc82e3a61290e4bfc39b7ec615f84e7782d645852ff04b0f1077ba3a8d6c85`  
		Last Modified: Sat, 28 Apr 2018 16:21:20 GMT  
		Size: 8.8 MB (8777726 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e60d4b7c236d855ddd6a1f286ece09d909ea721b8959a806142de215e84ad242`  
		Last Modified: Sat, 28 Apr 2018 16:21:17 GMT  
		Size: 207.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fd714148500451500a2957112b77e7e1feb9b7fa3095266d84623a097aa9935b`  
		Last Modified: Thu, 24 May 2018 13:51:44 GMT  
		Size: 20.9 MB (20939873 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:15b699e7e8d225b3c8087b29914345882f41c75520d205595171039ab1e0c856`  
		Last Modified: Fri, 25 May 2018 12:40:08 GMT  
		Size: 182.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0e957186fb243adf5019585383bf19defaa1d82b4636998b537528235dd777f2`  
		Last Modified: Sat, 26 May 2018 12:37:45 GMT  
		Size: 2.1 KB (2092 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:11e22cb6dff3aef6e6185c86a85889793c9f7fff65d461c749557bc8884b9624`  
		Last Modified: Sat, 26 May 2018 12:37:50 GMT  
		Size: 12.6 MB (12629462 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9726b5b13c21e003fe07315e1e1f21db27480310aa0606a5699f7435f62801cf`  
		Last Modified: Sat, 26 May 2018 12:37:45 GMT  
		Size: 475.3 KB (475267 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3784a11f9e4def9da3250391267c9bcffd3edd695febdb607895c2fa1524e923`  
		Last Modified: Sat, 26 May 2018 12:37:44 GMT  
		Size: 7.3 KB (7313 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1374393c860f34b65841b3158be787bc2df985c718b0bd332c8d8c7428a83e52`  
		Last Modified: Thu, 21 Jun 2018 12:18:49 GMT  
		Size: 54.7 MB (54698588 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:42db57f6861effae6af53fac1d6db5790da8afb4d14f64a0f0f22aba5649080e`  
		Last Modified: Thu, 21 Jun 2018 12:18:32 GMT  
		Size: 172.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:590497ab77d278095f81c2e419971e26ef0d6483e14a0b97ed13f8ec94a76f83`  
		Last Modified: Thu, 21 Jun 2018 12:18:34 GMT  
		Size: 2.5 MB (2457572 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d3918493345313d19d0cbd4c26bd6142b71be53be71d3976bbd956e00a1c7da8`  
		Last Modified: Thu, 21 Jun 2018 12:18:57 GMT  
		Size: 88.2 MB (88245671 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e118f56902617fa8db9f49493a8d0039c3a90976f6506cf6df565557e09560af`  
		Last Modified: Thu, 21 Jun 2018 12:18:32 GMT  
		Size: 1.8 KB (1793 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `redmine:latest` - linux; arm64 variant v8

```console
$ docker pull redmine@sha256:988df7496fea7b7cc53d5210dd1bd832b8d22cbf82fb0b9f6a7d61c366de95c4
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **243.2 MB (243226684 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:795f00ab797d1fb1e0e03e8ea4d2c01f3f953b9df56a7da35adfd390546f65a6`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["rails","server","-b","0.0.0.0"]`

```dockerfile
# Mon, 30 Apr 2018 23:21:38 GMT
ADD file:387c83918422a6546379c4d84818ca3949fcd63aec058da562b08c947a9ed571 in / 
# Mon, 30 Apr 2018 23:21:40 GMT
CMD ["bash"]
# Tue, 01 May 2018 08:41:36 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Tue, 01 May 2018 08:41:41 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Tue, 01 May 2018 08:41:42 GMT
ENV RUBY_MAJOR=2.4
# Tue, 01 May 2018 08:41:44 GMT
ENV RUBY_VERSION=2.4.4
# Tue, 01 May 2018 08:41:46 GMT
ENV RUBY_DOWNLOAD_SHA256=1d0034071d675193ca769f64c91827e5f54cb3a7962316a41d5217c7bc6949f0
# Fri, 25 May 2018 16:57:16 GMT
ENV RUBYGEMS_VERSION=2.7.7
# Fri, 25 May 2018 16:57:17 GMT
ENV BUNDLER_VERSION=1.16.2
# Fri, 25 May 2018 17:06:32 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		dpkg-dev 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 		xz-utils 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& dpkg-query --show --showformat '${package}\n' 		| grep -P '^libreadline\d+$' 		| xargs apt-mark manual 	&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force 	&& rm -r /root/.gem/
# Fri, 25 May 2018 17:06:33 GMT
ENV GEM_HOME=/usr/local/bundle
# Fri, 25 May 2018 17:06:34 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Fri, 25 May 2018 17:06:34 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/bundle/gems/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 25 May 2018 17:06:36 GMT
RUN mkdir -p "$GEM_HOME" && chmod 777 "$GEM_HOME"
# Fri, 25 May 2018 17:06:37 GMT
CMD ["irb"]
# Fri, 25 May 2018 21:43:13 GMT
RUN groupadd -r redmine && useradd -r -g redmine redmine
# Fri, 25 May 2018 21:43:38 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		wget 	&& rm -rf /var/lib/apt/lists/*
# Fri, 25 May 2018 21:43:38 GMT
ENV GOSU_VERSION=1.10
# Fri, 25 May 2018 21:43:43 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Fri, 25 May 2018 21:43:44 GMT
ENV TINI_VERSION=v0.16.1
# Fri, 25 May 2018 21:43:46 GMT
RUN set -x 	&& wget -O /usr/local/bin/tini "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/tini.asc "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5 	&& gpg --batch --verify /usr/local/bin/tini.asc /usr/local/bin/tini 	&& rm -r "$GNUPGHOME" /usr/local/bin/tini.asc 	&& chmod +x /usr/local/bin/tini 	&& tini -h
# Thu, 21 Jun 2018 16:59:11 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		imagemagick 		mercurial 		openssh-client 		subversion 	&& rm -rf /var/lib/apt/lists/*
# Thu, 21 Jun 2018 16:59:12 GMT
ENV RAILS_ENV=production
# Thu, 21 Jun 2018 16:59:13 GMT
WORKDIR /usr/src/redmine
# Thu, 21 Jun 2018 16:59:13 GMT
ENV REDMINE_VERSION=3.4.6
# Thu, 21 Jun 2018 16:59:14 GMT
ENV REDMINE_DOWNLOAD_MD5=5f4993446ecf25782f469763c0d32ea1
# Thu, 21 Jun 2018 16:59:20 GMT
RUN wget -O redmine.tar.gz "https://www.redmine.org/releases/redmine-${REDMINE_VERSION}.tar.gz" 	&& echo "$REDMINE_DOWNLOAD_MD5 redmine.tar.gz" | md5sum -c - 	&& tar -xvf redmine.tar.gz --strip-components=1 	&& rm redmine.tar.gz files/delete.me log/delete.me 	&& mkdir -p tmp/pdf public/plugin_assets 	&& chown -R redmine:redmine ./
# Thu, 21 Jun 2018 17:12:12 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		freetds-dev 		gcc 		libmagickcore-dev 		libmagickwand-dev 		libmysqlclient-dev 		libpq-dev 		libsqlite3-dev 		make 		patch 	; 	rm -rf /var/lib/apt/lists/*; 		bundle install --without development test; 	for adapter in mysql2 postgresql sqlserver sqlite3; do 		echo "$RAILS_ENV:" > ./config/database.yml; 		echo "  adapter: $adapter" >> ./config/database.yml; 		bundle install --without development test; 		cp Gemfile.lock "Gemfile.lock.${adapter}"; 	done; 	rm ./config/database.yml; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| grep -v '^/usr/local/' 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false
# Thu, 21 Jun 2018 17:12:14 GMT
VOLUME [/usr/src/redmine/files]
# Thu, 21 Jun 2018 17:12:14 GMT
COPY file:8064eeba1336402e59165b07c73d0734f58aa7e83e3c0a42b6888098f2e2c11d in / 
# Thu, 21 Jun 2018 17:12:15 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Thu, 21 Jun 2018 17:12:16 GMT
EXPOSE 3000/tcp
# Thu, 21 Jun 2018 17:12:17 GMT
CMD ["rails" "server" "-b" "0.0.0.0"]
```

-	Layers:
	-	`sha256:363cfded2ef3921ef972c85cafc77cf16cdcfddfd49782ad4540cb73fd5e57a2`  
		Last Modified: Mon, 30 Apr 2018 23:41:06 GMT  
		Size: 51.4 MB (51446854 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6aeaeeebfa7e2a1e6c69a484a7648b6313aff4bf219767667e43bbfc42bb40d9`  
		Last Modified: Tue, 01 May 2018 09:53:45 GMT  
		Size: 9.3 MB (9343083 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3b78cb3f4882a2b3bf1ecb4fdbe1e145a3ddb80ce1fde62a33ada1beaf12daf8`  
		Last Modified: Tue, 01 May 2018 09:53:41 GMT  
		Size: 205.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:18547e3cbea8ccf1a7ca22515077049b202d0f12cac441573f4edf1f9b567209`  
		Last Modified: Fri, 25 May 2018 18:07:21 GMT  
		Size: 21.3 MB (21265153 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1d6d550606a490752c05952acf272ef8a1e4df8e3a8be58f37f50260160a5b11`  
		Last Modified: Fri, 25 May 2018 18:07:10 GMT  
		Size: 148.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:548893d753de4a74e5a64d26225a85691cfd2ad2b0546591161f46916ea1229f`  
		Last Modified: Fri, 25 May 2018 22:12:00 GMT  
		Size: 2.1 KB (2113 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a5ecd4fc430347071a2c164435746340e018f58d8037eabf8dd5665ad1b0dff6`  
		Last Modified: Fri, 25 May 2018 22:12:03 GMT  
		Size: 12.9 MB (12940690 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bfc6b9486743d7946d7922a4c47f0cc78876f91c3db011553f4f9a25a1dc96e2`  
		Last Modified: Fri, 25 May 2018 22:11:58 GMT  
		Size: 468.7 KB (468701 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e8f19d3b246e0490714656220e538767a6b0f47ae8f43c10cc32017687ae3114`  
		Last Modified: Fri, 25 May 2018 22:11:58 GMT  
		Size: 8.2 KB (8154 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:33f179dd0cce7b503211ff6d22a331d47169a234442ac5b0f6d11519eb3ead53`  
		Last Modified: Thu, 21 Jun 2018 17:27:27 GMT  
		Size: 56.2 MB (56166767 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b00c8c2de88468ac5d8b2af1848ffa502eded4adfd3a7e8e3859a57018eaace6`  
		Last Modified: Thu, 21 Jun 2018 17:27:04 GMT  
		Size: 140.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:95eb29922954e0efbb03fb3ca6512c8ce0d257303fc9a551e8d52455bef6d5b1`  
		Last Modified: Thu, 21 Jun 2018 17:27:07 GMT  
		Size: 2.5 MB (2456916 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f2bfa5dcbc83e5d3cd044dfbc3d81faa5b22a07684e60e5ca7cc0c8f4c76a57f`  
		Last Modified: Thu, 21 Jun 2018 17:27:35 GMT  
		Size: 89.1 MB (89125967 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:51f3ad7cc3086c71f467f0eee89ca821bc6f3aae7bd05ce85b8eb78d72e15a94`  
		Last Modified: Thu, 21 Jun 2018 17:27:04 GMT  
		Size: 1.8 KB (1793 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `redmine:latest` - linux; 386

```console
$ docker pull redmine@sha256:d87c7c46bff353bc7e6f129b084607c93da5931f3d61a8ab52a1a2e6895bf371
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **253.9 MB (253912619 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:f17b65464fff83d872964798559dc27680b6902daaba36df7306c9fa0a810e9d`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["rails","server","-b","0.0.0.0"]`

```dockerfile
# Sat, 28 Apr 2018 10:39:32 GMT
ADD file:ce5174f2b2c155a2421fac3ff37a02d9551d5d79e31a541189bcfd2416a6903a in / 
# Sat, 28 Apr 2018 10:39:32 GMT
CMD ["bash"]
# Fri, 01 Jun 2018 14:56:41 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Fri, 01 Jun 2018 14:56:42 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Fri, 01 Jun 2018 14:56:42 GMT
ENV RUBY_MAJOR=2.4
# Fri, 01 Jun 2018 14:56:42 GMT
ENV RUBY_VERSION=2.4.4
# Fri, 01 Jun 2018 14:56:42 GMT
ENV RUBY_DOWNLOAD_SHA256=1d0034071d675193ca769f64c91827e5f54cb3a7962316a41d5217c7bc6949f0
# Fri, 01 Jun 2018 14:56:42 GMT
ENV RUBYGEMS_VERSION=2.7.7
# Fri, 01 Jun 2018 14:56:42 GMT
ENV BUNDLER_VERSION=1.16.2
# Fri, 01 Jun 2018 15:04:05 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		dpkg-dev 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 		xz-utils 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& dpkg-query --show --showformat '${package}\n' 		| grep -P '^libreadline\d+$' 		| xargs apt-mark manual 	&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force 	&& rm -r /root/.gem/
# Fri, 01 Jun 2018 15:04:06 GMT
ENV GEM_HOME=/usr/local/bundle
# Fri, 01 Jun 2018 15:04:06 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Fri, 01 Jun 2018 15:04:06 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/bundle/gems/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 01 Jun 2018 15:04:07 GMT
RUN mkdir -p "$GEM_HOME" && chmod 777 "$GEM_HOME"
# Fri, 01 Jun 2018 15:04:07 GMT
CMD ["irb"]
# Fri, 01 Jun 2018 17:09:55 GMT
RUN groupadd -r redmine && useradd -r -g redmine redmine
# Fri, 01 Jun 2018 17:10:49 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		wget 	&& rm -rf /var/lib/apt/lists/*
# Fri, 01 Jun 2018 17:10:49 GMT
ENV GOSU_VERSION=1.10
# Fri, 01 Jun 2018 17:10:56 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Fri, 01 Jun 2018 17:10:56 GMT
ENV TINI_VERSION=v0.16.1
# Fri, 01 Jun 2018 17:10:59 GMT
RUN set -x 	&& wget -O /usr/local/bin/tini "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/tini.asc "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5 	&& gpg --batch --verify /usr/local/bin/tini.asc /usr/local/bin/tini 	&& rm -r "$GNUPGHOME" /usr/local/bin/tini.asc 	&& chmod +x /usr/local/bin/tini 	&& tini -h
# Thu, 21 Jun 2018 11:00:37 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		imagemagick 		mercurial 		openssh-client 		subversion 	&& rm -rf /var/lib/apt/lists/*
# Thu, 21 Jun 2018 11:00:38 GMT
ENV RAILS_ENV=production
# Thu, 21 Jun 2018 11:00:38 GMT
WORKDIR /usr/src/redmine
# Thu, 21 Jun 2018 11:00:38 GMT
ENV REDMINE_VERSION=3.4.6
# Thu, 21 Jun 2018 11:00:39 GMT
ENV REDMINE_DOWNLOAD_MD5=5f4993446ecf25782f469763c0d32ea1
# Thu, 21 Jun 2018 11:00:43 GMT
RUN wget -O redmine.tar.gz "https://www.redmine.org/releases/redmine-${REDMINE_VERSION}.tar.gz" 	&& echo "$REDMINE_DOWNLOAD_MD5 redmine.tar.gz" | md5sum -c - 	&& tar -xvf redmine.tar.gz --strip-components=1 	&& rm redmine.tar.gz files/delete.me log/delete.me 	&& mkdir -p tmp/pdf public/plugin_assets 	&& chown -R redmine:redmine ./
# Thu, 21 Jun 2018 11:07:27 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		freetds-dev 		gcc 		libmagickcore-dev 		libmagickwand-dev 		libmysqlclient-dev 		libpq-dev 		libsqlite3-dev 		make 		patch 	; 	rm -rf /var/lib/apt/lists/*; 		bundle install --without development test; 	for adapter in mysql2 postgresql sqlserver sqlite3; do 		echo "$RAILS_ENV:" > ./config/database.yml; 		echo "  adapter: $adapter" >> ./config/database.yml; 		bundle install --without development test; 		cp Gemfile.lock "Gemfile.lock.${adapter}"; 	done; 	rm ./config/database.yml; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| grep -v '^/usr/local/' 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false
# Thu, 21 Jun 2018 11:07:28 GMT
VOLUME [/usr/src/redmine/files]
# Thu, 21 Jun 2018 11:07:35 GMT
COPY file:8064eeba1336402e59165b07c73d0734f58aa7e83e3c0a42b6888098f2e2c11d in / 
# Thu, 21 Jun 2018 11:07:36 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Thu, 21 Jun 2018 11:07:36 GMT
EXPOSE 3000/tcp
# Thu, 21 Jun 2018 11:07:36 GMT
CMD ["rails" "server" "-b" "0.0.0.0"]
```

-	Layers:
	-	`sha256:05b419d667f793c8c2edf0ff0aec14fc4d66733cdb89957ac89e8bfbeaddd0fa`  
		Last Modified: Sat, 28 Apr 2018 10:44:20 GMT  
		Size: 54.5 MB (54486782 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3d6891754f33e4c1f328ba0f4530fdb8383be81d86d518c6967565db3d8a7d3f`  
		Last Modified: Fri, 01 Jun 2018 15:49:54 GMT  
		Size: 14.9 MB (14942131 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:089cb9bb407565a3373144a74a72a2345d043f8423185a11fe236787bfc2d617`  
		Last Modified: Fri, 01 Jun 2018 15:49:47 GMT  
		Size: 208.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b853b205add0f75c6d80bbdfcfd40d09d2435262eb1076c603fd5a6ffff58a15`  
		Last Modified: Fri, 01 Jun 2018 15:49:56 GMT  
		Size: 20.3 MB (20303639 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7911295bc17916b28653d7cd6782d5eaede8fbbd7814f157a445829de1488cc8`  
		Last Modified: Fri, 01 Jun 2018 15:49:47 GMT  
		Size: 148.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2f80ba1db311f9d427a674563c28a8673d1b2941bcf25116f71c8446c382a3b4`  
		Last Modified: Fri, 01 Jun 2018 17:31:18 GMT  
		Size: 2.1 KB (2090 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ff801544c3611060c1d01382b678c4ae46af418e380369f5ebe1d34b0f29d77e`  
		Last Modified: Fri, 01 Jun 2018 17:31:27 GMT  
		Size: 13.1 MB (13103088 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a8e57a3fcd9a49a1c8880a39b935633a3041926c55a56be8bd38c07adff2c4fa`  
		Last Modified: Fri, 01 Jun 2018 17:31:16 GMT  
		Size: 480.6 KB (480563 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0351ff4ecba98d1064a87e597d3a72a277f456c7c8c5ca2c5d3232ee7d9ac7a5`  
		Last Modified: Fri, 01 Jun 2018 17:31:14 GMT  
		Size: 8.6 KB (8565 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a6451afdfb1e0e39ceba0ae2d333f8b7517af15e4c692a597d1b54293e304bb1`  
		Last Modified: Thu, 21 Jun 2018 11:15:18 GMT  
		Size: 60.6 MB (60580239 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bf645102966d197165f4e7e583a568f06ddf47daafd8fb4d473042543a2cac26`  
		Last Modified: Thu, 21 Jun 2018 11:14:48 GMT  
		Size: 140.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ce01371909c6db5cdb9d92de323d2973c0dd219f9f8daba9055a9dc8195ec003`  
		Last Modified: Thu, 21 Jun 2018 11:14:50 GMT  
		Size: 2.5 MB (2456909 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:95d4b6248a4676e50ab8bbfe182fb99d5dd0caff607308555d3f8d9147948743`  
		Last Modified: Thu, 21 Jun 2018 11:15:20 GMT  
		Size: 87.5 MB (87546324 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:114fe7ad48c3d506f86cfc90e19d21acbd0d6f6f8686ffd8c241234719076c80`  
		Last Modified: Thu, 21 Jun 2018 11:14:48 GMT  
		Size: 1.8 KB (1793 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `redmine:latest` - linux; ppc64le

```console
$ docker pull redmine@sha256:907c86f110cb9245f282d9daeb30d2fef6fe5073bc1c78cea57bc0f4c745dc1a
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **249.9 MB (249907098 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:b0de66b8b9f108221b0d577f34253c4482d759cf811a688bfc94660b4c03cb28`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["rails","server","-b","0.0.0.0"]`

```dockerfile
# Sat, 28 Apr 2018 08:17:46 GMT
ADD file:6a4bd4ea54f669286e984ecf8178e1fa7c12c8b6fc0f96e4203ae7a6f99a2279 in / 
# Sat, 28 Apr 2018 08:17:47 GMT
CMD ["bash"]
# Sat, 28 Apr 2018 11:24:06 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Sat, 28 Apr 2018 11:24:08 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Sat, 28 Apr 2018 11:24:08 GMT
ENV RUBY_MAJOR=2.4
# Sat, 28 Apr 2018 11:24:08 GMT
ENV RUBY_VERSION=2.4.4
# Sat, 28 Apr 2018 11:24:09 GMT
ENV RUBY_DOWNLOAD_SHA256=1d0034071d675193ca769f64c91827e5f54cb3a7962316a41d5217c7bc6949f0
# Thu, 24 May 2018 10:50:48 GMT
ENV RUBYGEMS_VERSION=2.7.7
# Thu, 24 May 2018 10:50:50 GMT
ENV BUNDLER_VERSION=1.16.2
# Thu, 24 May 2018 10:58:50 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		dpkg-dev 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 		xz-utils 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& dpkg-query --show --showformat '${package}\n' 		| grep -P '^libreadline\d+$' 		| xargs apt-mark manual 	&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force 	&& rm -r /root/.gem/
# Thu, 24 May 2018 10:58:51 GMT
ENV GEM_HOME=/usr/local/bundle
# Fri, 25 May 2018 09:19:08 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Fri, 25 May 2018 09:19:09 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/bundle/gems/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 25 May 2018 09:19:10 GMT
RUN mkdir -p "$GEM_HOME" && chmod 777 "$GEM_HOME"
# Fri, 25 May 2018 09:19:11 GMT
CMD ["irb"]
# Sat, 26 May 2018 09:41:15 GMT
RUN groupadd -r redmine && useradd -r -g redmine redmine
# Sat, 26 May 2018 09:42:45 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		wget 	&& rm -rf /var/lib/apt/lists/*
# Sat, 26 May 2018 09:42:51 GMT
ENV GOSU_VERSION=1.10
# Sat, 26 May 2018 09:43:05 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Sat, 26 May 2018 09:43:11 GMT
ENV TINI_VERSION=v0.16.1
# Sat, 26 May 2018 09:43:19 GMT
RUN set -x 	&& wget -O /usr/local/bin/tini "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/tini.asc "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5 	&& gpg --batch --verify /usr/local/bin/tini.asc /usr/local/bin/tini 	&& rm -r "$GNUPGHOME" /usr/local/bin/tini.asc 	&& chmod +x /usr/local/bin/tini 	&& tini -h
# Thu, 21 Jun 2018 09:57:56 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		imagemagick 		mercurial 		openssh-client 		subversion 	&& rm -rf /var/lib/apt/lists/*
# Thu, 21 Jun 2018 09:57:57 GMT
ENV RAILS_ENV=production
# Thu, 21 Jun 2018 09:57:58 GMT
WORKDIR /usr/src/redmine
# Thu, 21 Jun 2018 09:57:58 GMT
ENV REDMINE_VERSION=3.4.6
# Thu, 21 Jun 2018 09:57:59 GMT
ENV REDMINE_DOWNLOAD_MD5=5f4993446ecf25782f469763c0d32ea1
# Thu, 21 Jun 2018 09:58:05 GMT
RUN wget -O redmine.tar.gz "https://www.redmine.org/releases/redmine-${REDMINE_VERSION}.tar.gz" 	&& echo "$REDMINE_DOWNLOAD_MD5 redmine.tar.gz" | md5sum -c - 	&& tar -xvf redmine.tar.gz --strip-components=1 	&& rm redmine.tar.gz files/delete.me log/delete.me 	&& mkdir -p tmp/pdf public/plugin_assets 	&& chown -R redmine:redmine ./
# Thu, 21 Jun 2018 10:09:09 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		freetds-dev 		gcc 		libmagickcore-dev 		libmagickwand-dev 		libmysqlclient-dev 		libpq-dev 		libsqlite3-dev 		make 		patch 	; 	rm -rf /var/lib/apt/lists/*; 		bundle install --without development test; 	for adapter in mysql2 postgresql sqlserver sqlite3; do 		echo "$RAILS_ENV:" > ./config/database.yml; 		echo "  adapter: $adapter" >> ./config/database.yml; 		bundle install --without development test; 		cp Gemfile.lock "Gemfile.lock.${adapter}"; 	done; 	rm ./config/database.yml; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| grep -v '^/usr/local/' 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false
# Thu, 21 Jun 2018 10:09:12 GMT
VOLUME [/usr/src/redmine/files]
# Thu, 21 Jun 2018 10:09:12 GMT
COPY file:8064eeba1336402e59165b07c73d0734f58aa7e83e3c0a42b6888098f2e2c11d in / 
# Thu, 21 Jun 2018 10:09:14 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Thu, 21 Jun 2018 10:09:15 GMT
EXPOSE 3000/tcp
# Thu, 21 Jun 2018 10:09:19 GMT
CMD ["rails" "server" "-b" "0.0.0.0"]
```

-	Layers:
	-	`sha256:2668401c9f940b1d6b03e5f0086fa248cb957610ef9a7c79983d2fb0707ec76c`  
		Last Modified: Sat, 28 Apr 2018 08:24:36 GMT  
		Size: 53.4 MB (53392811 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ab444779be019b7a69946ce8e93e0062d82eedfe747470714b266730847305b0`  
		Last Modified: Sat, 28 Apr 2018 12:15:08 GMT  
		Size: 10.1 MB (10137971 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b6bfab4f27e54de1711e2752ce393ce141c20aef64a8cd42d95a20585d28fa73`  
		Last Modified: Sat, 28 Apr 2018 12:15:04 GMT  
		Size: 207.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8b15968d0ad41cd76cb81ece13f4d2ca5a0d8d6e4579ae1e619f8ddd2ad295c2`  
		Last Modified: Thu, 24 May 2018 11:43:15 GMT  
		Size: 21.8 MB (21757239 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:351a7ed5b215a7bd4c196ac77237a20aec73a9a6665d2224deead4283218f7d6`  
		Last Modified: Fri, 25 May 2018 09:32:02 GMT  
		Size: 183.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6bd39d3e6422d52b16dfac40b0f9fd915fe70de5266ff6e1c6a545538a617171`  
		Last Modified: Sat, 26 May 2018 10:28:52 GMT  
		Size: 2.1 KB (2122 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b890c32c8a35b49718465b739aa29851ea5d09645363047bcfd2646d0c7e59d2`  
		Last Modified: Sat, 26 May 2018 10:28:53 GMT  
		Size: 13.1 MB (13113602 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4a2678fca66b07491a24dbcff3ff476be318e02d27a9fa400cad6b5f547dd076`  
		Last Modified: Sat, 26 May 2018 10:28:49 GMT  
		Size: 469.8 KB (469848 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c4a046b512a788097cb981ae07112f3acf9a3a7e482327497e84752c042b0e3d`  
		Last Modified: Sat, 26 May 2018 10:28:49 GMT  
		Size: 8.6 KB (8645 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bbb5e064795a21c6fe2b678532828599dfeca38475f384ae401a3452917112a2`  
		Last Modified: Thu, 21 Jun 2018 10:24:26 GMT  
		Size: 58.6 MB (58565791 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8a889f049e1545e24c2d4646d29bf7b0a3e0f72f2d286d8c219dbe346c08efb9`  
		Last Modified: Thu, 21 Jun 2018 10:24:09 GMT  
		Size: 172.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7da14007fe0da424adf4a75292ded9fae229448fbca2f31fd9be25d875290f85`  
		Last Modified: Thu, 21 Jun 2018 10:24:10 GMT  
		Size: 2.5 MB (2457580 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ccc76284d5a2c5b70dc71348dd65954b145b82b10252ae4c34b4960f37e90b86`  
		Last Modified: Thu, 21 Jun 2018 10:24:30 GMT  
		Size: 90.0 MB (89999138 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f957288162825d819debf1f6f7c10ee1f44c5bd0d99f411380a51626910bda76`  
		Last Modified: Thu, 21 Jun 2018 10:24:10 GMT  
		Size: 1.8 KB (1789 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `redmine:latest` - linux; s390x

```console
$ docker pull redmine@sha256:30b50ca230b2b96668f067c3aa64f4ab650c5d0f58b705b9475e8eb036d65f63
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **254.9 MB (254937140 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:924bf921e4b13986dd1234309bc076c1a40bf4134fc02b23ec26aac9448fc0e1`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["rails","server","-b","0.0.0.0"]`

```dockerfile
# Sat, 28 Apr 2018 11:42:31 GMT
ADD file:ac1cfec75c7e1898f2c9b7d17653da3684fdda7d14440ce16f1939bb66105cdc in / 
# Sat, 28 Apr 2018 11:42:31 GMT
CMD ["bash"]
# Sat, 28 Apr 2018 15:34:23 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Sat, 28 Apr 2018 15:34:24 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Sat, 28 Apr 2018 15:34:24 GMT
ENV RUBY_MAJOR=2.4
# Sat, 28 Apr 2018 15:34:24 GMT
ENV RUBY_VERSION=2.4.4
# Sat, 28 Apr 2018 15:34:24 GMT
ENV RUBY_DOWNLOAD_SHA256=1d0034071d675193ca769f64c91827e5f54cb3a7962316a41d5217c7bc6949f0
# Thu, 24 May 2018 13:16:30 GMT
ENV RUBYGEMS_VERSION=2.7.7
# Thu, 24 May 2018 13:16:30 GMT
ENV BUNDLER_VERSION=1.16.2
# Thu, 24 May 2018 13:19:35 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		dpkg-dev 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 		xz-utils 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& dpkg-query --show --showformat '${package}\n' 		| grep -P '^libreadline\d+$' 		| xargs apt-mark manual 	&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force 	&& rm -r /root/.gem/
# Thu, 24 May 2018 13:19:35 GMT
ENV GEM_HOME=/usr/local/bundle
# Fri, 25 May 2018 11:58:16 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Fri, 25 May 2018 11:58:17 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/bundle/gems/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 25 May 2018 11:58:17 GMT
RUN mkdir -p "$GEM_HOME" && chmod 777 "$GEM_HOME"
# Fri, 25 May 2018 11:58:18 GMT
CMD ["irb"]
# Sat, 26 May 2018 13:25:59 GMT
RUN groupadd -r redmine && useradd -r -g redmine redmine
# Sat, 26 May 2018 13:26:09 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		wget 	&& rm -rf /var/lib/apt/lists/*
# Sat, 26 May 2018 13:26:09 GMT
ENV GOSU_VERSION=1.10
# Sat, 26 May 2018 13:26:11 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Sat, 26 May 2018 13:26:12 GMT
ENV TINI_VERSION=v0.16.1
# Sat, 26 May 2018 13:26:14 GMT
RUN set -x 	&& wget -O /usr/local/bin/tini "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/tini.asc "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5 	&& gpg --batch --verify /usr/local/bin/tini.asc /usr/local/bin/tini 	&& rm -r "$GNUPGHOME" /usr/local/bin/tini.asc 	&& chmod +x /usr/local/bin/tini 	&& tini -h
# Thu, 21 Jun 2018 13:40:18 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		imagemagick 		mercurial 		openssh-client 		subversion 	&& rm -rf /var/lib/apt/lists/*
# Thu, 21 Jun 2018 13:40:20 GMT
ENV RAILS_ENV=production
# Thu, 21 Jun 2018 13:40:20 GMT
WORKDIR /usr/src/redmine
# Thu, 21 Jun 2018 13:40:20 GMT
ENV REDMINE_VERSION=3.4.6
# Thu, 21 Jun 2018 13:40:20 GMT
ENV REDMINE_DOWNLOAD_MD5=5f4993446ecf25782f469763c0d32ea1
# Thu, 21 Jun 2018 13:40:23 GMT
RUN wget -O redmine.tar.gz "https://www.redmine.org/releases/redmine-${REDMINE_VERSION}.tar.gz" 	&& echo "$REDMINE_DOWNLOAD_MD5 redmine.tar.gz" | md5sum -c - 	&& tar -xvf redmine.tar.gz --strip-components=1 	&& rm redmine.tar.gz files/delete.me log/delete.me 	&& mkdir -p tmp/pdf public/plugin_assets 	&& chown -R redmine:redmine ./
# Thu, 21 Jun 2018 13:43:55 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		freetds-dev 		gcc 		libmagickcore-dev 		libmagickwand-dev 		libmysqlclient-dev 		libpq-dev 		libsqlite3-dev 		make 		patch 	; 	rm -rf /var/lib/apt/lists/*; 		bundle install --without development test; 	for adapter in mysql2 postgresql sqlserver sqlite3; do 		echo "$RAILS_ENV:" > ./config/database.yml; 		echo "  adapter: $adapter" >> ./config/database.yml; 		bundle install --without development test; 		cp Gemfile.lock "Gemfile.lock.${adapter}"; 	done; 	rm ./config/database.yml; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| grep -v '^/usr/local/' 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false
# Thu, 21 Jun 2018 13:43:56 GMT
VOLUME [/usr/src/redmine/files]
# Thu, 21 Jun 2018 13:43:56 GMT
COPY file:8064eeba1336402e59165b07c73d0734f58aa7e83e3c0a42b6888098f2e2c11d in / 
# Thu, 21 Jun 2018 13:43:57 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Thu, 21 Jun 2018 13:43:57 GMT
EXPOSE 3000/tcp
# Thu, 21 Jun 2018 13:43:57 GMT
CMD ["rails" "server" "-b" "0.0.0.0"]
```

-	Layers:
	-	`sha256:e0524893a6d25f3e36c190fea678ecf1845e7c0d2ba833b077a429d64b943e0a`  
		Last Modified: Sat, 28 Apr 2018 11:47:52 GMT  
		Size: 54.5 MB (54465857 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:61347f1daff97305b17924679d0a40043c3c68c04ecd38580c03a9f5f14cc025`  
		Last Modified: Sat, 28 Apr 2018 16:00:45 GMT  
		Size: 10.0 MB (9963110 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4516576626d0afc4ce307a23343efc17d8fa199788465d6fb1966c6e38405270`  
		Last Modified: Sat, 28 Apr 2018 16:00:42 GMT  
		Size: 205.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5db3c4bbb862bf979405dbf70d32620b3868872a06f125c0636aa2ca5d9a8118`  
		Last Modified: Thu, 24 May 2018 13:48:49 GMT  
		Size: 21.7 MB (21709046 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cc118bcf2202904ad8addf51827feb3eb0be972ee9912cfef0c03d939af4af5d`  
		Last Modified: Fri, 25 May 2018 12:08:37 GMT  
		Size: 148.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0bedd5671d7bb05f77a136f485548dd94b826bcaeca59790f44d37972cac966c`  
		Last Modified: Sat, 26 May 2018 13:34:13 GMT  
		Size: 2.1 KB (2107 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:df0ad57d1afd283e6ea7a12a3fdb17282925a2ac6c8fc1e0b18594b70f4860d8`  
		Last Modified: Sat, 26 May 2018 13:34:15 GMT  
		Size: 13.1 MB (13130009 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:38f941c2e8a178296eb5ef00af421a44bd40170e8b4535faf85b8c0f669e4127`  
		Last Modified: Sat, 26 May 2018 13:34:13 GMT  
		Size: 486.8 KB (486831 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2b65703d4fed12215b832fd6eb431e15ec6df3ea624470903495fa95675645b2`  
		Last Modified: Sat, 26 May 2018 13:34:11 GMT  
		Size: 8.6 KB (8628 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:147ee1fc1b1a421958c0c5f1e52aa1fcd3bb3db7c6b68f6c4c69b8daa4356bdd`  
		Last Modified: Thu, 21 Jun 2018 13:47:39 GMT  
		Size: 59.5 MB (59533196 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:33fc24964afaca53a8f69b089f296f90016a97249c28644192e99669d94ca950`  
		Last Modified: Thu, 21 Jun 2018 13:47:26 GMT  
		Size: 139.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:95937785bb16f99b2d94476fe49fab2418fd81f458a9214d61406057d60561f7`  
		Last Modified: Thu, 21 Jun 2018 13:47:27 GMT  
		Size: 2.5 MB (2456908 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5621a26308c9d8073f8ef0d18bc14689e45b96da0d71fe09658c0311b4578690`  
		Last Modified: Thu, 21 Jun 2018 13:47:43 GMT  
		Size: 93.2 MB (93179163 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1ff10f665c615aa7ed26b1dd97eec9db4674eb2affa120fb7b23dc95d1b52b7c`  
		Last Modified: Thu, 21 Jun 2018 13:47:26 GMT  
		Size: 1.8 KB (1793 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `redmine:passenger`

```console
$ docker pull redmine@sha256:fcb61c193c1ac787a3bcb36a480f369dc115cee985dbef56bd855aa32869c6b9
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `redmine:passenger` - linux; amd64

```console
$ docker pull redmine@sha256:c5345ca71ca7a09d13827489ff2976b31b6448f942990fe801485222f931efb0
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **273.9 MB (273922952 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:906833a174e69cdf240302ed3eb2ab694bb5536f544fed950d48ff6b55daca3d`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["passenger","start"]`

```dockerfile
# Sat, 28 Apr 2018 06:44:15 GMT
ADD file:3e6141c0c9cb74b14a281eb3ab7aaf162a625733e652c3948b323bb2ec8b4343 in / 
# Sat, 28 Apr 2018 06:44:16 GMT
CMD ["bash"]
# Sun, 29 Apr 2018 16:52:40 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		bzip2 		ca-certificates 		libffi-dev 		libgdbm3 		libssl-dev 		libyaml-dev 		procps 		zlib1g-dev 	&& rm -rf /var/lib/apt/lists/*
# Sun, 29 Apr 2018 16:52:41 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Sun, 29 Apr 2018 16:52:42 GMT
ENV RUBY_MAJOR=2.4
# Sun, 29 Apr 2018 16:52:42 GMT
ENV RUBY_VERSION=2.4.4
# Sun, 29 Apr 2018 16:52:42 GMT
ENV RUBY_DOWNLOAD_SHA256=1d0034071d675193ca769f64c91827e5f54cb3a7962316a41d5217c7bc6949f0
# Thu, 24 May 2018 01:25:52 GMT
ENV RUBYGEMS_VERSION=2.7.7
# Thu, 24 May 2018 01:25:52 GMT
ENV BUNDLER_VERSION=1.16.2
# Thu, 24 May 2018 01:29:14 GMT
RUN set -ex 		&& buildDeps=' 		autoconf 		bison 		dpkg-dev 		gcc 		libbz2-dev 		libgdbm-dev 		libglib2.0-dev 		libncurses-dev 		libreadline-dev 		libxml2-dev 		libxslt-dev 		make 		ruby 		wget 		xz-utils 	' 	&& apt-get update 	&& apt-get install -y --no-install-recommends $buildDeps 	&& rm -rf /var/lib/apt/lists/* 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& dpkg-query --show --showformat '${package}\n' 		| grep -P '^libreadline\d+$' 		| xargs apt-mark manual 	&& apt-get purge -y --auto-remove $buildDeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION" 	&& gem install bundler --version "$BUNDLER_VERSION" --force 	&& rm -r /root/.gem/
# Thu, 24 May 2018 01:29:14 GMT
ENV GEM_HOME=/usr/local/bundle
# Thu, 24 May 2018 21:08:01 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Thu, 24 May 2018 21:08:02 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/bundle/gems/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Thu, 24 May 2018 21:08:02 GMT
RUN mkdir -p "$GEM_HOME" && chmod 777 "$GEM_HOME"
# Thu, 24 May 2018 21:08:03 GMT
CMD ["irb"]
# Fri, 25 May 2018 22:37:54 GMT
RUN groupadd -r redmine && useradd -r -g redmine redmine
# Fri, 25 May 2018 22:38:14 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		wget 	&& rm -rf /var/lib/apt/lists/*
# Fri, 25 May 2018 22:38:14 GMT
ENV GOSU_VERSION=1.10
# Fri, 25 May 2018 22:38:18 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Fri, 25 May 2018 22:38:18 GMT
ENV TINI_VERSION=v0.16.1
# Fri, 25 May 2018 22:38:20 GMT
RUN set -x 	&& wget -O /usr/local/bin/tini "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/tini.asc "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5 	&& gpg --batch --verify /usr/local/bin/tini.asc /usr/local/bin/tini 	&& rm -r "$GNUPGHOME" /usr/local/bin/tini.asc 	&& chmod +x /usr/local/bin/tini 	&& tini -h
# Wed, 20 Jun 2018 21:28:18 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		imagemagick 		mercurial 		openssh-client 		subversion 	&& rm -rf /var/lib/apt/lists/*
# Wed, 20 Jun 2018 21:28:18 GMT
ENV RAILS_ENV=production
# Wed, 20 Jun 2018 21:28:19 GMT
WORKDIR /usr/src/redmine
# Wed, 20 Jun 2018 21:28:19 GMT
ENV REDMINE_VERSION=3.4.6
# Wed, 20 Jun 2018 21:28:19 GMT
ENV REDMINE_DOWNLOAD_MD5=5f4993446ecf25782f469763c0d32ea1
# Wed, 20 Jun 2018 21:28:23 GMT
RUN wget -O redmine.tar.gz "https://www.redmine.org/releases/redmine-${REDMINE_VERSION}.tar.gz" 	&& echo "$REDMINE_DOWNLOAD_MD5 redmine.tar.gz" | md5sum -c - 	&& tar -xvf redmine.tar.gz --strip-components=1 	&& rm redmine.tar.gz files/delete.me log/delete.me 	&& mkdir -p tmp/pdf public/plugin_assets 	&& chown -R redmine:redmine ./
# Wed, 20 Jun 2018 21:31:54 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 	apt-get install -y --no-install-recommends 		freetds-dev 		gcc 		libmagickcore-dev 		libmagickwand-dev 		libmysqlclient-dev 		libpq-dev 		libsqlite3-dev 		make 		patch 	; 	rm -rf /var/lib/apt/lists/*; 		bundle install --without development test; 	for adapter in mysql2 postgresql sqlserver sqlite3; do 		echo "$RAILS_ENV:" > ./config/database.yml; 		echo "  adapter: $adapter" >> ./config/database.yml; 		bundle install --without development test; 		cp Gemfile.lock "Gemfile.lock.${adapter}"; 	done; 	rm ./config/database.yml; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	find /usr/local -type f -executable -exec ldd '{}' ';' 		| awk '/=>/ { print $(NF-1) }' 		| sort -u 		| grep -v '^/usr/local/' 		| xargs -r dpkg-query --search 		| cut -d: -f1 		| sort -u 		| xargs -r apt-mark manual 	; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false
# Wed, 20 Jun 2018 21:31:54 GMT
VOLUME [/usr/src/redmine/files]
# Wed, 20 Jun 2018 21:31:54 GMT
COPY file:8064eeba1336402e59165b07c73d0734f58aa7e83e3c0a42b6888098f2e2c11d in / 
# Wed, 20 Jun 2018 21:31:55 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Wed, 20 Jun 2018 21:31:55 GMT
EXPOSE 3000/tcp
# Wed, 20 Jun 2018 21:31:55 GMT
CMD ["rails" "server" "-b" "0.0.0.0"]
# Wed, 20 Jun 2018 21:38:41 GMT
ENV PASSENGER_VERSION=5.3.2
# Wed, 20 Jun 2018 21:39:09 GMT
RUN buildDeps=' 		make 	' 	&& set -x 	&& apt-get update && apt-get install -y --no-install-recommends $buildDeps && rm -rf /var/lib/apt/lists/* 	&& gem install passenger --version "$PASSENGER_VERSION" 	&& apt-get purge -y --auto-remove $buildDeps
# Wed, 20 Jun 2018 21:39:10 GMT
RUN set -x 	&& passenger-config install-agent 	&& passenger-config download-nginx-engine
# Wed, 20 Jun 2018 21:39:10 GMT
CMD ["passenger" "start"]
```

-	Layers:
	-	`sha256:3d77ce4481b119f00e53bee9b4a443469c42c224db954ddaa2e6b74cd73cd5d0`  
		Last Modified: Sat, 28 Apr 2018 08:24:47 GMT  
		Size: 54.3 MB (54262566 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:05a78650ca91970038096c478f5bc7b8155cf0226db13c86ccf40e0e476e23d5`  
		Last Modified: Sun, 29 Apr 2018 19:33:59 GMT  
		Size: 10.2 MB (10168983 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:860996a55f7fba99ae60e7be5fc25d885d982031d74467b9bcfc84f96e72def6`  
		Last Modified: Sun, 29 Apr 2018 19:33:57 GMT  
		Size: 205.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0af7e9644f308307bcbf19ad9eea243ce5dd469c0211039f47b3120cabdfc99c`  
		Last Modified: Thu, 24 May 2018 02:02:57 GMT  
		Size: 21.3 MB (21305911 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3c2741f1d4c75227c788ea0d4f97b9d842c26908b326b7341255dc08df8c2ff0`  
		Last Modified: Thu, 24 May 2018 21:16:41 GMT  
		Size: 149.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:085bf055e4f7fca4100b86db549ca65dbd113d5633f293b7d60c64580e40fc9c`  
		Last Modified: Fri, 25 May 2018 22:53:00 GMT  
		Size: 2.1 KB (2100 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:02757c5b4f758477ace554b047238004f1ba80dd0253f13e4afde2cff60c8fe2`  
		Last Modified: Fri, 25 May 2018 22:53:02 GMT  
		Size: 13.0 MB (12967769 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0b812d52f0b76913f780e051066b0aec46d9f1a2bc758a19b4872c304bf83525`  
		Last Modified: Fri, 25 May 2018 22:52:57 GMT  
		Size: 500.7 KB (500671 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a1ee2b52aad93348e461129e48f8cb4e4cbc9418e7363ce6ed71b679ed0da25e`  
		Last Modified: Fri, 25 May 2018 22:52:58 GMT  
		Size: 8.5 KB (8506 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:50ec0628480d6092f4ac1c09226941258eaa856ae2b192f54b82351b8147c5a2`  
		Last Modified: Wed, 20 Jun 2018 21:49:29 GMT  
		Size: 59.7 MB (59702353 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d7d52a5fdbb89bea397274ff00985194056ee68db884b686daa2e63575fa3730`  
		Last Modified: Wed, 20 Jun 2018 21:49:09 GMT  
		Size: 140.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:079a05a37d0bc8ec6e3819f8806a9ff391a4c3ff38e3c35679acabccd7281ed1`  
		Last Modified: Wed, 20 Jun 2018 21:49:11 GMT  
		Size: 2.5 MB (2456917 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:828f67b9c47148252d063a4e719ca8ed0be6c8a2487a5ac84f2bade3fd5e83ae`  
		Last Modified: Wed, 20 Jun 2018 21:49:35 GMT  
		Size: 89.3 MB (89291037 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d4660d39964eb0750734643da738a9352ccb35da2e28172ac5340f00f0cd40ea`  
		Last Modified: Wed, 20 Jun 2018 21:49:09 GMT  
		Size: 1.8 KB (1791 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a168cd64a8c99d11fc203758e12bebe2466c268badacf8a6cf6811c7fde7571e`  
		Last Modified: Wed, 20 Jun 2018 21:50:28 GMT  
		Size: 18.8 MB (18769103 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:adbd7bcd3736ab47fc3557c2ed59316963d6f4bab6f367c31609cbd34f1ce46c`  
		Last Modified: Wed, 20 Jun 2018 21:50:24 GMT  
		Size: 4.5 MB (4484751 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
