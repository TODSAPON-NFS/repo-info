## `ghost:alpine`

```console
$ docker pull ghost@sha256:f359ce73cef3368797f8542870598b2d707c631144b01a3c3c01e25502ebaffc
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `ghost:alpine` - linux; amd64

```console
$ docker pull ghost@sha256:a6071c35133a200252ff7a556b1715d74270d8391a6390bc73585084f60d2764
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **179.1 MB (179061989 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:603334de009fa5d4c665f251d653be32328042dc4769f1c68be3d1472d1b823c`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["node","current\/index.js"]`

```dockerfile
# Tue, 09 Jan 2018 21:12:40 GMT
ADD file:69848cb51056edaf120230b6f218a79968ac797295c2cef6728332e1801357be in / 
# Tue, 09 Jan 2018 21:12:40 GMT
CMD ["/bin/sh"]
# Wed, 20 Jun 2018 23:16:10 GMT
ENV NODE_VERSION=6.14.3
# Wed, 20 Jun 2018 23:28:19 GMT
RUN addgroup -g 1000 node     && adduser -u 1000 -G node -s /bin/sh -D node     && apk add --no-cache         libstdc++     && apk add --no-cache --virtual .build-deps         binutils-gold         curl         g++         gcc         gnupg         libgcc         linux-headers         make         python   && for key in     94AE36675C464D64BAFA68DD7434390BDBE9B9C5     FD3A5288F042B6850C66B31F09FE44734EB7990E     71DCFD284A79C3B38668286BC97EC7A07EDE3FC1     DD8F2338BAE7501E3DD5AC78C273792F7D83545D     C4F0DFFF4E8C1A8236409D08E73BC641CC11F4C8     B9AE9905FFD7803F25714661B63B535A4C206CA9     56730D5401028683275BD23C23EFEFE93C4CFFFE     77984A986EBC2AA786BC0F66B01FBB92821C587A     8FCCA13FEF1D0C2E91008E09770F7A9A5AE15600   ; do     gpg --keyserver hkp://p80.pool.sks-keyservers.net:80 --recv-keys "$key" ||     gpg --keyserver hkp://ipv4.pool.sks-keyservers.net --recv-keys "$key" ||     gpg --keyserver hkp://pgp.mit.edu:80 --recv-keys "$key" ;   done     && curl -fsSLO --compressed "https://nodejs.org/dist/v$NODE_VERSION/node-v$NODE_VERSION.tar.xz"     && curl -fsSLO --compressed "https://nodejs.org/dist/v$NODE_VERSION/SHASUMS256.txt.asc"     && gpg --batch --decrypt --output SHASUMS256.txt SHASUMS256.txt.asc     && grep " node-v$NODE_VERSION.tar.xz\$" SHASUMS256.txt | sha256sum -c -     && tar -xf "node-v$NODE_VERSION.tar.xz"     && cd "node-v$NODE_VERSION"     && ./configure     && make -j$(getconf _NPROCESSORS_ONLN)     && make install     && apk del .build-deps     && cd ..     && rm -Rf "node-v$NODE_VERSION"     && rm "node-v$NODE_VERSION.tar.xz" SHASUMS256.txt.asc SHASUMS256.txt
# Wed, 20 Jun 2018 23:28:19 GMT
ENV YARN_VERSION=1.6.0
# Wed, 20 Jun 2018 23:28:33 GMT
RUN apk add --no-cache --virtual .build-deps-yarn curl gnupg tar   && for key in     6A010C5166006599AA17F08146C2130DFD2497F5   ; do     gpg --keyserver hkp://p80.pool.sks-keyservers.net:80 --recv-keys "$key" ||     gpg --keyserver hkp://ipv4.pool.sks-keyservers.net --recv-keys "$key" ||     gpg --keyserver hkp://pgp.mit.edu:80 --recv-keys "$key" ;   done   && curl -fsSLO --compressed "https://yarnpkg.com/downloads/$YARN_VERSION/yarn-v$YARN_VERSION.tar.gz"   && curl -fsSLO --compressed "https://yarnpkg.com/downloads/$YARN_VERSION/yarn-v$YARN_VERSION.tar.gz.asc"   && gpg --batch --verify yarn-v$YARN_VERSION.tar.gz.asc yarn-v$YARN_VERSION.tar.gz   && mkdir -p /opt   && tar -xzf yarn-v$YARN_VERSION.tar.gz -C /opt/   && ln -s /opt/yarn-v$YARN_VERSION/bin/yarn /usr/local/bin/yarn   && ln -s /opt/yarn-v$YARN_VERSION/bin/yarnpkg /usr/local/bin/yarnpkg   && rm yarn-v$YARN_VERSION.tar.gz.asc yarn-v$YARN_VERSION.tar.gz   && apk del .build-deps-yarn
# Wed, 20 Jun 2018 23:28:33 GMT
CMD ["node"]
# Thu, 21 Jun 2018 00:43:47 GMT
RUN apk add --no-cache 'su-exec>=0.2'
# Thu, 21 Jun 2018 00:43:49 GMT
RUN apk add --no-cache 		bash
# Thu, 21 Jun 2018 00:43:56 GMT
ENV NODE_ENV=production
# Thu, 21 Jun 2018 00:43:56 GMT
ENV GHOST_CLI_VERSION=1.8.1
# Thu, 21 Jun 2018 00:44:28 GMT
RUN npm install -g "ghost-cli@$GHOST_CLI_VERSION"
# Thu, 21 Jun 2018 00:44:29 GMT
ENV GHOST_INSTALL=/var/lib/ghost
# Thu, 21 Jun 2018 00:44:29 GMT
ENV GHOST_CONTENT=/var/lib/ghost/content
# Thu, 21 Jun 2018 00:44:29 GMT
ENV GHOST_VERSION=1.24.5
# Thu, 21 Jun 2018 00:45:20 GMT
RUN set -ex; 	mkdir -p "$GHOST_INSTALL"; 	chown node:node "$GHOST_INSTALL"; 		su-exec node ghost install "$GHOST_VERSION" --db sqlite3 --no-prompt --no-stack --no-setup --dir "$GHOST_INSTALL"; 		cd "$GHOST_INSTALL"; 	su-exec node ghost config --ip 0.0.0.0 --port 2368 --no-prompt --db sqlite3 --url http://localhost:2368 --dbpath "$GHOST_CONTENT/data/ghost.db"; 	su-exec node ghost config paths.contentPath "$GHOST_CONTENT"; 		su-exec node ln -s config.production.json "$GHOST_INSTALL/config.development.json"; 	readlink -f "$GHOST_INSTALL/config.development.json"; 		mv "$GHOST_CONTENT" "$GHOST_INSTALL/content.orig"; 	mkdir -p "$GHOST_CONTENT"; 	chown node:node "$GHOST_CONTENT"; 		"$GHOST_INSTALL/current/node_modules/knex-migrator/bin/knex-migrator" --version
# Thu, 21 Jun 2018 00:45:22 GMT
ENV PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/var/lib/ghost/current/node_modules/knex-migrator/bin
# Thu, 21 Jun 2018 00:45:27 GMT
WORKDIR /var/lib/ghost
# Thu, 21 Jun 2018 00:45:27 GMT
VOLUME [/var/lib/ghost/content]
# Thu, 21 Jun 2018 00:45:27 GMT
COPY file:fe4f8ce065580d78daf2ea3ae3ab9174f3edd7740df8b95889926dc1cdfe77b0 in /usr/local/bin 
# Thu, 21 Jun 2018 00:45:27 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Thu, 21 Jun 2018 00:45:27 GMT
EXPOSE 2368/tcp
# Thu, 21 Jun 2018 00:45:28 GMT
CMD ["node" "current/index.js"]
```

-	Layers:
	-	`sha256:81033e7c1d6a5b44a94bb6b40033a6e589f50fd6b61578da6fc809e61f83898d`  
		Last Modified: Tue, 09 Jan 2018 21:15:04 GMT  
		Size: 2.4 MB (2387570 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0271827f8906b22a7291f6c6bca9c78da874ab08b6fa954ae464c8f47fa86bc9`  
		Last Modified: Thu, 21 Jun 2018 00:18:22 GMT  
		Size: 15.5 MB (15515157 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ad6e97105bdf7011951263aca0ce452e732e9f39b1f44b5f5214dfe3cacde617`  
		Last Modified: Thu, 21 Jun 2018 00:18:17 GMT  
		Size: 1.1 MB (1079011 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:977c25c637035f957a10a8be760931c388e00d9ac669ad0c203d7f3903355244`  
		Last Modified: Thu, 21 Jun 2018 00:51:47 GMT  
		Size: 8.4 KB (8364 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e36b20705504f2a14c4e7c215ca5ec0c9b8310f96ee93d40a82193d35ea6b231`  
		Last Modified: Thu, 21 Jun 2018 00:51:49 GMT  
		Size: 1.1 MB (1119118 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4adf98ce337ee57d636ad9865c848058680941c3f725ffa2b225bd640e3d2b6e`  
		Last Modified: Thu, 21 Jun 2018 00:51:56 GMT  
		Size: 17.8 MB (17838112 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:514288f0804f9d5b8442cf3861c270f667c77b2b8504d3c9dd72d714b427355c`  
		Last Modified: Thu, 21 Jun 2018 00:52:24 GMT  
		Size: 141.1 MB (141114101 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:89f2946383b6dff62f58427be52a100a4172870b7ecfbd0dfbc9767316fc9fe9`  
		Last Modified: Thu, 21 Jun 2018 00:51:47 GMT  
		Size: 556.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
