## `mongo-express:latest`

```console
$ docker pull mongo-express@sha256:92ce1f308e1fdb3aff5e739b5b34362178fd519bcb0d1d22d123e2b7bf69a462
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `mongo-express:latest` - linux; amd64

```console
$ docker pull mongo-express@sha256:f225ec6052b09c11a74746f71e15d6066d40db0344bff15b9f3480f797f8c23f
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **76.3 MB (76276379 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:e588c58655e55e0ca05e7bc78a1a7b83a227816013984d00e36cd2307342d002`
-	Default Command: `["tini","--","node","app"]`

```dockerfile
# Sat, 28 Apr 2018 06:45:24 GMT
ADD file:50be6ceb11c382ed9674106471df123e9a76f549fe729b4751bc95662258f9e0 in / 
# Sat, 28 Apr 2018 06:45:24 GMT
CMD ["bash"]
# Thu, 24 May 2018 19:43:05 GMT
RUN groupadd --gid 1000 node   && useradd --uid 1000 --gid node --shell /bin/bash --create-home node
# Wed, 20 Jun 2018 22:46:42 GMT
RUN set -ex   && for key in     94AE36675C464D64BAFA68DD7434390BDBE9B9C5     FD3A5288F042B6850C66B31F09FE44734EB7990E     71DCFD284A79C3B38668286BC97EC7A07EDE3FC1     DD8F2338BAE7501E3DD5AC78C273792F7D83545D     C4F0DFFF4E8C1A8236409D08E73BC641CC11F4C8     B9AE9905FFD7803F25714661B63B535A4C206CA9     56730D5401028683275BD23C23EFEFE93C4CFFFE     77984A986EBC2AA786BC0F66B01FBB92821C587A     8FCCA13FEF1D0C2E91008E09770F7A9A5AE15600   ; do     gpg --keyserver hkp://p80.pool.sks-keyservers.net:80 --recv-keys "$key" ||     gpg --keyserver hkp://ipv4.pool.sks-keyservers.net --recv-keys "$key" ||     gpg --keyserver hkp://pgp.mit.edu:80 --recv-keys "$key" ;   done
# Wed, 20 Jun 2018 23:14:43 GMT
ENV NODE_VERSION=8.11.3
# Wed, 20 Jun 2018 23:15:13 GMT
RUN buildDeps='xz-utils'     && ARCH= && dpkgArch="$(dpkg --print-architecture)"     && case "${dpkgArch##*-}" in       amd64) ARCH='x64';;       ppc64el) ARCH='ppc64le';;       s390x) ARCH='s390x';;       arm64) ARCH='arm64';;       armhf) ARCH='armv7l';;       i386) ARCH='x86';;       *) echo "unsupported architecture"; exit 1 ;;     esac     && set -x     && apt-get update && apt-get install -y ca-certificates curl wget $buildDeps --no-install-recommends     && rm -rf /var/lib/apt/lists/*     && curl -fsSLO --compressed "https://nodejs.org/dist/v$NODE_VERSION/node-v$NODE_VERSION-linux-$ARCH.tar.xz"     && curl -fsSLO --compressed "https://nodejs.org/dist/v$NODE_VERSION/SHASUMS256.txt.asc"     && gpg --batch --decrypt --output SHASUMS256.txt SHASUMS256.txt.asc     && grep " node-v$NODE_VERSION-linux-$ARCH.tar.xz\$" SHASUMS256.txt | sha256sum -c -     && tar -xJf "node-v$NODE_VERSION-linux-$ARCH.tar.xz" -C /usr/local --strip-components=1 --no-same-owner     && rm "node-v$NODE_VERSION-linux-$ARCH.tar.xz" SHASUMS256.txt.asc SHASUMS256.txt     && apt-get purge -y --auto-remove $buildDeps     && ln -s /usr/local/bin/node /usr/local/bin/nodejs
# Wed, 20 Jun 2018 23:15:14 GMT
ENV YARN_VERSION=1.6.0
# Wed, 20 Jun 2018 23:15:17 GMT
RUN set -ex   && for key in     6A010C5166006599AA17F08146C2130DFD2497F5   ; do     gpg --keyserver hkp://p80.pool.sks-keyservers.net:80 --recv-keys "$key" ||     gpg --keyserver hkp://ipv4.pool.sks-keyservers.net --recv-keys "$key" ||     gpg --keyserver hkp://pgp.mit.edu:80 --recv-keys "$key" ;   done   && curl -fsSLO --compressed "https://yarnpkg.com/downloads/$YARN_VERSION/yarn-v$YARN_VERSION.tar.gz"   && curl -fsSLO --compressed "https://yarnpkg.com/downloads/$YARN_VERSION/yarn-v$YARN_VERSION.tar.gz.asc"   && gpg --batch --verify yarn-v$YARN_VERSION.tar.gz.asc yarn-v$YARN_VERSION.tar.gz   && mkdir -p /opt   && tar -xzf yarn-v$YARN_VERSION.tar.gz -C /opt/   && ln -s /opt/yarn-v$YARN_VERSION/bin/yarn /usr/local/bin/yarn   && ln -s /opt/yarn-v$YARN_VERSION/bin/yarnpkg /usr/local/bin/yarnpkg   && rm yarn-v$YARN_VERSION.tar.gz.asc yarn-v$YARN_VERSION.tar.gz
# Wed, 20 Jun 2018 23:15:17 GMT
CMD ["node"]
# Thu, 21 Jun 2018 00:43:38 GMT
ENV TINI_VERSION=0.9.0
# Thu, 21 Jun 2018 00:43:56 GMT
RUN set -x 	&& apt-get update && apt-get install -y ca-certificates curl 		--no-install-recommends 	&& curl -fSL "https://github.com/krallin/tini/releases/download/v${TINI_VERSION}/tini" -o /usr/local/bin/tini 	&& curl -fSL "https://github.com/krallin/tini/releases/download/v${TINI_VERSION}/tini.asc" -o /usr/local/bin/tini.asc 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5 	&& gpg --batch --verify /usr/local/bin/tini.asc /usr/local/bin/tini 	&& rm -r "$GNUPGHOME" /usr/local/bin/tini.asc 	&& chmod +x /usr/local/bin/tini 	&& tini -h 	&& apt-get purge --auto-remove -y ca-certificates curl 	&& rm -rf /var/lib/apt/lists/*
# Thu, 21 Jun 2018 00:43:57 GMT
EXPOSE 8081/tcp
# Thu, 21 Jun 2018 00:43:57 GMT
ENV ME_CONFIG_EDITORTHEME=default ME_CONFIG_MONGODB_SERVER=mongo ME_CONFIG_MONGODB_ENABLE_ADMIN=true ME_CONFIG_BASICAUTH_USERNAME= ME_CONFIG_BASICAUTH_PASSWORD= VCAP_APP_HOST=0.0.0.0
# Thu, 21 Jun 2018 00:43:57 GMT
ENV MONGO_EXPRESS=0.45.0
# Thu, 21 Jun 2018 00:44:06 GMT
RUN npm install mongo-express@$MONGO_EXPRESS
# Thu, 21 Jun 2018 00:44:07 GMT
WORKDIR /node_modules/mongo-express
# Thu, 21 Jun 2018 00:44:08 GMT
RUN cp config.default.js config.js
# Thu, 21 Jun 2018 00:44:08 GMT
CMD ["tini" "--" "node" "app"]
```

-	Layers:
	-	`sha256:4d0d76e05f3c6caf923a71ca3b3d2cc8c834ca61779ae6b6d83547f3dd814980`  
		Last Modified: Sat, 28 Apr 2018 08:30:42 GMT  
		Size: 30.1 MB (30127297 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:db908151ac093a2ced2707e30d84874d4d162594ee84613e477f739f682410f1`  
		Last Modified: Thu, 24 May 2018 20:54:10 GMT  
		Size: 4.4 KB (4400 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2af720db3333a732576adb3559c71f226a60f6ac5af8fcceb3383299c115599d`  
		Last Modified: Thu, 21 Jun 2018 00:10:27 GMT  
		Size: 123.6 KB (123616 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8c62eb4ab4e0abedea0043be15b880e9c54f12120ab7ae9ee20cbe9f14e9a7be`  
		Last Modified: Thu, 21 Jun 2018 00:15:07 GMT  
		Size: 35.3 MB (35266807 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:06c72047b59bf2926075a818288b99bc7bc4e654d3d34bc4ae54f92b3f697211`  
		Last Modified: Thu, 21 Jun 2018 00:14:57 GMT  
		Size: 1.1 MB (1072187 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c6f36a1776d8562a435dfd588ea2ae9b3639e37e9a5eb3c17713c6787ef92a8d`  
		Last Modified: Thu, 21 Jun 2018 00:44:25 GMT  
		Size: 532.4 KB (532387 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:de64f5d8052413a698f177517d1ee39e38d150311b75fc17501ec815c01ed687`  
		Last Modified: Thu, 21 Jun 2018 00:44:26 GMT  
		Size: 9.1 MB (9146927 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1cacb8e99a36e097eb91c1af08a72413fd3fafb7fd1825670d79bfa898c3ba15`  
		Last Modified: Thu, 21 Jun 2018 00:44:25 GMT  
		Size: 2.8 KB (2758 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
