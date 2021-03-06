## `mongo:rc`

```console
$ docker pull mongo@sha256:cf9f43c9da3c12ce4af7721bdd7941e3ab341e83a3d3d3ebd85102bd3173b302
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm64 variant v8

### `mongo:rc` - linux; amd64

```console
$ docker pull mongo@sha256:d3445e8fd59357cfd690030cb76c635480e9c05ce5810d1952084bb792aa6f4d
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **133.3 MB (133290204 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:ff6df1473b5e76b5882320c5a86baa938197254a850b6ca29f4274e3a3b8d5ad`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["mongod"]`

```dockerfile
# Tue, 05 Jun 2018 21:21:52 GMT
ADD file:d37ff24540ea7700d0fc053e1996b234428a88f3a324d7fcbd83d8ef95318040 in / 
# Tue, 05 Jun 2018 21:21:53 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Tue, 05 Jun 2018 21:21:54 GMT
RUN rm -rf /var/lib/apt/lists/*
# Tue, 05 Jun 2018 21:21:54 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Tue, 05 Jun 2018 21:21:55 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Tue, 05 Jun 2018 21:21:55 GMT
CMD ["/bin/bash"]
# Tue, 05 Jun 2018 22:17:46 GMT
RUN groupadd -r mongodb && useradd -r -g mongodb mongodb
# Tue, 05 Jun 2018 22:18:03 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		ca-certificates 		jq 		numactl 	&& rm -rf /var/lib/apt/lists/*
# Tue, 05 Jun 2018 22:18:03 GMT
ENV GOSU_VERSION=1.10
# Tue, 05 Jun 2018 22:18:03 GMT
ENV JSYAML_VERSION=3.10.0
# Tue, 05 Jun 2018 22:18:14 GMT
RUN set -ex; 		apt-get update; 	apt-get install -y --no-install-recommends 		wget 	; 	rm -rf /var/lib/apt/lists/*; 		dpkgArch="$(dpkg --print-architecture | awk -F- '{ print $NF }')"; 	wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch"; 	wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch.asc"; 	export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4; 	gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu; 	rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc; 	chmod +x /usr/local/bin/gosu; 	gosu nobody true; 		wget -O /js-yaml.js "https://github.com/nodeca/js-yaml/raw/${JSYAML_VERSION}/dist/js-yaml.js"; 		apt-get purge -y --auto-remove wget
# Tue, 05 Jun 2018 22:18:15 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Tue, 05 Jun 2018 22:18:55 GMT
ENV GPG_KEYS=9DA31620334BD75D9DCB49F368818C72E52529D4
# Tue, 05 Jun 2018 22:18:55 GMT
RUN set -ex; 	export GNUPGHOME="$(mktemp -d)"; 	for key in $GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	done; 	gpg --export $GPG_KEYS > /etc/apt/trusted.gpg.d/mongodb.gpg; 	rm -r "$GNUPGHOME"; 	apt-key list
# Tue, 05 Jun 2018 22:18:56 GMT
ARG MONGO_PACKAGE=mongodb-org
# Tue, 05 Jun 2018 22:18:56 GMT
ARG MONGO_REPO=repo.mongodb.org
# Tue, 05 Jun 2018 22:18:56 GMT
ENV MONGO_PACKAGE=mongodb-org MONGO_REPO=repo.mongodb.org
# Tue, 05 Jun 2018 22:18:56 GMT
ENV MONGO_MAJOR=testing
# Wed, 20 Jun 2018 21:19:49 GMT
ENV MONGO_VERSION=4.0.0~rc6
# Wed, 20 Jun 2018 21:19:50 GMT
RUN echo "deb http://$MONGO_REPO/apt/ubuntu xenial/${MONGO_PACKAGE%-unstable}/$MONGO_MAJOR multiverse" | tee "/etc/apt/sources.list.d/${MONGO_PACKAGE%-unstable}.list"
# Wed, 20 Jun 2018 21:20:41 GMT
RUN set -x 	&& apt-get update 	&& apt-get install -y 		${MONGO_PACKAGE}=$MONGO_VERSION 		${MONGO_PACKAGE}-server=$MONGO_VERSION 		${MONGO_PACKAGE}-shell=$MONGO_VERSION 		${MONGO_PACKAGE}-mongos=$MONGO_VERSION 		${MONGO_PACKAGE}-tools=$MONGO_VERSION 	&& rm -rf /var/lib/apt/lists/* 	&& rm -rf /var/lib/mongodb 	&& mv /etc/mongod.conf /etc/mongod.conf.orig
# Wed, 20 Jun 2018 21:20:42 GMT
RUN mkdir -p /data/db /data/configdb 	&& chown -R mongodb:mongodb /data/db /data/configdb
# Wed, 20 Jun 2018 21:20:43 GMT
VOLUME [/data/db /data/configdb]
# Wed, 20 Jun 2018 21:20:43 GMT
COPY file:18c5d9b642a89adf49e037d95a9e7de6b60557c77e049c9652605cf9cba57df9 in /usr/local/bin/ 
# Wed, 20 Jun 2018 21:20:43 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Wed, 20 Jun 2018 21:20:44 GMT
EXPOSE 27017/tcp
# Wed, 20 Jun 2018 21:20:44 GMT
CMD ["mongod"]
```

-	Layers:
	-	`sha256:b234f539f7a1d65eabae1617e63c81ac01768abffd48b5cbbf7166efca6a3429`  
		Last Modified: Mon, 28 May 2018 14:57:20 GMT  
		Size: 43.1 MB (43122477 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:55172d420b43cf03feeec11bcc917c7ddfc192036102e065ab57aa9abb95311e`  
		Last Modified: Tue, 05 Jun 2018 21:24:52 GMT  
		Size: 853.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5ba5bbeb6b91e2676c98255c6babc66d7b05cac40185eeba4b3773199c701da0`  
		Last Modified: Tue, 05 Jun 2018 21:24:50 GMT  
		Size: 619.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:43ae2841ad7a7fd1aeae30028105cac7f6ee0ec955e5229e52b3333fea3c17b5`  
		Last Modified: Tue, 05 Jun 2018 21:24:50 GMT  
		Size: 851.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f6c9c6de41905e9a66f2bc2c4a19858c8dc5b0a94f01e03eafc719afe25888aa`  
		Last Modified: Tue, 05 Jun 2018 21:24:50 GMT  
		Size: 168.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f81ef705874ba41139fb9e3e738890926d3b288a7bcb95ad4a221dca803bee64`  
		Last Modified: Tue, 05 Jun 2018 22:22:21 GMT  
		Size: 2.0 KB (1991 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e03aae48954c67da71e6660e9e9a7d998f1091136f2a9fbb12ff1cd2b1007025`  
		Last Modified: Tue, 05 Jun 2018 22:22:23 GMT  
		Size: 2.9 MB (2946140 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:28f5018fd172c8d359b998fb99d68bea25ebac4863591020c4a140bdf6d3dda8`  
		Last Modified: Tue, 05 Jun 2018 22:22:23 GMT  
		Size: 750.9 KB (750919 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3a113ac70b9a14fa4f056d53b06fef4996af9097c8ab7e7e73d8511c79b6e6b3`  
		Last Modified: Tue, 05 Jun 2018 22:22:21 GMT  
		Size: 115.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ea5de9f6f5aca92a32077d8ea3c392759667ed649ba98c2afd35cb9009b24fdd`  
		Last Modified: Tue, 05 Jun 2018 22:23:09 GMT  
		Size: 1.4 KB (1423 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c585705b362b2fc46a94c62dd3d74a9dfe0dcc65940305d6863a78179f6bb297`  
		Last Modified: Wed, 20 Jun 2018 21:21:06 GMT  
		Size: 240.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2b6a88e5e4885ac6fcccc9bafd107c0f6f675b17f57faf5eccc3f53f937ba30f`  
		Last Modified: Wed, 20 Jun 2018 21:21:38 GMT  
		Size: 86.5 MB (86460557 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:beba0a5a9221ae08aa9b2d12b85487fd2265092d3794cc1863b4a5608a2a6f7a`  
		Last Modified: Wed, 20 Jun 2018 21:21:06 GMT  
		Size: 139.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:43cbf03936e6cff309c96818023ca640df395f1d775e5f9d2894168c2d358791`  
		Last Modified: Wed, 20 Jun 2018 21:21:06 GMT  
		Size: 3.7 KB (3712 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `mongo:rc` - linux; arm64 variant v8

```console
$ docker pull mongo@sha256:72e07381553c53b6b467d25980d27ab8e8c21f877f5468f2f7cf1114de92796c
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **153.4 MB (153385398 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:b823e8979b28445314ceddab6192dd728287fac9a3ce31d421515406fcb2add3`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["mongod"]`

```dockerfile
# Wed, 06 Jun 2018 09:38:27 GMT
ADD file:4d66a098626c376a1c073e0332a6c8d18aa8cc0dbadb329fd506fdfa59793143 in / 
# Wed, 06 Jun 2018 09:38:30 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Wed, 06 Jun 2018 09:38:32 GMT
RUN rm -rf /var/lib/apt/lists/*
# Wed, 06 Jun 2018 09:38:34 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Wed, 06 Jun 2018 09:38:37 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Wed, 06 Jun 2018 09:38:37 GMT
CMD ["/bin/bash"]
# Wed, 06 Jun 2018 10:41:32 GMT
RUN groupadd -r mongodb && useradd -r -g mongodb mongodb
# Wed, 06 Jun 2018 10:42:08 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		ca-certificates 		jq 		numactl 	&& rm -rf /var/lib/apt/lists/*
# Wed, 06 Jun 2018 10:42:10 GMT
ENV GOSU_VERSION=1.10
# Wed, 06 Jun 2018 10:42:12 GMT
ENV JSYAML_VERSION=3.10.0
# Wed, 06 Jun 2018 10:42:44 GMT
RUN set -ex; 		apt-get update; 	apt-get install -y --no-install-recommends 		wget 	; 	rm -rf /var/lib/apt/lists/*; 		dpkgArch="$(dpkg --print-architecture | awk -F- '{ print $NF }')"; 	wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch"; 	wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch.asc"; 	export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4; 	gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu; 	rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc; 	chmod +x /usr/local/bin/gosu; 	gosu nobody true; 		wget -O /js-yaml.js "https://github.com/nodeca/js-yaml/raw/${JSYAML_VERSION}/dist/js-yaml.js"; 		apt-get purge -y --auto-remove wget
# Wed, 06 Jun 2018 10:42:54 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Wed, 06 Jun 2018 10:45:22 GMT
ENV GPG_KEYS=9DA31620334BD75D9DCB49F368818C72E52529D4
# Wed, 06 Jun 2018 10:45:25 GMT
RUN set -ex; 	export GNUPGHOME="$(mktemp -d)"; 	for key in $GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	done; 	gpg --export $GPG_KEYS > /etc/apt/trusted.gpg.d/mongodb.gpg; 	rm -r "$GNUPGHOME"; 	apt-key list
# Wed, 06 Jun 2018 10:45:28 GMT
ARG MONGO_PACKAGE=mongodb-org
# Wed, 06 Jun 2018 10:45:31 GMT
ARG MONGO_REPO=repo.mongodb.org
# Wed, 06 Jun 2018 10:45:34 GMT
ENV MONGO_PACKAGE=mongodb-org MONGO_REPO=repo.mongodb.org
# Wed, 06 Jun 2018 10:45:35 GMT
ENV MONGO_MAJOR=testing
# Thu, 21 Jun 2018 08:48:34 GMT
ENV MONGO_VERSION=4.0.0~rc6
# Thu, 21 Jun 2018 08:48:36 GMT
RUN echo "deb http://$MONGO_REPO/apt/ubuntu xenial/${MONGO_PACKAGE%-unstable}/$MONGO_MAJOR multiverse" | tee "/etc/apt/sources.list.d/${MONGO_PACKAGE%-unstable}.list"
# Thu, 21 Jun 2018 08:49:38 GMT
RUN set -x 	&& apt-get update 	&& apt-get install -y 		${MONGO_PACKAGE}=$MONGO_VERSION 		${MONGO_PACKAGE}-server=$MONGO_VERSION 		${MONGO_PACKAGE}-shell=$MONGO_VERSION 		${MONGO_PACKAGE}-mongos=$MONGO_VERSION 		${MONGO_PACKAGE}-tools=$MONGO_VERSION 	&& rm -rf /var/lib/apt/lists/* 	&& rm -rf /var/lib/mongodb 	&& mv /etc/mongod.conf /etc/mongod.conf.orig
# Thu, 21 Jun 2018 08:49:40 GMT
RUN mkdir -p /data/db /data/configdb 	&& chown -R mongodb:mongodb /data/db /data/configdb
# Thu, 21 Jun 2018 08:49:41 GMT
VOLUME [/data/db /data/configdb]
# Thu, 21 Jun 2018 08:49:42 GMT
COPY file:18c5d9b642a89adf49e037d95a9e7de6b60557c77e049c9652605cf9cba57df9 in /usr/local/bin/ 
# Thu, 21 Jun 2018 08:49:43 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Thu, 21 Jun 2018 08:49:44 GMT
EXPOSE 27017/tcp
# Thu, 21 Jun 2018 08:49:44 GMT
CMD ["mongod"]
```

-	Layers:
	-	`sha256:21707c5c72669fddc5511cbdced3327d864e1cb7aa4d1d273beb008be29c82dc`  
		Last Modified: Mon, 28 May 2018 14:58:41 GMT  
		Size: 39.3 MB (39283293 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f2b2716544889f4e40c0d32347e352b47046e2b8f272a78cd166f50462a2010a`  
		Last Modified: Wed, 06 Jun 2018 09:43:13 GMT  
		Size: 853.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3396a4a881d875be937f4b13c557a03aca52cb7d058d39395da1f896f8feda23`  
		Last Modified: Wed, 06 Jun 2018 09:43:12 GMT  
		Size: 612.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4f138533abd45add28f8a1ca64239b68a83458387b0d2b1066002ca9b94f6215`  
		Last Modified: Wed, 06 Jun 2018 09:43:12 GMT  
		Size: 856.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7992862215acd8daf7477cdc3dea5fbf67934989b013a18828f88e64ea00d70a`  
		Last Modified: Wed, 06 Jun 2018 09:43:12 GMT  
		Size: 170.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ae65166e186b0f755bceb763832e7e1c061687a5b6d2fa3dae1f1fce6e19f1e3`  
		Last Modified: Wed, 06 Jun 2018 10:48:14 GMT  
		Size: 2.0 KB (1992 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a03fc6d46aeeb4deb87079ac87fc8579d68283ff85a7a3bc12349c2175230490`  
		Last Modified: Wed, 06 Jun 2018 10:48:17 GMT  
		Size: 2.5 MB (2474969 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ccc1a4d2360f90254ba7da51561477e79e2bb549c3ede15f70b2361117d0e24f`  
		Last Modified: Wed, 06 Jun 2018 10:48:14 GMT  
		Size: 717.9 KB (717900 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:89c801b5777b67a93934e6ac32be46391aa742ad3b0365b6b8d3220a23884df4`  
		Last Modified: Wed, 06 Jun 2018 10:48:12 GMT  
		Size: 113.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:039f3cc35ee7920cd06f65d5f0909f54e5626231d9e8dfe25eb9f6ce3c05b50e`  
		Last Modified: Wed, 06 Jun 2018 10:49:33 GMT  
		Size: 1.4 KB (1425 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6e2b9ca8b0c46872875a0833b954213afdbc7a5846a0fe1fd567e910b7fc3e23`  
		Last Modified: Thu, 21 Jun 2018 08:50:16 GMT  
		Size: 242.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7b66391dc3320e5c9e66c304fa2814c5d62d182563d9a4c98ea734e34a33a1c8`  
		Last Modified: Thu, 21 Jun 2018 08:50:58 GMT  
		Size: 110.9 MB (110899123 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:211e4c41abe5532e618435b045095e097b70096bec6f5f993792002c5de88b55`  
		Last Modified: Thu, 21 Jun 2018 08:50:15 GMT  
		Size: 139.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:609eb6a22681d0fe6c7a5b437995b21fc28ca974d6d686f6bf1f528941abd1f1`  
		Last Modified: Thu, 21 Jun 2018 08:50:16 GMT  
		Size: 3.7 KB (3711 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
