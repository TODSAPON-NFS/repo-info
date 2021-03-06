<!-- THIS FILE IS GENERATED VIA './update-remote.sh' -->

# Tags of `orientdb`

-	[`orientdb:2.0.18`](#orientdb2018)
-	[`orientdb:2.1.25`](#orientdb2125)
-	[`orientdb:2.2.35`](#orientdb2235)
-	[`orientdb:2.2.35-spatial`](#orientdb2235-spatial)
-	[`orientdb:3.0.2`](#orientdb302)
-	[`orientdb:3.0.2-tp3`](#orientdb302-tp3)
-	[`orientdb:latest`](#orientdblatest)

## `orientdb:2.0.18`

```console
$ docker pull orientdb@sha256:55c0f3fa576a90dcfe12b7ec22fef4bd2b59c4c2606e74bce93d7b1f707689a2
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `orientdb:2.0.18` - linux; amd64

```console
$ docker pull orientdb@sha256:26617424ab8b8f2510b5253e9a50291d891a1ac80c0359979ec1332389a4e298
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **292.2 MB (292214555 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:54a5b1d719725170d35dbae5eb0962f4c1c0ee0a955d9e4881552f6c99c505d4`
-	Default Command: `["server.sh"]`

```dockerfile
# Sat, 28 Apr 2018 07:08:53 GMT
ADD file:9572fdb59dfbb9b032f3331bbc2a08b31e0aef5fbde44c8f2008d22bf5290cf2 in / 
# Sat, 28 Apr 2018 07:08:53 GMT
CMD ["bash"]
# Tue, 05 Jun 2018 23:13:29 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 05 Jun 2018 23:13:38 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Tue, 05 Jun 2018 23:14:11 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
# Wed, 06 Jun 2018 18:43:16 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Wed, 06 Jun 2018 18:43:16 GMT
ENV LANG=C.UTF-8
# Wed, 06 Jun 2018 18:43:17 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Wed, 06 Jun 2018 18:43:18 GMT
RUN ln -svT "/usr/lib/jvm/java-8-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Wed, 06 Jun 2018 18:43:18 GMT
ENV JAVA_HOME=/docker-java-home
# Wed, 06 Jun 2018 18:43:19 GMT
ENV JAVA_VERSION=8u171
# Wed, 06 Jun 2018 18:43:19 GMT
ENV JAVA_DEBIAN_VERSION=8u171-b11-1~deb9u1
# Wed, 06 Jun 2018 18:43:19 GMT
ENV CA_CERTIFICATES_JAVA_VERSION=20170531+nmu1
# Wed, 06 Jun 2018 18:44:10 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-8-jdk="$JAVA_DEBIAN_VERSION" 		ca-certificates-java="$CA_CERTIFICATES_JAVA_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Wed, 06 Jun 2018 18:44:12 GMT
RUN /var/lib/dpkg/info/ca-certificates-java.postinst configure
# Tue, 12 Jun 2018 02:02:28 GMT
MAINTAINER OrientDB LTD (info@orientdb.com)
# Tue, 12 Jun 2018 02:02:29 GMT
ENV ORIENTDB_VERSION=2.0.18
# Tue, 12 Jun 2018 02:02:29 GMT
ENV ORIENTDB_DOWNLOAD_MD5=9e7b7e7b6d95795b188adb4e5898a1b8
# Tue, 12 Jun 2018 02:02:29 GMT
ENV ORIENTDB_DOWNLOAD_SHA1=f562794536bbf8ae2145f96153e58b1e5d9211b3
# Tue, 12 Jun 2018 02:02:34 GMT
RUN mkdir /orientdb &&   wget  "http://central.maven.org/maven2/com/orientechnologies/orientdb-community/$ORIENTDB_VERSION/orientdb-community-$ORIENTDB_VERSION.tar.gz"   && echo "$ORIENTDB_DOWNLOAD_MD5 *orientdb-community-$ORIENTDB_VERSION.tar.gz" | md5sum -c -   && echo "$ORIENTDB_DOWNLOAD_SHA1 *orientdb-community-$ORIENTDB_VERSION.tar.gz" | sha1sum -c -   && tar -xvzf orientdb-community-$ORIENTDB_VERSION.tar.gz -C /orientdb --strip-components=1  && rm orientdb-community-$ORIENTDB_VERSION.tar.gz   && rm -rf /orientdb/databases/*
# Tue, 12 Jun 2018 02:02:34 GMT
ENV PATH=/orientdb/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Tue, 12 Jun 2018 02:02:34 GMT
VOLUME [/orientdb/backup /orientdb/databases /orientdb/config]
# Tue, 12 Jun 2018 02:02:35 GMT
WORKDIR /orientdb
# Tue, 12 Jun 2018 02:02:35 GMT
EXPOSE 2424/tcp
# Tue, 12 Jun 2018 02:02:36 GMT
EXPOSE 2480/tcp
# Tue, 12 Jun 2018 02:02:36 GMT
CMD ["server.sh"]
```

-	Layers:
	-	`sha256:cc1a78bfd46becbfc3abb8a74d9a70a0e0dc7a5809bbd12e814f9382db003707`  
		Last Modified: Sat, 28 Apr 2018 09:27:54 GMT  
		Size: 45.3 MB (45318159 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d2c05365ee2a2245bb9f6786bc88aa12bf64da676a52668424437826d0f0cb92`  
		Last Modified: Tue, 05 Jun 2018 23:41:58 GMT  
		Size: 10.8 MB (10774184 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:231cb0e216d30ea48044d44d37fba016eb67eca9b19b29a741d95775359d3533`  
		Last Modified: Tue, 05 Jun 2018 23:41:55 GMT  
		Size: 4.3 MB (4335886 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3d2aa70286b89febc36370098220c9b2960cc67c03375c9df4e82736519f1e8a`  
		Last Modified: Tue, 05 Jun 2018 23:42:32 GMT  
		Size: 50.1 MB (50063911 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b621e52d9d658893f0e51550b5414c10829793b963124ae9647e49969a509376`  
		Last Modified: Wed, 06 Jun 2018 19:03:02 GMT  
		Size: 892.5 KB (892549 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f12314f6054acb6b912887bf6ed9d0054a73412f73a3dc0213241d1ca4adc2dd`  
		Last Modified: Wed, 06 Jun 2018 19:03:02 GMT  
		Size: 249.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f5ce6397976f9916f45826968371d80d8894dce238e7afb4e775a962f6cf0632`  
		Last Modified: Wed, 06 Jun 2018 19:03:01 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:965859e0769be99cf2b18ab5a6eab78a7fb01f4006922dfa976f5d90b1d54834`  
		Last Modified: Wed, 06 Jun 2018 19:03:32 GMT  
		Size: 134.0 MB (133970784 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4a76f2995e397f8236214496eb67842f821cf592228e3c46504ed3273de9f9d0`  
		Last Modified: Wed, 06 Jun 2018 19:03:02 GMT  
		Size: 272.1 KB (272133 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:873ba5d6223feff1b13a367de1542885e0faac063e1b269acca168b620b79735`  
		Last Modified: Tue, 12 Jun 2018 02:02:56 GMT  
		Size: 46.6 MB (46586569 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `orientdb:2.1.25`

```console
$ docker pull orientdb@sha256:04599bc97127f2b647d1e7bf83fa22fd346c47f513391cc8abbb868faa05b36b
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `orientdb:2.1.25` - linux; amd64

```console
$ docker pull orientdb@sha256:98b82d9cc45b0b91e5a32d611463682a0f6fc978b1c60c3b16dca0020917b394
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **103.7 MB (103740692 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:04888c6e57f2172e3253d85e9f406580ff45abc2a216b096fd052f8be7651599`
-	Default Command: `["server.sh"]`

```dockerfile
# Tue, 09 Jan 2018 21:10:58 GMT
ADD file:093f0723fa46f6cdbd6f7bd146448bb70ecce54254c35701feeceb956414622f in / 
# Tue, 09 Jan 2018 21:10:58 GMT
CMD ["/bin/sh"]
# Wed, 06 Jun 2018 01:55:39 GMT
ENV LANG=C.UTF-8
# Wed, 06 Jun 2018 01:55:40 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Wed, 06 Jun 2018 01:57:39 GMT
ENV JAVA_HOME=/usr/lib/jvm/java-1.8-openjdk
# Wed, 06 Jun 2018 01:57:39 GMT
ENV PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/lib/jvm/java-1.8-openjdk/jre/bin:/usr/lib/jvm/java-1.8-openjdk/bin
# Sat, 16 Jun 2018 07:22:40 GMT
ENV JAVA_VERSION=8u171
# Sat, 16 Jun 2018 07:22:40 GMT
ENV JAVA_ALPINE_VERSION=8.171.11-r0
# Sat, 16 Jun 2018 07:22:49 GMT
RUN set -x 	&& apk add --no-cache 		openjdk8="$JAVA_ALPINE_VERSION" 	&& [ "$JAVA_HOME" = "$(docker-java-home)" ]
# Sat, 16 Jun 2018 09:31:01 GMT
MAINTAINER OrientDB LTD (info@orientdb.com)
# Sat, 16 Jun 2018 09:31:01 GMT
ENV ORIENTDB_VERSION=2.1.25
# Sat, 16 Jun 2018 09:31:01 GMT
ENV ORIENTDB_DOWNLOAD_MD5=054da3fb7c56e7822b2af116966576ce
# Sat, 16 Jun 2018 09:31:02 GMT
ENV ORIENTDB_DOWNLOAD_SHA1=b7b08242b40117ac8eb9a201f8704bde839dfcb8
# Sat, 16 Jun 2018 09:31:03 GMT
RUN apk add --update tar     && rm -rf /var/cache/apk/*
# Sat, 16 Jun 2018 09:31:11 GMT
RUN mkdir /orientdb &&   wget  "http://central.maven.org/maven2/com/orientechnologies/orientdb-community/$ORIENTDB_VERSION/orientdb-community-$ORIENTDB_VERSION.tar.gz"   && echo "$ORIENTDB_DOWNLOAD_MD5 *orientdb-community-$ORIENTDB_VERSION.tar.gz" | md5sum -c -   && echo "$ORIENTDB_DOWNLOAD_SHA1 *orientdb-community-$ORIENTDB_VERSION.tar.gz" | sha1sum -c -   && tar -xvzf orientdb-community-$ORIENTDB_VERSION.tar.gz -C /orientdb --strip-components=1  && rm orientdb-community-$ORIENTDB_VERSION.tar.gz   && rm -rf /orientdb/databases/*
# Sat, 16 Jun 2018 09:31:11 GMT
ENV PATH=/orientdb/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/lib/jvm/java-1.8-openjdk/jre/bin:/usr/lib/jvm/java-1.8-openjdk/bin
# Sat, 16 Jun 2018 09:31:12 GMT
VOLUME [/orientdb/backup /orientdb/databases /orientdb/config]
# Sat, 16 Jun 2018 09:31:12 GMT
WORKDIR /orientdb
# Sat, 16 Jun 2018 09:31:12 GMT
EXPOSE 2424/tcp
# Sat, 16 Jun 2018 09:31:12 GMT
EXPOSE 2480/tcp
# Sat, 16 Jun 2018 09:31:13 GMT
CMD ["server.sh"]
```

-	Layers:
	-	`sha256:ff3a5c916c92643ff77519ffa742d3ec61b7f591b6b7504599d95a4a41134e28`  
		Last Modified: Tue, 09 Jan 2018 21:13:34 GMT  
		Size: 2.1 MB (2065537 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a8906544047d741c82ab8e4f6b3a698cdc37170b9afe8006a7c2aee85bc78618`  
		Last Modified: Wed, 06 Jun 2018 02:15:28 GMT  
		Size: 241.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7120596ce621571aded381ea153b8cb4916c306331648b2e6f3d09a93c3967e4`  
		Last Modified: Sat, 16 Jun 2018 07:30:42 GMT  
		Size: 70.3 MB (70318307 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3e1ab9336c8350a78f7acc1ebe64f0535e8cfd4cccdcf624674f27da3b7a9081`  
		Last Modified: Sat, 16 Jun 2018 09:32:32 GMT  
		Size: 268.6 KB (268632 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bde8d439fd9bf609dab14dcd3229a8911789082f3fa623b0eaca69b0b9c5b9d4`  
		Last Modified: Sat, 16 Jun 2018 09:32:41 GMT  
		Size: 31.1 MB (31087975 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `orientdb:2.2.35`

```console
$ docker pull orientdb@sha256:0cdf4beedd1e4ee8aa596c7ccd84c693368e8fc255c81286e55375b4ce9ca703
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `orientdb:2.2.35` - linux; amd64

```console
$ docker pull orientdb@sha256:e9e02190b948d0c2314c4a516a47c68658886c15e23c639e4c9ae92e4257b66a
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **119.5 MB (119529470 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:f7f495635d493af87b1ed6be6ded12d6c1948ce93364f7cbddd40e10494d3c17`
-	Default Command: `["server.sh"]`

```dockerfile
# Tue, 09 Jan 2018 21:10:58 GMT
ADD file:093f0723fa46f6cdbd6f7bd146448bb70ecce54254c35701feeceb956414622f in / 
# Tue, 09 Jan 2018 21:10:58 GMT
CMD ["/bin/sh"]
# Wed, 06 Jun 2018 01:55:39 GMT
ENV LANG=C.UTF-8
# Wed, 06 Jun 2018 01:55:40 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Wed, 06 Jun 2018 01:57:39 GMT
ENV JAVA_HOME=/usr/lib/jvm/java-1.8-openjdk
# Wed, 06 Jun 2018 01:57:39 GMT
ENV PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/lib/jvm/java-1.8-openjdk/jre/bin:/usr/lib/jvm/java-1.8-openjdk/bin
# Sat, 16 Jun 2018 07:22:40 GMT
ENV JAVA_VERSION=8u171
# Sat, 16 Jun 2018 07:22:40 GMT
ENV JAVA_ALPINE_VERSION=8.171.11-r0
# Sat, 16 Jun 2018 07:22:49 GMT
RUN set -x 	&& apk add --no-cache 		openjdk8="$JAVA_ALPINE_VERSION" 	&& [ "$JAVA_HOME" = "$(docker-java-home)" ]
# Sat, 16 Jun 2018 09:31:01 GMT
MAINTAINER OrientDB LTD (info@orientdb.com)
# Sat, 16 Jun 2018 09:31:19 GMT
ARG ORIENTDB_DOWNLOAD_SERVER
# Sat, 16 Jun 2018 09:31:20 GMT
ENV ORIENTDB_VERSION=2.2.35
# Sat, 16 Jun 2018 09:31:20 GMT
ENV ORIENTDB_DOWNLOAD_MD5=9cc574028860b85f1b910a3c43e43082
# Sat, 16 Jun 2018 09:31:20 GMT
ENV ORIENTDB_DOWNLOAD_SHA1=e9fca1028228249fa3f81094df2246802e880b52
# Sat, 16 Jun 2018 09:31:20 GMT
ENV ORIENTDB_DOWNLOAD_URL=http://central.maven.org/maven2/com/orientechnologies/orientdb-community/2.2.35/orientdb-community-2.2.35.tar.gz
# Sat, 16 Jun 2018 09:31:21 GMT
RUN apk add --update tar curl     && rm -rf /var/cache/apk/*
# Sat, 16 Jun 2018 09:31:32 GMT
RUN mkdir /orientdb &&   wget  $ORIENTDB_DOWNLOAD_URL   && echo "$ORIENTDB_DOWNLOAD_MD5 *orientdb-community-$ORIENTDB_VERSION.tar.gz" | md5sum -c -   && echo "$ORIENTDB_DOWNLOAD_SHA1 *orientdb-community-$ORIENTDB_VERSION.tar.gz" | sha1sum -c -   && tar -xvzf orientdb-community-$ORIENTDB_VERSION.tar.gz -C /orientdb --strip-components=1   && rm orientdb-community-$ORIENTDB_VERSION.tar.gz   && rm -rf /orientdb/databases/*
# Sat, 16 Jun 2018 09:31:33 GMT
ENV PATH=/orientdb/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/lib/jvm/java-1.8-openjdk/jre/bin:/usr/lib/jvm/java-1.8-openjdk/bin
# Sat, 16 Jun 2018 09:31:33 GMT
VOLUME [/orientdb/backup /orientdb/databases /orientdb/config]
# Sat, 16 Jun 2018 09:31:33 GMT
WORKDIR /orientdb
# Sat, 16 Jun 2018 09:31:33 GMT
EXPOSE 2424/tcp
# Sat, 16 Jun 2018 09:31:34 GMT
EXPOSE 2480/tcp
# Sat, 16 Jun 2018 09:31:34 GMT
CMD ["server.sh"]
```

-	Layers:
	-	`sha256:ff3a5c916c92643ff77519ffa742d3ec61b7f591b6b7504599d95a4a41134e28`  
		Last Modified: Tue, 09 Jan 2018 21:13:34 GMT  
		Size: 2.1 MB (2065537 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a8906544047d741c82ab8e4f6b3a698cdc37170b9afe8006a7c2aee85bc78618`  
		Last Modified: Wed, 06 Jun 2018 02:15:28 GMT  
		Size: 241.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7120596ce621571aded381ea153b8cb4916c306331648b2e6f3d09a93c3967e4`  
		Last Modified: Sat, 16 Jun 2018 07:30:42 GMT  
		Size: 70.3 MB (70318307 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:33ab245225b2a783584498b7db391b22b7b6c1f19354d1c13e84303025fec85f`  
		Last Modified: Sat, 16 Jun 2018 09:32:58 GMT  
		Size: 673.4 KB (673354 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5f26c45b612a514c639a6b3c1d3e84c64598300f1c59610067cfe7748f26084a`  
		Last Modified: Sat, 16 Jun 2018 09:33:12 GMT  
		Size: 46.5 MB (46472031 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `orientdb:2.2.35-spatial`

```console
$ docker pull orientdb@sha256:38a177bf2c23a7e733a801e1a0210e66fd6cd306e02750dea2fbeaa59dc79954
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `orientdb:2.2.35-spatial` - linux; amd64

```console
$ docker pull orientdb@sha256:7c834dc3b7e3ec417e239fd0b5427c679e09e909d43e5937d936365296197ea9
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **120.7 MB (120731958 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:054814a270bbc276ef928f28f12b6489ab43c5c94ce212eef5f181bcabd5d3f9`
-	Default Command: `["server.sh"]`

```dockerfile
# Tue, 09 Jan 2018 21:10:58 GMT
ADD file:093f0723fa46f6cdbd6f7bd146448bb70ecce54254c35701feeceb956414622f in / 
# Tue, 09 Jan 2018 21:10:58 GMT
CMD ["/bin/sh"]
# Wed, 06 Jun 2018 01:55:39 GMT
ENV LANG=C.UTF-8
# Wed, 06 Jun 2018 01:55:40 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Wed, 06 Jun 2018 01:57:39 GMT
ENV JAVA_HOME=/usr/lib/jvm/java-1.8-openjdk
# Wed, 06 Jun 2018 01:57:39 GMT
ENV PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/lib/jvm/java-1.8-openjdk/jre/bin:/usr/lib/jvm/java-1.8-openjdk/bin
# Sat, 16 Jun 2018 07:22:40 GMT
ENV JAVA_VERSION=8u171
# Sat, 16 Jun 2018 07:22:40 GMT
ENV JAVA_ALPINE_VERSION=8.171.11-r0
# Sat, 16 Jun 2018 07:22:49 GMT
RUN set -x 	&& apk add --no-cache 		openjdk8="$JAVA_ALPINE_VERSION" 	&& [ "$JAVA_HOME" = "$(docker-java-home)" ]
# Sat, 16 Jun 2018 09:31:01 GMT
MAINTAINER OrientDB LTD (info@orientdb.com)
# Sat, 16 Jun 2018 09:31:19 GMT
ARG ORIENTDB_DOWNLOAD_SERVER
# Sat, 16 Jun 2018 09:31:20 GMT
ENV ORIENTDB_VERSION=2.2.35
# Sat, 16 Jun 2018 09:31:20 GMT
ENV ORIENTDB_DOWNLOAD_MD5=9cc574028860b85f1b910a3c43e43082
# Sat, 16 Jun 2018 09:31:20 GMT
ENV ORIENTDB_DOWNLOAD_SHA1=e9fca1028228249fa3f81094df2246802e880b52
# Sat, 16 Jun 2018 09:31:20 GMT
ENV ORIENTDB_DOWNLOAD_URL=http://central.maven.org/maven2/com/orientechnologies/orientdb-community/2.2.35/orientdb-community-2.2.35.tar.gz
# Sat, 16 Jun 2018 09:31:21 GMT
RUN apk add --update tar curl     && rm -rf /var/cache/apk/*
# Sat, 16 Jun 2018 09:31:32 GMT
RUN mkdir /orientdb &&   wget  $ORIENTDB_DOWNLOAD_URL   && echo "$ORIENTDB_DOWNLOAD_MD5 *orientdb-community-$ORIENTDB_VERSION.tar.gz" | md5sum -c -   && echo "$ORIENTDB_DOWNLOAD_SHA1 *orientdb-community-$ORIENTDB_VERSION.tar.gz" | sha1sum -c -   && tar -xvzf orientdb-community-$ORIENTDB_VERSION.tar.gz -C /orientdb --strip-components=1   && rm orientdb-community-$ORIENTDB_VERSION.tar.gz   && rm -rf /orientdb/databases/*
# Sat, 16 Jun 2018 09:31:33 GMT
ENV PATH=/orientdb/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/lib/jvm/java-1.8-openjdk/jre/bin:/usr/lib/jvm/java-1.8-openjdk/bin
# Sat, 16 Jun 2018 09:31:33 GMT
VOLUME [/orientdb/backup /orientdb/databases /orientdb/config]
# Sat, 16 Jun 2018 09:31:33 GMT
WORKDIR /orientdb
# Sat, 16 Jun 2018 09:31:33 GMT
EXPOSE 2424/tcp
# Sat, 16 Jun 2018 09:31:34 GMT
EXPOSE 2480/tcp
# Sat, 16 Jun 2018 09:31:34 GMT
CMD ["server.sh"]
# Sat, 16 Jun 2018 09:31:41 GMT
ENV ORIENTDB_DOWNLOAD_SPATIAL_MD5=d434e07628a1897f69bc348b7a214b0a
# Sat, 16 Jun 2018 09:31:41 GMT
ENV ORIENTDB_DOWNLOAD_SPATIAL_SHA1=eb37f21c3aa7b718a36a32963ef38fba0bb7b8d3
# Sat, 16 Jun 2018 09:31:41 GMT
ENV ORIENTDB_DOWNLOAD_SPATIAL_URL=http://central.maven.org/maven2/com/orientechnologies/orientdb-spatial/2.2.35/orientdb-spatial-2.2.35-dist.jar
# Sat, 16 Jun 2018 09:31:42 GMT
RUN wget $ORIENTDB_DOWNLOAD_SPATIAL_URL     && echo "$ORIENTDB_DOWNLOAD_SPATIAL_MD5 *orientdb-spatial-$ORIENTDB_VERSION-dist.jar" | md5sum -c -     && echo "$ORIENTDB_DOWNLOAD_SPATIAL_SHA1 *orientdb-spatial-$ORIENTDB_VERSION-dist.jar" | sha1sum -c -     && mv orientdb-spatial-*-dist.jar /orientdb/lib/
```

-	Layers:
	-	`sha256:ff3a5c916c92643ff77519ffa742d3ec61b7f591b6b7504599d95a4a41134e28`  
		Last Modified: Tue, 09 Jan 2018 21:13:34 GMT  
		Size: 2.1 MB (2065537 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a8906544047d741c82ab8e4f6b3a698cdc37170b9afe8006a7c2aee85bc78618`  
		Last Modified: Wed, 06 Jun 2018 02:15:28 GMT  
		Size: 241.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7120596ce621571aded381ea153b8cb4916c306331648b2e6f3d09a93c3967e4`  
		Last Modified: Sat, 16 Jun 2018 07:30:42 GMT  
		Size: 70.3 MB (70318307 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:33ab245225b2a783584498b7db391b22b7b6c1f19354d1c13e84303025fec85f`  
		Last Modified: Sat, 16 Jun 2018 09:32:58 GMT  
		Size: 673.4 KB (673354 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5f26c45b612a514c639a6b3c1d3e84c64598300f1c59610067cfe7748f26084a`  
		Last Modified: Sat, 16 Jun 2018 09:33:12 GMT  
		Size: 46.5 MB (46472031 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:64fd8ed51029228b71a20eecc332e652c27d5c2274c34e74828823516a7c562a`  
		Last Modified: Sat, 16 Jun 2018 09:33:26 GMT  
		Size: 1.2 MB (1202488 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `orientdb:3.0.2`

```console
$ docker pull orientdb@sha256:8fe8c5d0930f92c51f701eb138a7181ce50dbc169ff9a54af1a2881a015b05e2
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `orientdb:3.0.2` - linux; amd64

```console
$ docker pull orientdb@sha256:b9cb21aefe78ddfced5692128663d64524a388ac244490133ad755480b6a158f
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **109.1 MB (109144626 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:52f7fac38da5eee4502235d35e7c9a7027924a430436c1155e047f6fd726c64d`
-	Default Command: `["server.sh"]`

```dockerfile
# Tue, 09 Jan 2018 21:10:58 GMT
ADD file:093f0723fa46f6cdbd6f7bd146448bb70ecce54254c35701feeceb956414622f in / 
# Tue, 09 Jan 2018 21:10:58 GMT
CMD ["/bin/sh"]
# Wed, 06 Jun 2018 01:55:39 GMT
ENV LANG=C.UTF-8
# Wed, 06 Jun 2018 01:55:40 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Wed, 06 Jun 2018 01:57:39 GMT
ENV JAVA_HOME=/usr/lib/jvm/java-1.8-openjdk
# Wed, 06 Jun 2018 01:57:39 GMT
ENV PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/lib/jvm/java-1.8-openjdk/jre/bin:/usr/lib/jvm/java-1.8-openjdk/bin
# Sat, 16 Jun 2018 07:22:40 GMT
ENV JAVA_VERSION=8u171
# Sat, 16 Jun 2018 07:22:40 GMT
ENV JAVA_ALPINE_VERSION=8.171.11-r0
# Sat, 16 Jun 2018 07:22:49 GMT
RUN set -x 	&& apk add --no-cache 		openjdk8="$JAVA_ALPINE_VERSION" 	&& [ "$JAVA_HOME" = "$(docker-java-home)" ]
# Sat, 16 Jun 2018 09:31:01 GMT
MAINTAINER OrientDB LTD (info@orientdb.com)
# Sat, 16 Jun 2018 09:31:19 GMT
ARG ORIENTDB_DOWNLOAD_SERVER
# Wed, 20 Jun 2018 17:20:00 GMT
ENV ORIENTDB_VERSION=3.0.2
# Wed, 20 Jun 2018 17:20:00 GMT
ENV ORIENTDB_DOWNLOAD_MD5=145e4836a3066783f0d2545af17b9e56
# Wed, 20 Jun 2018 17:20:01 GMT
ENV ORIENTDB_DOWNLOAD_SHA1=9aae978d9943af6e82fb4707519239e60054f652
# Wed, 20 Jun 2018 17:20:01 GMT
ENV ORIENTDB_DOWNLOAD_URL=http://central.maven.org/maven2/com/orientechnologies/orientdb-community/3.0.2/orientdb-community-3.0.2.tar.gz
# Wed, 20 Jun 2018 17:20:02 GMT
RUN apk add --update tar curl     && rm -rf /var/cache/apk/*
# Wed, 20 Jun 2018 17:20:09 GMT
RUN mkdir /orientdb &&   wget  $ORIENTDB_DOWNLOAD_URL   && echo "$ORIENTDB_DOWNLOAD_MD5 *orientdb-community-$ORIENTDB_VERSION.tar.gz" | md5sum -c -   && echo "$ORIENTDB_DOWNLOAD_SHA1 *orientdb-community-$ORIENTDB_VERSION.tar.gz" | sha1sum -c -   && tar -xvzf orientdb-community-$ORIENTDB_VERSION.tar.gz -C /orientdb --strip-components=1   && rm orientdb-community-$ORIENTDB_VERSION.tar.gz   && rm -rf /orientdb/databases/*
# Wed, 20 Jun 2018 17:20:09 GMT
ENV PATH=/orientdb/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/lib/jvm/java-1.8-openjdk/jre/bin:/usr/lib/jvm/java-1.8-openjdk/bin
# Wed, 20 Jun 2018 17:20:09 GMT
VOLUME [/orientdb/backup /orientdb/databases /orientdb/config]
# Wed, 20 Jun 2018 17:20:09 GMT
WORKDIR /orientdb
# Wed, 20 Jun 2018 17:20:10 GMT
EXPOSE 2424/tcp
# Wed, 20 Jun 2018 17:20:10 GMT
EXPOSE 2480/tcp
# Wed, 20 Jun 2018 17:20:10 GMT
CMD ["server.sh"]
```

-	Layers:
	-	`sha256:ff3a5c916c92643ff77519ffa742d3ec61b7f591b6b7504599d95a4a41134e28`  
		Last Modified: Tue, 09 Jan 2018 21:13:34 GMT  
		Size: 2.1 MB (2065537 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a8906544047d741c82ab8e4f6b3a698cdc37170b9afe8006a7c2aee85bc78618`  
		Last Modified: Wed, 06 Jun 2018 02:15:28 GMT  
		Size: 241.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7120596ce621571aded381ea153b8cb4916c306331648b2e6f3d09a93c3967e4`  
		Last Modified: Sat, 16 Jun 2018 07:30:42 GMT  
		Size: 70.3 MB (70318307 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:df97a4277ba1e4161b5a79ee6bd927e8213417fc8eb2ffabbdf10bb5a3a4d1f4`  
		Last Modified: Wed, 20 Jun 2018 17:20:47 GMT  
		Size: 673.4 KB (673353 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4487821890798b332d5c00c7db56219e20f3a903f78e35fdb775bf8842c0ddeb`  
		Last Modified: Wed, 20 Jun 2018 17:20:57 GMT  
		Size: 36.1 MB (36087188 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `orientdb:3.0.2-tp3`

```console
$ docker pull orientdb@sha256:0efe3c6ea541535d56a24d2ee460163f56b173b0b8fee674a8b68012d9c7533d
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `orientdb:3.0.2-tp3` - linux; amd64

```console
$ docker pull orientdb@sha256:d4be266534d9e874083f2f6afab45353dd3900bce69d57174f6c1f80bb3fbd8c
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **136.4 MB (136423470 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:888fe756afe6c60bd26eec34f231060e4a4a4d5b0219b4f8b4adf83f55e31066`
-	Default Command: `["server.sh"]`

```dockerfile
# Tue, 09 Jan 2018 21:10:58 GMT
ADD file:093f0723fa46f6cdbd6f7bd146448bb70ecce54254c35701feeceb956414622f in / 
# Tue, 09 Jan 2018 21:10:58 GMT
CMD ["/bin/sh"]
# Wed, 06 Jun 2018 01:55:39 GMT
ENV LANG=C.UTF-8
# Wed, 06 Jun 2018 01:55:40 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Wed, 06 Jun 2018 01:57:39 GMT
ENV JAVA_HOME=/usr/lib/jvm/java-1.8-openjdk
# Wed, 06 Jun 2018 01:57:39 GMT
ENV PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/lib/jvm/java-1.8-openjdk/jre/bin:/usr/lib/jvm/java-1.8-openjdk/bin
# Sat, 16 Jun 2018 07:22:40 GMT
ENV JAVA_VERSION=8u171
# Sat, 16 Jun 2018 07:22:40 GMT
ENV JAVA_ALPINE_VERSION=8.171.11-r0
# Sat, 16 Jun 2018 07:22:49 GMT
RUN set -x 	&& apk add --no-cache 		openjdk8="$JAVA_ALPINE_VERSION" 	&& [ "$JAVA_HOME" = "$(docker-java-home)" ]
# Sat, 16 Jun 2018 09:31:01 GMT
MAINTAINER OrientDB LTD (info@orientdb.com)
# Sat, 16 Jun 2018 09:31:19 GMT
ARG ORIENTDB_DOWNLOAD_SERVER
# Wed, 20 Jun 2018 17:20:00 GMT
ENV ORIENTDB_VERSION=3.0.2
# Wed, 20 Jun 2018 17:20:18 GMT
ENV ORIENTDB_DOWNLOAD_MD5=7983a5be80ff1418e5290ad72fe7f6f3
# Wed, 20 Jun 2018 17:20:18 GMT
ENV ORIENTDB_DOWNLOAD_SHA1=086445a6bed081cec1162931a87bdfad39f11c38
# Wed, 20 Jun 2018 17:20:18 GMT
ENV ORIENTDB_DOWNLOAD_URL=http://central.maven.org/maven2/com/orientechnologies/orientdb-tp3/3.0.2/orientdb-tp3-3.0.2.tar.gz
# Wed, 20 Jun 2018 17:20:19 GMT
RUN apk add --update tar curl     && rm -rf /var/cache/apk/*
# Wed, 20 Jun 2018 17:20:30 GMT
RUN mkdir /orientdb &&   wget  $ORIENTDB_DOWNLOAD_URL   && echo "$ORIENTDB_DOWNLOAD_MD5 *orientdb-tp3-$ORIENTDB_VERSION.tar.gz" | md5sum -c -   && echo "$ORIENTDB_DOWNLOAD_SHA1 *orientdb-tp3-$ORIENTDB_VERSION.tar.gz" | sha1sum -c -   && tar -xvzf orientdb-tp3-$ORIENTDB_VERSION.tar.gz -C /orientdb --strip-components=1   && rm orientdb-tp3-$ORIENTDB_VERSION.tar.gz   && rm -rf /orientdb/databases/*
# Wed, 20 Jun 2018 17:20:31 GMT
ADD file:99b7a1625594810d4a6ad850d8e45ce20c6e5e95127b6a7316cae65e7aa03c13 in /orientdb/config 
# Wed, 20 Jun 2018 17:20:31 GMT
ENV PATH=/orientdb/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/lib/jvm/java-1.8-openjdk/jre/bin:/usr/lib/jvm/java-1.8-openjdk/bin
# Wed, 20 Jun 2018 17:20:31 GMT
VOLUME [/orientdb/backup /orientdb/databases /orientdb/config]
# Wed, 20 Jun 2018 17:20:32 GMT
WORKDIR /orientdb
# Wed, 20 Jun 2018 17:20:32 GMT
EXPOSE 2424/tcp
# Wed, 20 Jun 2018 17:20:32 GMT
EXPOSE 2480/tcp
# Wed, 20 Jun 2018 17:20:33 GMT
CMD ["server.sh"]
```

-	Layers:
	-	`sha256:ff3a5c916c92643ff77519ffa742d3ec61b7f591b6b7504599d95a4a41134e28`  
		Last Modified: Tue, 09 Jan 2018 21:13:34 GMT  
		Size: 2.1 MB (2065537 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a8906544047d741c82ab8e4f6b3a698cdc37170b9afe8006a7c2aee85bc78618`  
		Last Modified: Wed, 06 Jun 2018 02:15:28 GMT  
		Size: 241.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7120596ce621571aded381ea153b8cb4916c306331648b2e6f3d09a93c3967e4`  
		Last Modified: Sat, 16 Jun 2018 07:30:42 GMT  
		Size: 70.3 MB (70318307 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3399509e1c129e6c3a9f07c2ff2016659999f783323a55809c53fbb66c85ad4c`  
		Last Modified: Wed, 20 Jun 2018 17:21:19 GMT  
		Size: 673.4 KB (673356 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7f12d01024f3f92eb4c2cd0bc6bcedd941ae112e0e8e2db9ff2edc3b97bd8261`  
		Last Modified: Wed, 20 Jun 2018 17:21:35 GMT  
		Size: 63.4 MB (63364652 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b54e03e96e866c557696a5f10961e51a68fba3de1fd8069a001d04269488bfbf`  
		Last Modified: Wed, 20 Jun 2018 17:21:18 GMT  
		Size: 1.4 KB (1377 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `orientdb:latest`

```console
$ docker pull orientdb@sha256:8fe8c5d0930f92c51f701eb138a7181ce50dbc169ff9a54af1a2881a015b05e2
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `orientdb:latest` - linux; amd64

```console
$ docker pull orientdb@sha256:b9cb21aefe78ddfced5692128663d64524a388ac244490133ad755480b6a158f
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **109.1 MB (109144626 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:52f7fac38da5eee4502235d35e7c9a7027924a430436c1155e047f6fd726c64d`
-	Default Command: `["server.sh"]`

```dockerfile
# Tue, 09 Jan 2018 21:10:58 GMT
ADD file:093f0723fa46f6cdbd6f7bd146448bb70ecce54254c35701feeceb956414622f in / 
# Tue, 09 Jan 2018 21:10:58 GMT
CMD ["/bin/sh"]
# Wed, 06 Jun 2018 01:55:39 GMT
ENV LANG=C.UTF-8
# Wed, 06 Jun 2018 01:55:40 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Wed, 06 Jun 2018 01:57:39 GMT
ENV JAVA_HOME=/usr/lib/jvm/java-1.8-openjdk
# Wed, 06 Jun 2018 01:57:39 GMT
ENV PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/lib/jvm/java-1.8-openjdk/jre/bin:/usr/lib/jvm/java-1.8-openjdk/bin
# Sat, 16 Jun 2018 07:22:40 GMT
ENV JAVA_VERSION=8u171
# Sat, 16 Jun 2018 07:22:40 GMT
ENV JAVA_ALPINE_VERSION=8.171.11-r0
# Sat, 16 Jun 2018 07:22:49 GMT
RUN set -x 	&& apk add --no-cache 		openjdk8="$JAVA_ALPINE_VERSION" 	&& [ "$JAVA_HOME" = "$(docker-java-home)" ]
# Sat, 16 Jun 2018 09:31:01 GMT
MAINTAINER OrientDB LTD (info@orientdb.com)
# Sat, 16 Jun 2018 09:31:19 GMT
ARG ORIENTDB_DOWNLOAD_SERVER
# Wed, 20 Jun 2018 17:20:00 GMT
ENV ORIENTDB_VERSION=3.0.2
# Wed, 20 Jun 2018 17:20:00 GMT
ENV ORIENTDB_DOWNLOAD_MD5=145e4836a3066783f0d2545af17b9e56
# Wed, 20 Jun 2018 17:20:01 GMT
ENV ORIENTDB_DOWNLOAD_SHA1=9aae978d9943af6e82fb4707519239e60054f652
# Wed, 20 Jun 2018 17:20:01 GMT
ENV ORIENTDB_DOWNLOAD_URL=http://central.maven.org/maven2/com/orientechnologies/orientdb-community/3.0.2/orientdb-community-3.0.2.tar.gz
# Wed, 20 Jun 2018 17:20:02 GMT
RUN apk add --update tar curl     && rm -rf /var/cache/apk/*
# Wed, 20 Jun 2018 17:20:09 GMT
RUN mkdir /orientdb &&   wget  $ORIENTDB_DOWNLOAD_URL   && echo "$ORIENTDB_DOWNLOAD_MD5 *orientdb-community-$ORIENTDB_VERSION.tar.gz" | md5sum -c -   && echo "$ORIENTDB_DOWNLOAD_SHA1 *orientdb-community-$ORIENTDB_VERSION.tar.gz" | sha1sum -c -   && tar -xvzf orientdb-community-$ORIENTDB_VERSION.tar.gz -C /orientdb --strip-components=1   && rm orientdb-community-$ORIENTDB_VERSION.tar.gz   && rm -rf /orientdb/databases/*
# Wed, 20 Jun 2018 17:20:09 GMT
ENV PATH=/orientdb/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/lib/jvm/java-1.8-openjdk/jre/bin:/usr/lib/jvm/java-1.8-openjdk/bin
# Wed, 20 Jun 2018 17:20:09 GMT
VOLUME [/orientdb/backup /orientdb/databases /orientdb/config]
# Wed, 20 Jun 2018 17:20:09 GMT
WORKDIR /orientdb
# Wed, 20 Jun 2018 17:20:10 GMT
EXPOSE 2424/tcp
# Wed, 20 Jun 2018 17:20:10 GMT
EXPOSE 2480/tcp
# Wed, 20 Jun 2018 17:20:10 GMT
CMD ["server.sh"]
```

-	Layers:
	-	`sha256:ff3a5c916c92643ff77519ffa742d3ec61b7f591b6b7504599d95a4a41134e28`  
		Last Modified: Tue, 09 Jan 2018 21:13:34 GMT  
		Size: 2.1 MB (2065537 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a8906544047d741c82ab8e4f6b3a698cdc37170b9afe8006a7c2aee85bc78618`  
		Last Modified: Wed, 06 Jun 2018 02:15:28 GMT  
		Size: 241.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7120596ce621571aded381ea153b8cb4916c306331648b2e6f3d09a93c3967e4`  
		Last Modified: Sat, 16 Jun 2018 07:30:42 GMT  
		Size: 70.3 MB (70318307 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:df97a4277ba1e4161b5a79ee6bd927e8213417fc8eb2ffabbdf10bb5a3a4d1f4`  
		Last Modified: Wed, 20 Jun 2018 17:20:47 GMT  
		Size: 673.4 KB (673353 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4487821890798b332d5c00c7db56219e20f3a903f78e35fdb775bf8842c0ddeb`  
		Last Modified: Wed, 20 Jun 2018 17:20:57 GMT  
		Size: 36.1 MB (36087188 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
