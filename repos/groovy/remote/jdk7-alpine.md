## `groovy:jdk7-alpine`

```console
$ docker pull groovy@sha256:6ac458f633b5717121b5574855d0d33bc996840272120e9af57647caaac27d17
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm64 variant v8
	-	linux; 386
	-	linux; ppc64le
	-	linux; s390x

### `groovy:jdk7-alpine` - linux; amd64

```console
$ docker pull groovy@sha256:d319b5d758f9a33c1bd4a428d968a6f86157b9a8896de1db30961c89374659e4
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **116.9 MB (116943276 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:97cf9e75426691efead6a06ea4f34baa0243c85d29e75f82774e7ff99c3961a1`
-	Default Command: `["groovysh"]`

```dockerfile
# Tue, 09 Jan 2018 21:10:58 GMT
ADD file:093f0723fa46f6cdbd6f7bd146448bb70ecce54254c35701feeceb956414622f in / 
# Tue, 09 Jan 2018 21:10:58 GMT
CMD ["/bin/sh"]
# Wed, 06 Jun 2018 01:55:39 GMT
ENV LANG=C.UTF-8
# Wed, 06 Jun 2018 01:55:40 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Wed, 06 Jun 2018 02:04:35 GMT
ENV JAVA_HOME=/usr/lib/jvm/java-1.7-openjdk
# Wed, 06 Jun 2018 02:04:36 GMT
ENV PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/lib/jvm/java-1.7-openjdk/jre/bin:/usr/lib/jvm/java-1.7-openjdk/bin
# Wed, 06 Jun 2018 02:04:36 GMT
ENV JAVA_VERSION=7u151
# Wed, 06 Jun 2018 02:04:36 GMT
ENV JAVA_ALPINE_VERSION=7.151.2.6.11-r0
# Wed, 06 Jun 2018 02:04:44 GMT
RUN set -x 	&& apk add --no-cache 		openjdk7="$JAVA_ALPINE_VERSION" 	&& [ "$JAVA_HOME" = "$(docker-java-home)" ]
# Tue, 19 Jun 2018 18:21:12 GMT
CMD ["groovysh"]
# Tue, 19 Jun 2018 18:21:12 GMT
ENV GROOVY_HOME=/opt/groovy
# Tue, 19 Jun 2018 18:21:12 GMT
ENV GROOVY_VERSION=2.4.15
# Tue, 19 Jun 2018 18:21:21 GMT
RUN set -o errexit -o nounset 	&& echo "Installing build dependencies" 	&& apk add --no-cache --virtual .build-deps 		ca-certificates 		gnupg 		openssl 		unzip 		&& echo "Downloading Groovy" 	&& wget -O groovy.zip "https://dist.apache.org/repos/dist/release/groovy/${GROOVY_VERSION}/distribution/apache-groovy-binary-${GROOVY_VERSION}.zip" 		&& echo "Importing keys listed in http://www.apache.org/dist/groovy/KEYS from key server" 	&& export GNUPGHOME="$(mktemp -d)" 	&& for key in 		"7FAA0F2206DE228F0DB01AD741321490758AAD6F" 		"331224E1D7BE883D16E8A685825C06C827AF6B66" 		"34441E504A937F43EB0DAEF96A65176A0FB1CD0B" 		"9A810E3B766E089FFB27C70F11B595CEDC4AEBB5" 		"81CABC23EECA0790E8989B361FF96E10F0E13706" 	; do 		for server in 			"ha.pool.sks-keyservers.net" 			"hkp://p80.pool.sks-keyservers.net:80" 			"pgp.mit.edu" 		; do 			echo "  Trying ${server}"; 			if gpg --keyserver "${server}" --recv-keys "${key}"; then 				break; 			fi; 		done; 	done; 	if [ $(gpg --list-keys | grep -c "pub ") -ne 5 ]; then 		echo "ERROR: Failed to fetch GPG keys" >&2; 		exit 1; 	fi 		&& echo "Checking download signature" 	&& wget -O groovy.zip.asc "https://dist.apache.org/repos/dist/release/groovy/${GROOVY_VERSION}/distribution/apache-groovy-binary-${GROOVY_VERSION}.zip.asc" 	&& gpg --batch --verify groovy.zip.asc groovy.zip 	&& rm -rf "${GNUPGHOME}" 	&& rm groovy.zip.asc 		&& echo "Installing Groovy" 	&& unzip groovy.zip 	&& rm groovy.zip 	&& mkdir /opt 	&& mv "groovy-${GROOVY_VERSION}" "${GROOVY_HOME}/" 	&& ln -s "${GROOVY_HOME}/bin/grape" /usr/bin/grape 	&& ln -s "${GROOVY_HOME}/bin/groovy" /usr/bin/groovy 	&& ln -s "${GROOVY_HOME}/bin/groovyc" /usr/bin/groovyc 	&& ln -s "${GROOVY_HOME}/bin/groovyConsole" /usr/bin/groovyConsole 	&& ln -s "${GROOVY_HOME}/bin/groovydoc" /usr/bin/groovydoc 	&& ln -s "${GROOVY_HOME}/bin/groovysh" /usr/bin/groovysh 	&& ln -s "${GROOVY_HOME}/bin/java2groovy" /usr/bin/java2groovy 		&& echo "Cleaning up build dependencies" 	&& apk del .build-deps 		&& echo "Adding groovy user and group" 	&& addgroup -S -g 1000 groovy 	&& adduser -D -S -G groovy -u 1000 -s /bin/ash groovy 	&& mkdir -p /home/groovy/.groovy/grapes 	&& chown -R groovy:groovy /home/groovy 		&& echo "Symlinking root .groovy to groovy .groovy" 	&& ln -s /home/groovy/.groovy /root/.groovy
# Tue, 19 Jun 2018 18:21:22 GMT
USER [groovy]
# Tue, 19 Jun 2018 18:21:22 GMT
VOLUME [/home/groovy/.groovy/grapes]
# Tue, 19 Jun 2018 18:21:22 GMT
WORKDIR /home/groovy
# Tue, 19 Jun 2018 18:21:25 GMT
RUN set -o errexit -o nounset 	&& echo "Testing Groovy installation" 	&& groovy --version
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
	-	`sha256:95f4dbc50da8407166ee96a8f817633942e9a1e1c0f939667abf99a9e9b33cb3`  
		Last Modified: Wed, 06 Jun 2018 02:24:42 GMT  
		Size: 77.4 MB (77404822 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a0fda20198ae353e075bf9d725214cbf1654648a6844bbbf06cc073a5183e558`  
		Last Modified: Tue, 19 Jun 2018 18:29:27 GMT  
		Size: 37.5 MB (37472536 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5f196b05a8c3fd425a1ccb03bd204059ce0accb76d6fa3b686101f1864e5a140`  
		Last Modified: Tue, 19 Jun 2018 18:29:24 GMT  
		Size: 140.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `groovy:jdk7-alpine` - linux; arm64 variant v8

```console
$ docker pull groovy@sha256:1f3d33f5bb8152432584830cdc61ff2d134a2618b0785a435d5b2189e4bd023c
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **114.9 MB (114896477 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:138feba549c6867f9addcc2827796fbe03317d2cc5596b1de8b73cc94758444f`
-	Default Command: `["groovysh"]`

```dockerfile
# Fri, 01 Dec 2017 18:42:42 GMT
ADD file:a6ef3cbbb1c0e5dfc6c3e41d70fd93e548594d9cb42c067e52df46d418c10a79 in / 
# Fri, 01 Dec 2017 18:42:42 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Fri, 01 Dec 2017 18:42:43 GMT
CMD ["/bin/sh"]
# Tue, 05 Dec 2017 11:05:19 GMT
ENV LANG=C.UTF-8
# Tue, 05 Dec 2017 11:05:21 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 05 Dec 2017 11:05:21 GMT
ENV JAVA_HOME=/usr/lib/jvm/java-1.7-openjdk
# Tue, 05 Dec 2017 11:05:22 GMT
ENV PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/lib/jvm/java-1.7-openjdk/jre/bin:/usr/lib/jvm/java-1.7-openjdk/bin
# Tue, 05 Dec 2017 11:05:23 GMT
ENV JAVA_VERSION=7u151
# Tue, 05 Dec 2017 11:05:23 GMT
ENV JAVA_ALPINE_VERSION=7.151.2.6.11-r0
# Tue, 05 Dec 2017 11:06:14 GMT
RUN set -x 	&& apk add --no-cache 		openjdk7="$JAVA_ALPINE_VERSION" 	&& [ "$JAVA_HOME" = "$(docker-java-home)" ]
# Wed, 20 Jun 2018 08:42:17 GMT
CMD ["groovysh"]
# Wed, 20 Jun 2018 08:42:18 GMT
ENV GROOVY_HOME=/opt/groovy
# Wed, 20 Jun 2018 08:42:19 GMT
ENV GROOVY_VERSION=2.4.15
# Wed, 20 Jun 2018 08:42:37 GMT
RUN set -o errexit -o nounset 	&& echo "Installing build dependencies" 	&& apk add --no-cache --virtual .build-deps 		ca-certificates 		gnupg 		openssl 		unzip 		&& echo "Downloading Groovy" 	&& wget -O groovy.zip "https://dist.apache.org/repos/dist/release/groovy/${GROOVY_VERSION}/distribution/apache-groovy-binary-${GROOVY_VERSION}.zip" 		&& echo "Importing keys listed in http://www.apache.org/dist/groovy/KEYS from key server" 	&& export GNUPGHOME="$(mktemp -d)" 	&& for key in 		"7FAA0F2206DE228F0DB01AD741321490758AAD6F" 		"331224E1D7BE883D16E8A685825C06C827AF6B66" 		"34441E504A937F43EB0DAEF96A65176A0FB1CD0B" 		"9A810E3B766E089FFB27C70F11B595CEDC4AEBB5" 		"81CABC23EECA0790E8989B361FF96E10F0E13706" 	; do 		for server in 			"ha.pool.sks-keyservers.net" 			"hkp://p80.pool.sks-keyservers.net:80" 			"pgp.mit.edu" 		; do 			echo "  Trying ${server}"; 			if gpg --keyserver "${server}" --recv-keys "${key}"; then 				break; 			fi; 		done; 	done; 	if [ $(gpg --list-keys | grep -c "pub ") -ne 5 ]; then 		echo "ERROR: Failed to fetch GPG keys" >&2; 		exit 1; 	fi 		&& echo "Checking download signature" 	&& wget -O groovy.zip.asc "https://dist.apache.org/repos/dist/release/groovy/${GROOVY_VERSION}/distribution/apache-groovy-binary-${GROOVY_VERSION}.zip.asc" 	&& gpg --batch --verify groovy.zip.asc groovy.zip 	&& rm -rf "${GNUPGHOME}" 	&& rm groovy.zip.asc 		&& echo "Installing Groovy" 	&& unzip groovy.zip 	&& rm groovy.zip 	&& mkdir /opt 	&& mv "groovy-${GROOVY_VERSION}" "${GROOVY_HOME}/" 	&& ln -s "${GROOVY_HOME}/bin/grape" /usr/bin/grape 	&& ln -s "${GROOVY_HOME}/bin/groovy" /usr/bin/groovy 	&& ln -s "${GROOVY_HOME}/bin/groovyc" /usr/bin/groovyc 	&& ln -s "${GROOVY_HOME}/bin/groovyConsole" /usr/bin/groovyConsole 	&& ln -s "${GROOVY_HOME}/bin/groovydoc" /usr/bin/groovydoc 	&& ln -s "${GROOVY_HOME}/bin/groovysh" /usr/bin/groovysh 	&& ln -s "${GROOVY_HOME}/bin/java2groovy" /usr/bin/java2groovy 		&& echo "Cleaning up build dependencies" 	&& apk del .build-deps 		&& echo "Adding groovy user and group" 	&& addgroup -S -g 1000 groovy 	&& adduser -D -S -G groovy -u 1000 -s /bin/ash groovy 	&& mkdir -p /home/groovy/.groovy/grapes 	&& chown -R groovy:groovy /home/groovy 		&& echo "Symlinking root .groovy to groovy .groovy" 	&& ln -s /home/groovy/.groovy /root/.groovy
# Wed, 20 Jun 2018 08:42:38 GMT
USER [groovy]
# Wed, 20 Jun 2018 08:42:39 GMT
VOLUME [/home/groovy/.groovy/grapes]
# Wed, 20 Jun 2018 08:42:40 GMT
WORKDIR /home/groovy
# Wed, 20 Jun 2018 08:42:44 GMT
RUN set -o errexit -o nounset 	&& echo "Testing Groovy installation" 	&& groovy --version
```

-	Layers:
	-	`sha256:b78042c299ad99d1e646b18762d4bc22a84c4f88e5bb491ea6293a10f53ddf79`  
		Last Modified: Fri, 01 Dec 2017 18:43:42 GMT  
		Size: 2.0 MB (1988857 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6fd45b97b6c2a3ac869ae5c99e087e97bc29714b165180e06f0c9116f400f2dd`  
		Last Modified: Fri, 01 Dec 2017 18:43:41 GMT  
		Size: 175.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bc4b770fee7695d8ca568c04817dd4e9d077997d617c75c75c6c47038c837df1`  
		Last Modified: Tue, 05 Dec 2017 11:12:04 GMT  
		Size: 238.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:416413fec3fbf11f3e37e924a354ac977f1933f06f58afe41111736da2f4828d`  
		Last Modified: Tue, 05 Dec 2017 11:12:21 GMT  
		Size: 75.4 MB (75434547 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d7167fe4977ffd2d2efab9eff6e59fa227b88b5adbc7f1cc5b02ff0d3e901128`  
		Last Modified: Fri, 22 Jun 2018 19:02:02 GMT  
		Size: 37.5 MB (37472520 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bebefe53a76a6b96724177a37d64867c4a86b1caa69edd186cf5297a516397a0`  
		Last Modified: Fri, 22 Jun 2018 19:01:56 GMT  
		Size: 140.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `groovy:jdk7-alpine` - linux; 386

```console
$ docker pull groovy@sha256:37ad37d7281e2e2406d2449e73547a18972e3fbb7406ec4fadcb6d29093d97d4
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **120.1 MB (120094313 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:82d631310b515ccefc8dc06225acd4a37eb4b58f19d3cbac102c7e3a72a82637`
-	Default Command: `["groovysh"]`

```dockerfile
# Fri, 01 Jun 2018 06:57:26 GMT
ADD file:614c07101e677db9a4118a71c852a2be45a337d94c5bedfb48ae8c4cad21d625 in / 
# Fri, 01 Jun 2018 06:57:26 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Fri, 01 Jun 2018 06:57:26 GMT
CMD ["/bin/sh"]
# Fri, 01 Jun 2018 10:39:41 GMT
ENV LANG=C.UTF-8
# Fri, 01 Jun 2018 10:39:42 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Fri, 01 Jun 2018 10:40:40 GMT
ENV JAVA_HOME=/usr/lib/jvm/java-1.7-openjdk
# Fri, 01 Jun 2018 10:40:40 GMT
ENV PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/lib/jvm/java-1.7-openjdk/jre/bin:/usr/lib/jvm/java-1.7-openjdk/bin
# Fri, 01 Jun 2018 10:40:40 GMT
ENV JAVA_VERSION=7u151
# Fri, 01 Jun 2018 10:40:40 GMT
ENV JAVA_ALPINE_VERSION=7.151.2.6.11-r0
# Fri, 01 Jun 2018 10:40:51 GMT
RUN set -x 	&& apk add --no-cache 		openjdk7="$JAVA_ALPINE_VERSION" 	&& [ "$JAVA_HOME" = "$(docker-java-home)" ]
# Wed, 20 Jun 2018 10:40:41 GMT
CMD ["groovysh"]
# Wed, 20 Jun 2018 10:40:41 GMT
ENV GROOVY_HOME=/opt/groovy
# Wed, 20 Jun 2018 10:40:42 GMT
ENV GROOVY_VERSION=2.4.15
# Wed, 20 Jun 2018 10:41:22 GMT
RUN set -o errexit -o nounset 	&& echo "Installing build dependencies" 	&& apk add --no-cache --virtual .build-deps 		ca-certificates 		gnupg 		openssl 		unzip 		&& echo "Downloading Groovy" 	&& wget -O groovy.zip "https://dist.apache.org/repos/dist/release/groovy/${GROOVY_VERSION}/distribution/apache-groovy-binary-${GROOVY_VERSION}.zip" 		&& echo "Importing keys listed in http://www.apache.org/dist/groovy/KEYS from key server" 	&& export GNUPGHOME="$(mktemp -d)" 	&& for key in 		"7FAA0F2206DE228F0DB01AD741321490758AAD6F" 		"331224E1D7BE883D16E8A685825C06C827AF6B66" 		"34441E504A937F43EB0DAEF96A65176A0FB1CD0B" 		"9A810E3B766E089FFB27C70F11B595CEDC4AEBB5" 		"81CABC23EECA0790E8989B361FF96E10F0E13706" 	; do 		for server in 			"ha.pool.sks-keyservers.net" 			"hkp://p80.pool.sks-keyservers.net:80" 			"pgp.mit.edu" 		; do 			echo "  Trying ${server}"; 			if gpg --keyserver "${server}" --recv-keys "${key}"; then 				break; 			fi; 		done; 	done; 	if [ $(gpg --list-keys | grep -c "pub ") -ne 5 ]; then 		echo "ERROR: Failed to fetch GPG keys" >&2; 		exit 1; 	fi 		&& echo "Checking download signature" 	&& wget -O groovy.zip.asc "https://dist.apache.org/repos/dist/release/groovy/${GROOVY_VERSION}/distribution/apache-groovy-binary-${GROOVY_VERSION}.zip.asc" 	&& gpg --batch --verify groovy.zip.asc groovy.zip 	&& rm -rf "${GNUPGHOME}" 	&& rm groovy.zip.asc 		&& echo "Installing Groovy" 	&& unzip groovy.zip 	&& rm groovy.zip 	&& mkdir /opt 	&& mv "groovy-${GROOVY_VERSION}" "${GROOVY_HOME}/" 	&& ln -s "${GROOVY_HOME}/bin/grape" /usr/bin/grape 	&& ln -s "${GROOVY_HOME}/bin/groovy" /usr/bin/groovy 	&& ln -s "${GROOVY_HOME}/bin/groovyc" /usr/bin/groovyc 	&& ln -s "${GROOVY_HOME}/bin/groovyConsole" /usr/bin/groovyConsole 	&& ln -s "${GROOVY_HOME}/bin/groovydoc" /usr/bin/groovydoc 	&& ln -s "${GROOVY_HOME}/bin/groovysh" /usr/bin/groovysh 	&& ln -s "${GROOVY_HOME}/bin/java2groovy" /usr/bin/java2groovy 		&& echo "Cleaning up build dependencies" 	&& apk del .build-deps 		&& echo "Adding groovy user and group" 	&& addgroup -S -g 1000 groovy 	&& adduser -D -S -G groovy -u 1000 -s /bin/ash groovy 	&& mkdir -p /home/groovy/.groovy/grapes 	&& chown -R groovy:groovy /home/groovy 		&& echo "Symlinking root .groovy to groovy .groovy" 	&& ln -s /home/groovy/.groovy /root/.groovy
# Wed, 20 Jun 2018 10:41:23 GMT
USER [groovy]
# Wed, 20 Jun 2018 10:41:23 GMT
VOLUME [/home/groovy/.groovy/grapes]
# Wed, 20 Jun 2018 10:41:23 GMT
WORKDIR /home/groovy
# Wed, 20 Jun 2018 10:41:25 GMT
RUN set -o errexit -o nounset 	&& echo "Testing Groovy installation" 	&& groovy --version
```

-	Layers:
	-	`sha256:381c1d4107a4401d75b916e6dc4331efddc01adac41f49eeaa711ab898606a1a`  
		Last Modified: Fri, 01 Dec 2017 18:47:24 GMT  
		Size: 2.1 MB (2126217 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:061a9db3c9e4f3bc32618a5f1a7e2b8aefb20fcc48f8be709bc7f7eabe61d003`  
		Last Modified: Fri, 01 Jun 2018 06:57:51 GMT  
		Size: 175.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:730d81ac3b103a2b66d5e57cd18c6079b49738517c93f83aa9bcc442da1f2b21`  
		Last Modified: Fri, 01 Jun 2018 10:42:08 GMT  
		Size: 240.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c63213ead468f3ce61f47a24b1ed9d82e343cf76d9fc57ed02b5e867cadf2e86`  
		Last Modified: Fri, 01 Jun 2018 10:45:27 GMT  
		Size: 80.5 MB (80494949 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a26920a54da3aeb73687f1e58025f1aebbee8b8863912c3ed0cd63883964a653`  
		Last Modified: Wed, 20 Jun 2018 11:16:24 GMT  
		Size: 37.5 MB (37472592 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6229bbf41eaba6a86c9f5f9b1e330c107e8ce316a184ab1a90c16c31565a04ba`  
		Last Modified: Wed, 20 Jun 2018 11:16:19 GMT  
		Size: 140.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `groovy:jdk7-alpine` - linux; ppc64le

```console
$ docker pull groovy@sha256:514cead7d5b66374f64e89f7b0b589dc3ac3924b1c2449a245ea962ab24d71d8
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **109.2 MB (109235943 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:070628c09bc95684bc29d9caaf1002cd2f9537d0e6d85b66bbd65963218083a5`
-	Default Command: `["groovysh"]`

```dockerfile
# Fri, 01 Dec 2017 18:41:54 GMT
ADD file:791370adae5cfa8feec749693f5a995a01f58f0462b7aa675fc5bf991e1282b5 in / 
# Fri, 01 Dec 2017 18:41:55 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Fri, 01 Dec 2017 18:41:57 GMT
CMD ["/bin/sh"]
# Tue, 05 Dec 2017 11:47:54 GMT
ENV LANG=C.UTF-8
# Tue, 05 Dec 2017 11:47:57 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 05 Dec 2017 11:47:59 GMT
ENV JAVA_HOME=/usr/lib/jvm/java-1.7-openjdk
# Tue, 05 Dec 2017 11:48:00 GMT
ENV PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/lib/jvm/java-1.7-openjdk/jre/bin:/usr/lib/jvm/java-1.7-openjdk/bin
# Tue, 05 Dec 2017 11:48:01 GMT
ENV JAVA_VERSION=7u151
# Tue, 05 Dec 2017 11:48:02 GMT
ENV JAVA_ALPINE_VERSION=7.151.2.6.11-r0
# Tue, 05 Dec 2017 11:48:55 GMT
RUN set -x 	&& apk add --no-cache 		openjdk7="$JAVA_ALPINE_VERSION" 	&& [ "$JAVA_HOME" = "$(docker-java-home)" ]
# Wed, 20 Jun 2018 08:36:59 GMT
CMD ["groovysh"]
# Wed, 20 Jun 2018 08:37:02 GMT
ENV GROOVY_HOME=/opt/groovy
# Wed, 20 Jun 2018 08:37:04 GMT
ENV GROOVY_VERSION=2.4.15
# Wed, 20 Jun 2018 08:37:42 GMT
RUN set -o errexit -o nounset 	&& echo "Installing build dependencies" 	&& apk add --no-cache --virtual .build-deps 		ca-certificates 		gnupg 		openssl 		unzip 		&& echo "Downloading Groovy" 	&& wget -O groovy.zip "https://dist.apache.org/repos/dist/release/groovy/${GROOVY_VERSION}/distribution/apache-groovy-binary-${GROOVY_VERSION}.zip" 		&& echo "Importing keys listed in http://www.apache.org/dist/groovy/KEYS from key server" 	&& export GNUPGHOME="$(mktemp -d)" 	&& for key in 		"7FAA0F2206DE228F0DB01AD741321490758AAD6F" 		"331224E1D7BE883D16E8A685825C06C827AF6B66" 		"34441E504A937F43EB0DAEF96A65176A0FB1CD0B" 		"9A810E3B766E089FFB27C70F11B595CEDC4AEBB5" 		"81CABC23EECA0790E8989B361FF96E10F0E13706" 	; do 		for server in 			"ha.pool.sks-keyservers.net" 			"hkp://p80.pool.sks-keyservers.net:80" 			"pgp.mit.edu" 		; do 			echo "  Trying ${server}"; 			if gpg --keyserver "${server}" --recv-keys "${key}"; then 				break; 			fi; 		done; 	done; 	if [ $(gpg --list-keys | grep -c "pub ") -ne 5 ]; then 		echo "ERROR: Failed to fetch GPG keys" >&2; 		exit 1; 	fi 		&& echo "Checking download signature" 	&& wget -O groovy.zip.asc "https://dist.apache.org/repos/dist/release/groovy/${GROOVY_VERSION}/distribution/apache-groovy-binary-${GROOVY_VERSION}.zip.asc" 	&& gpg --batch --verify groovy.zip.asc groovy.zip 	&& rm -rf "${GNUPGHOME}" 	&& rm groovy.zip.asc 		&& echo "Installing Groovy" 	&& unzip groovy.zip 	&& rm groovy.zip 	&& mkdir /opt 	&& mv "groovy-${GROOVY_VERSION}" "${GROOVY_HOME}/" 	&& ln -s "${GROOVY_HOME}/bin/grape" /usr/bin/grape 	&& ln -s "${GROOVY_HOME}/bin/groovy" /usr/bin/groovy 	&& ln -s "${GROOVY_HOME}/bin/groovyc" /usr/bin/groovyc 	&& ln -s "${GROOVY_HOME}/bin/groovyConsole" /usr/bin/groovyConsole 	&& ln -s "${GROOVY_HOME}/bin/groovydoc" /usr/bin/groovydoc 	&& ln -s "${GROOVY_HOME}/bin/groovysh" /usr/bin/groovysh 	&& ln -s "${GROOVY_HOME}/bin/java2groovy" /usr/bin/java2groovy 		&& echo "Cleaning up build dependencies" 	&& apk del .build-deps 		&& echo "Adding groovy user and group" 	&& addgroup -S -g 1000 groovy 	&& adduser -D -S -G groovy -u 1000 -s /bin/ash groovy 	&& mkdir -p /home/groovy/.groovy/grapes 	&& chown -R groovy:groovy /home/groovy 		&& echo "Symlinking root .groovy to groovy .groovy" 	&& ln -s /home/groovy/.groovy /root/.groovy
# Wed, 20 Jun 2018 08:37:44 GMT
USER [groovy]
# Wed, 20 Jun 2018 08:37:45 GMT
VOLUME [/home/groovy/.groovy/grapes]
# Wed, 20 Jun 2018 08:37:47 GMT
WORKDIR /home/groovy
# Wed, 20 Jun 2018 08:37:53 GMT
RUN set -o errexit -o nounset 	&& echo "Testing Groovy installation" 	&& groovy --version
```

-	Layers:
	-	`sha256:0da653ea85b50d280ec56ca2eafb7e8b37590630356e043fa9ff162d55732a23`  
		Last Modified: Fri, 01 Dec 2017 18:42:14 GMT  
		Size: 2.1 MB (2081469 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9fd90b777cc38b5b6ca1b2407e647fdc22ef31b57ef98e924e7e0635adffc385`  
		Last Modified: Fri, 01 Dec 2017 18:42:15 GMT  
		Size: 176.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8d80117bba7af560896439d844c0f3998317292d41faacc0a842ce3dd7e14605`  
		Last Modified: Tue, 05 Dec 2017 11:51:04 GMT  
		Size: 239.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1061c72558b55c62bfb93a17e9c05869fb18ca7ae72cb680eda1102a80b13b6e`  
		Last Modified: Tue, 05 Dec 2017 11:51:24 GMT  
		Size: 69.7 MB (69681273 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:828bceee0894fbd2888d6bd828dd3e134a03d7279ce493ed5219e6503a76f795`  
		Last Modified: Wed, 20 Jun 2018 09:36:21 GMT  
		Size: 37.5 MB (37472613 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5df25e4d0afe4fe779cd6d457198356c652204cfed3f580e4f1302c02775ee79`  
		Last Modified: Wed, 20 Jun 2018 09:36:16 GMT  
		Size: 173.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `groovy:jdk7-alpine` - linux; s390x

```console
$ docker pull groovy@sha256:79e1b6266bc3e020e04897fec30a81a86e771115121516ec0a84d71f2f0b7055
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **109.4 MB (109401865 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:efccd1edc8f071c4fd3ba3517d02db4f7a12e2fa3c6187d6e45445507e5a7cef`
-	Default Command: `["groovysh"]`

```dockerfile
# Fri, 01 Dec 2017 18:41:57 GMT
ADD file:9c09dfc247c393ab1c6205a4b7857047a3d88e398e8d35aede30f7d613ef1de9 in / 
# Fri, 01 Dec 2017 18:41:58 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Fri, 01 Dec 2017 18:41:58 GMT
CMD ["/bin/sh"]
# Tue, 05 Dec 2017 17:54:50 GMT
ENV LANG=C.UTF-8
# Tue, 05 Dec 2017 17:54:52 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 05 Dec 2017 17:54:52 GMT
ENV JAVA_HOME=/usr/lib/jvm/java-1.7-openjdk
# Tue, 05 Dec 2017 17:54:53 GMT
ENV PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/lib/jvm/java-1.7-openjdk/jre/bin:/usr/lib/jvm/java-1.7-openjdk/bin
# Tue, 05 Dec 2017 17:54:53 GMT
ENV JAVA_VERSION=7u151
# Tue, 05 Dec 2017 17:54:53 GMT
ENV JAVA_ALPINE_VERSION=7.151.2.6.11-r0
# Tue, 05 Dec 2017 17:55:40 GMT
RUN set -x 	&& apk add --no-cache 		openjdk7="$JAVA_ALPINE_VERSION" 	&& [ "$JAVA_HOME" = "$(docker-java-home)" ]
# Wed, 20 Jun 2018 11:42:55 GMT
CMD ["groovysh"]
# Wed, 20 Jun 2018 11:42:55 GMT
ENV GROOVY_HOME=/opt/groovy
# Wed, 20 Jun 2018 11:42:55 GMT
ENV GROOVY_VERSION=2.4.15
# Wed, 20 Jun 2018 11:43:07 GMT
RUN set -o errexit -o nounset 	&& echo "Installing build dependencies" 	&& apk add --no-cache --virtual .build-deps 		ca-certificates 		gnupg 		openssl 		unzip 		&& echo "Downloading Groovy" 	&& wget -O groovy.zip "https://dist.apache.org/repos/dist/release/groovy/${GROOVY_VERSION}/distribution/apache-groovy-binary-${GROOVY_VERSION}.zip" 		&& echo "Importing keys listed in http://www.apache.org/dist/groovy/KEYS from key server" 	&& export GNUPGHOME="$(mktemp -d)" 	&& for key in 		"7FAA0F2206DE228F0DB01AD741321490758AAD6F" 		"331224E1D7BE883D16E8A685825C06C827AF6B66" 		"34441E504A937F43EB0DAEF96A65176A0FB1CD0B" 		"9A810E3B766E089FFB27C70F11B595CEDC4AEBB5" 		"81CABC23EECA0790E8989B361FF96E10F0E13706" 	; do 		for server in 			"ha.pool.sks-keyservers.net" 			"hkp://p80.pool.sks-keyservers.net:80" 			"pgp.mit.edu" 		; do 			echo "  Trying ${server}"; 			if gpg --keyserver "${server}" --recv-keys "${key}"; then 				break; 			fi; 		done; 	done; 	if [ $(gpg --list-keys | grep -c "pub ") -ne 5 ]; then 		echo "ERROR: Failed to fetch GPG keys" >&2; 		exit 1; 	fi 		&& echo "Checking download signature" 	&& wget -O groovy.zip.asc "https://dist.apache.org/repos/dist/release/groovy/${GROOVY_VERSION}/distribution/apache-groovy-binary-${GROOVY_VERSION}.zip.asc" 	&& gpg --batch --verify groovy.zip.asc groovy.zip 	&& rm -rf "${GNUPGHOME}" 	&& rm groovy.zip.asc 		&& echo "Installing Groovy" 	&& unzip groovy.zip 	&& rm groovy.zip 	&& mkdir /opt 	&& mv "groovy-${GROOVY_VERSION}" "${GROOVY_HOME}/" 	&& ln -s "${GROOVY_HOME}/bin/grape" /usr/bin/grape 	&& ln -s "${GROOVY_HOME}/bin/groovy" /usr/bin/groovy 	&& ln -s "${GROOVY_HOME}/bin/groovyc" /usr/bin/groovyc 	&& ln -s "${GROOVY_HOME}/bin/groovyConsole" /usr/bin/groovyConsole 	&& ln -s "${GROOVY_HOME}/bin/groovydoc" /usr/bin/groovydoc 	&& ln -s "${GROOVY_HOME}/bin/groovysh" /usr/bin/groovysh 	&& ln -s "${GROOVY_HOME}/bin/java2groovy" /usr/bin/java2groovy 		&& echo "Cleaning up build dependencies" 	&& apk del .build-deps 		&& echo "Adding groovy user and group" 	&& addgroup -S -g 1000 groovy 	&& adduser -D -S -G groovy -u 1000 -s /bin/ash groovy 	&& mkdir -p /home/groovy/.groovy/grapes 	&& chown -R groovy:groovy /home/groovy 		&& echo "Symlinking root .groovy to groovy .groovy" 	&& ln -s /home/groovy/.groovy /root/.groovy
# Wed, 20 Jun 2018 11:43:07 GMT
USER [groovy]
# Wed, 20 Jun 2018 11:43:07 GMT
VOLUME [/home/groovy/.groovy/grapes]
# Wed, 20 Jun 2018 11:43:07 GMT
WORKDIR /home/groovy
# Wed, 20 Jun 2018 11:43:09 GMT
RUN set -o errexit -o nounset 	&& echo "Testing Groovy installation" 	&& groovy --version
```

-	Layers:
	-	`sha256:11e7bc85614a236b32043d147930fd2bc9055af8642fe30e5e56142590572b0e`  
		Last Modified: Fri, 01 Dec 2017 18:42:22 GMT  
		Size: 2.2 MB (2185231 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3f825cbb729285f1fe2a0cd1d4d36897e3fe2191c5ee044ce11a5d301dc64a34`  
		Last Modified: Fri, 01 Dec 2017 18:42:22 GMT  
		Size: 175.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:320238e3e22d841c8337cb6f2d8b95f9c1ab000f2845efcd5bd977690210f427`  
		Last Modified: Tue, 05 Dec 2017 17:58:18 GMT  
		Size: 239.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2f71969401ebfd29cbfcf3b4a230ad9279e59d89ae146e4953e07ebf1adf7dc6`  
		Last Modified: Tue, 05 Dec 2017 17:58:26 GMT  
		Size: 69.7 MB (69743443 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9b5df67d70608a911a39bd2b9e069747ca2856f169655d3445d097b37840ac53`  
		Last Modified: Wed, 20 Jun 2018 12:00:41 GMT  
		Size: 37.5 MB (37472638 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:82c5eaa168512b12fc25e2ed7ce75f84d4932aebd5167d37babe242a97ed3438`  
		Last Modified: Wed, 20 Jun 2018 12:00:37 GMT  
		Size: 139.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
