## `jetty:9-jre7`

```console
$ docker pull jetty@sha256:1ce124d8dfa96a43f4d1fb5de15d0bb63f2724c6d8bf9be89bcfda16c0b922cb
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

### `jetty:9-jre7` - linux; amd64

```console
$ docker pull jetty@sha256:d9de5d0bde461be8dea86462e54fb7fcc965c60f6a24fb1664308948d81c7da3
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **165.0 MB (164959581 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:c8ff5588b46296a4103925b073823a7309467f1715b09757e9b8e73f2cdb494d`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["java","-jar","\/usr\/local\/jetty\/start.jar"]`

```dockerfile
# Sat, 28 Apr 2018 06:44:15 GMT
ADD file:3e6141c0c9cb74b14a281eb3ab7aaf162a625733e652c3948b323bb2ec8b4343 in / 
# Sat, 28 Apr 2018 06:44:16 GMT
CMD ["bash"]
# Tue, 05 Jun 2018 23:07:43 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 05 Jun 2018 23:07:44 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Wed, 06 Jun 2018 01:58:22 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Wed, 06 Jun 2018 01:58:22 GMT
ENV LANG=C.UTF-8
# Wed, 06 Jun 2018 01:58:23 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Wed, 06 Jun 2018 01:58:23 GMT
RUN ln -svT "/usr/lib/jvm/java-7-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Wed, 06 Jun 2018 01:58:24 GMT
ENV JAVA_HOME=/docker-java-home/jre
# Sat, 16 Jun 2018 07:26:46 GMT
ENV JAVA_VERSION=7u181
# Sat, 16 Jun 2018 07:26:47 GMT
ENV JAVA_DEBIAN_VERSION=7u181-2.6.14-1~deb8u1
# Sat, 16 Jun 2018 07:27:58 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-7-jre="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Sat, 16 Jun 2018 08:16:36 GMT
RUN groupadd -r jetty && useradd -r -g jetty jetty
# Sat, 16 Jun 2018 08:16:36 GMT
ENV JETTY_HOME=/usr/local/jetty
# Sat, 16 Jun 2018 08:16:37 GMT
ENV PATH=/usr/local/jetty/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Sat, 16 Jun 2018 08:16:37 GMT
RUN mkdir -p "$JETTY_HOME"
# Sat, 16 Jun 2018 08:16:38 GMT
WORKDIR /usr/local/jetty
# Sat, 16 Jun 2018 08:16:38 GMT
ENV JETTY_VERSION=9.2.24.v20180105
# Sat, 16 Jun 2018 08:16:38 GMT
ENV JETTY_TGZ_URL=https://repo1.maven.org/maven2/org/eclipse/jetty/jetty-distribution/9.2.24.v20180105/jetty-distribution-9.2.24.v20180105.tar.gz
# Sat, 16 Jun 2018 08:16:38 GMT
ENV JETTY_GPG_KEYS=AED5EE6C45D0FE8D5D1B164F27DED4BF6216DB8F 	2A684B57436A81FA8706B53C61C3351A438A3B7D 	5989BAF76217B843D66BE55B2D0E1FB8FE4B68B4 	B59B67FD7904984367F931800818D9D68FB67BAC 	BFBB21C246D7776836287A48A04E0C74ABB35FEA 	8B096546B1A8F02656B15D3B1677D141BCF3584D 	FBA2B18D238AB852DF95745C76157BDF03D0DCD6 	5C9579B3DB2E506429319AAEF33B071B29559E1E
# Sat, 16 Jun 2018 08:16:41 GMT
RUN set -xe 	&& curl -SL "$JETTY_TGZ_URL" -o jetty.tar.gz 	&& curl -SL "$JETTY_TGZ_URL.asc" -o jetty.tar.gz.asc 	&& export GNUPGHOME="$(mktemp -d)" 	&& for key in $JETTY_GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; done 	&& gpg --batch --verify jetty.tar.gz.asc jetty.tar.gz 	&& rm -rf "$GNUPGHOME" 	&& tar -xvf jetty.tar.gz --strip-components=1 	&& sed -i '/jetty-logging/d' etc/jetty.conf 	&& rm -fr demo-base javadoc 	&& rm jetty.tar.gz* 	&& rm -rf /tmp/hsperfdata_root
# Sat, 16 Jun 2018 08:16:41 GMT
ENV JETTY_BASE=/var/lib/jetty
# Sat, 16 Jun 2018 08:16:42 GMT
RUN mkdir -p "$JETTY_BASE"
# Sat, 16 Jun 2018 08:16:42 GMT
WORKDIR /var/lib/jetty
# Sat, 16 Jun 2018 08:16:43 GMT
RUN modules="$(grep -- ^--module= "$JETTY_HOME/start.ini" | cut -d= -f2 | paste -d, -s)" 	&& set -xe 	&& java -jar "$JETTY_HOME/start.jar" --add-to-startd="$modules" 	&& chown -R jetty:jetty "$JETTY_BASE" 	&& rm -rf /tmp/hsperfdata_root
# Sat, 16 Jun 2018 08:16:44 GMT
ENV TMPDIR=/tmp/jetty
# Sat, 16 Jun 2018 08:16:44 GMT
RUN set -xe 	&& mkdir -p "$TMPDIR" 	&& chown -R jetty:jetty "$TMPDIR"
# Sat, 16 Jun 2018 08:16:45 GMT
COPY multi:4510ce2f7fb9540fb389937165085b97c71d4b0659b22ddb7dfe601528a7461a in / 
# Sat, 16 Jun 2018 08:16:45 GMT
USER [jetty]
# Sat, 16 Jun 2018 08:16:45 GMT
EXPOSE 8080/tcp
# Sat, 16 Jun 2018 08:16:45 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Sat, 16 Jun 2018 08:16:46 GMT
CMD ["java" "-jar" "/usr/local/jetty/start.jar"]
```

-	Layers:
	-	`sha256:3d77ce4481b119f00e53bee9b4a443469c42c224db954ddaa2e6b74cd73cd5d0`  
		Last Modified: Sat, 28 Apr 2018 08:24:47 GMT  
		Size: 54.3 MB (54262566 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7d2f329349632fac6046432536420d15d630b68e7c536dcb28714fadb45a8a14`  
		Last Modified: Tue, 05 Jun 2018 23:37:57 GMT  
		Size: 17.6 MB (17584925 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:631f1f90ff9680f5886c8e2ffc03be2cbaaa112f8d8a6f459a04176b7e77539b`  
		Last Modified: Wed, 06 Jun 2018 02:20:12 GMT  
		Size: 795.4 KB (795374 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ab3169ba3d2d0611a242fb23e7fd6bc53d7fd6419728286fcafff259e59bb604`  
		Last Modified: Wed, 06 Jun 2018 02:20:11 GMT  
		Size: 249.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2337ad0f8d4cd572ac5751d68470c6a030b9688de6d493dfe7ae8d188abddbb9`  
		Last Modified: Wed, 06 Jun 2018 02:20:11 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:666e5e5c2b3efdf4f74cea103c7fa71dc906b5296a643447a03abbf30efe01ea`  
		Last Modified: Sat, 16 Jun 2018 07:37:46 GMT  
		Size: 82.3 MB (82282159 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ac5c8e9a11803e237b70a55a97222599440458978d8aaa6bc838c043a82980ec`  
		Last Modified: Sat, 16 Jun 2018 08:19:18 GMT  
		Size: 2.1 KB (2100 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7544cf14ca088124ecef40235ed733d25184973bd0e2ddb1d6c41d4b7aa7013a`  
		Last Modified: Sat, 16 Jun 2018 08:19:18 GMT  
		Size: 151.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cc816f22bd786c45c8a09df828162fa9d21d6fe1cc490e9108662221317d4266`  
		Last Modified: Sat, 16 Jun 2018 08:19:17 GMT  
		Size: 10.0 MB (10028803 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9383dae30d9349c2a56707f109f5b00c9c7dcd59f03cd493867fcd72b272b995`  
		Last Modified: Sat, 16 Jun 2018 08:19:16 GMT  
		Size: 139.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a8bc194c7004953fb157ac8f1f833dc606552287c399f1ad6c0328d1bb65977f`  
		Last Modified: Sat, 16 Jun 2018 08:19:16 GMT  
		Size: 1.5 KB (1469 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f4b45e5d355e7ca3bd6253c97518d7601cd2070c1367be73be11b8e9c3778ff3`  
		Last Modified: Sat, 16 Jun 2018 08:19:15 GMT  
		Size: 126.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:845dd6d7253cf2d9f356ff2fa5000b5f3fc532b4a23af425fd07263effc0a850`  
		Last Modified: Sat, 16 Jun 2018 08:19:16 GMT  
		Size: 1.4 KB (1389 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `jetty:9-jre7` - linux; arm variant v5

```console
$ docker pull jetty@sha256:10427ee4e23781358bb9507264828dbd009cad314469bd1628cc8545fd7a306c
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **152.3 MB (152325901 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:50bea9a79bd575ea1e98638dc3f89c6e78fd9373498d4ccf16a0da0649e06f64`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["java","-jar","\/usr\/local\/jetty\/start.jar"]`

```dockerfile
# Sat, 28 Apr 2018 08:49:23 GMT
ADD file:2d2cd360e66aeff5557c7e7117985a00d109278c3f456ee970afcc9a46483264 in / 
# Sat, 28 Apr 2018 08:49:23 GMT
CMD ["bash"]
# Sat, 05 May 2018 08:53:50 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 08:53:51 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Sat, 05 May 2018 09:35:57 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 09:35:58 GMT
ENV LANG=C.UTF-8
# Sat, 05 May 2018 09:35:58 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Sat, 05 May 2018 09:35:59 GMT
RUN ln -svT "/usr/lib/jvm/java-7-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Sat, 05 May 2018 09:36:00 GMT
ENV JAVA_HOME=/docker-java-home/jre
# Tue, 12 Jun 2018 09:03:17 GMT
ENV JAVA_VERSION=7u181
# Tue, 12 Jun 2018 09:03:17 GMT
ENV JAVA_DEBIAN_VERSION=7u181-2.6.14-1~deb8u1
# Tue, 12 Jun 2018 09:04:13 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-7-jre="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Tue, 12 Jun 2018 09:28:31 GMT
RUN groupadd -r jetty && useradd -r -g jetty jetty
# Tue, 12 Jun 2018 09:28:31 GMT
ENV JETTY_HOME=/usr/local/jetty
# Tue, 12 Jun 2018 09:28:31 GMT
ENV PATH=/usr/local/jetty/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Tue, 12 Jun 2018 09:28:32 GMT
RUN mkdir -p "$JETTY_HOME"
# Tue, 12 Jun 2018 09:28:32 GMT
WORKDIR /usr/local/jetty
# Tue, 12 Jun 2018 09:28:33 GMT
ENV JETTY_VERSION=9.2.24.v20180105
# Tue, 12 Jun 2018 09:28:33 GMT
ENV JETTY_TGZ_URL=https://repo1.maven.org/maven2/org/eclipse/jetty/jetty-distribution/9.2.24.v20180105/jetty-distribution-9.2.24.v20180105.tar.gz
# Tue, 12 Jun 2018 09:28:33 GMT
ENV JETTY_GPG_KEYS=AED5EE6C45D0FE8D5D1B164F27DED4BF6216DB8F 	2A684B57436A81FA8706B53C61C3351A438A3B7D 	5989BAF76217B843D66BE55B2D0E1FB8FE4B68B4 	B59B67FD7904984367F931800818D9D68FB67BAC 	BFBB21C246D7776836287A48A04E0C74ABB35FEA 	8B096546B1A8F02656B15D3B1677D141BCF3584D 	FBA2B18D238AB852DF95745C76157BDF03D0DCD6 	5C9579B3DB2E506429319AAEF33B071B29559E1E
# Tue, 12 Jun 2018 09:28:36 GMT
RUN set -xe 	&& curl -SL "$JETTY_TGZ_URL" -o jetty.tar.gz 	&& curl -SL "$JETTY_TGZ_URL.asc" -o jetty.tar.gz.asc 	&& export GNUPGHOME="$(mktemp -d)" 	&& for key in $JETTY_GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; done 	&& gpg --batch --verify jetty.tar.gz.asc jetty.tar.gz 	&& rm -rf "$GNUPGHOME" 	&& tar -xvf jetty.tar.gz --strip-components=1 	&& sed -i '/jetty-logging/d' etc/jetty.conf 	&& rm -fr demo-base javadoc 	&& rm jetty.tar.gz* 	&& rm -rf /tmp/hsperfdata_root
# Tue, 12 Jun 2018 09:28:36 GMT
ENV JETTY_BASE=/var/lib/jetty
# Tue, 12 Jun 2018 09:28:37 GMT
RUN mkdir -p "$JETTY_BASE"
# Tue, 12 Jun 2018 09:28:37 GMT
WORKDIR /var/lib/jetty
# Tue, 12 Jun 2018 09:28:40 GMT
RUN modules="$(grep -- ^--module= "$JETTY_HOME/start.ini" | cut -d= -f2 | paste -d, -s)" 	&& set -xe 	&& java -jar "$JETTY_HOME/start.jar" --add-to-startd="$modules" 	&& chown -R jetty:jetty "$JETTY_BASE" 	&& rm -rf /tmp/hsperfdata_root
# Tue, 12 Jun 2018 09:28:40 GMT
ENV TMPDIR=/tmp/jetty
# Tue, 12 Jun 2018 09:28:41 GMT
RUN set -xe 	&& mkdir -p "$TMPDIR" 	&& chown -R jetty:jetty "$TMPDIR"
# Tue, 12 Jun 2018 09:28:41 GMT
COPY multi:4510ce2f7fb9540fb389937165085b97c71d4b0659b22ddb7dfe601528a7461a in / 
# Tue, 12 Jun 2018 09:28:42 GMT
USER [jetty]
# Tue, 12 Jun 2018 09:28:42 GMT
EXPOSE 8080/tcp
# Tue, 12 Jun 2018 09:28:42 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Tue, 12 Jun 2018 09:28:42 GMT
CMD ["java" "-jar" "/usr/local/jetty/start.jar"]
```

-	Layers:
	-	`sha256:81fc0826192f72abe617753d378af4047dbce89faf17cdab9166877006a25d8e`  
		Last Modified: Sat, 28 Apr 2018 08:57:10 GMT  
		Size: 52.5 MB (52456037 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ceea42ca1c50a28c4602df4c2da5d4a49162eeeb7bd7c9b9bd9593f4ae0ccbc8`  
		Last Modified: Sat, 05 May 2018 09:09:51 GMT  
		Size: 17.1 MB (17084448 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:64a66ea1754bee5106ca283a42342ae8d4c979c243c5d3bf3479ff0f70da2811`  
		Last Modified: Sat, 05 May 2018 10:02:46 GMT  
		Size: 788.1 KB (788105 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:01d6c139fa427247de53422a1b0aeb2e8c054026f113523a3d78dd75783f262c`  
		Last Modified: Sat, 05 May 2018 10:02:46 GMT  
		Size: 248.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:984619550ec48c1ca7f0056e409f5a55748b9bfd97f81b838e26c1958ab14ff2`  
		Last Modified: Sat, 05 May 2018 10:02:46 GMT  
		Size: 130.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f03bcd8dbbfc64a07fd3c95a3823e9a5d53f18ee85f572ea4dadf4ed8c91d654`  
		Last Modified: Tue, 12 Jun 2018 09:12:26 GMT  
		Size: 72.0 MB (71962399 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cc175d4bba4eb3eac5dc77ee5cad32e4f0e6a2b1074c34f88837b6f472632432`  
		Last Modified: Tue, 12 Jun 2018 09:28:59 GMT  
		Size: 2.1 KB (2090 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c6fd8bfae634579e66d062a73aa739921d34f27a02dae3d8c0fdf404d6fd7d11`  
		Last Modified: Tue, 12 Jun 2018 09:28:59 GMT  
		Size: 182.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ec74cae7c0a056795ca3074ea6dcf174ceb65464d0c253cb63a8625492bfd35e`  
		Last Modified: Tue, 12 Jun 2018 09:29:00 GMT  
		Size: 10.0 MB (10029007 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:364ab590f474a3c870a4168c26dff4be1836cf414e3327bced243f44fb2a7ef0`  
		Last Modified: Tue, 12 Jun 2018 09:29:00 GMT  
		Size: 171.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1a6ad7d418df03a5b801c4f4b1a0575c59218b365b9b14a8fb6042a870643a04`  
		Last Modified: Tue, 12 Jun 2018 09:28:58 GMT  
		Size: 1.5 KB (1541 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2cb482f1d6db52430200ee8514a3ae992587c5a2e14bd66b03960b59c9c64fd6`  
		Last Modified: Tue, 12 Jun 2018 09:28:58 GMT  
		Size: 155.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0038f65a614e1d36d6ceba30baf6a0698168a3c792adfc7bf01170cd0c398350`  
		Last Modified: Tue, 12 Jun 2018 09:28:58 GMT  
		Size: 1.4 KB (1388 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `jetty:9-jre7` - linux; arm variant v7

```console
$ docker pull jetty@sha256:476aaf0581d026cb7f264a6d70be584e10f2c0e8605b79779130e3f7b200b428
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **148.3 MB (148258336 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:ac00427edfec97b5f744a138c3d985a109ebcd752ad81f05395e9da75fe75c44`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["java","-jar","\/usr\/local\/jetty\/start.jar"]`

```dockerfile
# Sat, 28 Apr 2018 11:59:05 GMT
ADD file:4e9c283075c120ce66f83bf541b0aeaa8a46f74c21d38e4ab1578e7f1b892823 in / 
# Sat, 28 Apr 2018 11:59:05 GMT
CMD ["bash"]
# Sat, 05 May 2018 12:07:15 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 12:07:16 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Sat, 05 May 2018 13:05:37 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 13:05:38 GMT
ENV LANG=C.UTF-8
# Sat, 05 May 2018 13:05:39 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Sat, 05 May 2018 13:05:40 GMT
RUN ln -svT "/usr/lib/jvm/java-7-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Sat, 05 May 2018 13:05:40 GMT
ENV JAVA_HOME=/docker-java-home/jre
# Tue, 12 Jun 2018 12:10:54 GMT
ENV JAVA_VERSION=7u181
# Tue, 12 Jun 2018 12:10:55 GMT
ENV JAVA_DEBIAN_VERSION=7u181-2.6.14-1~deb8u1
# Tue, 12 Jun 2018 12:11:54 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-7-jre="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Tue, 12 Jun 2018 12:40:35 GMT
RUN groupadd -r jetty && useradd -r -g jetty jetty
# Tue, 12 Jun 2018 12:40:35 GMT
ENV JETTY_HOME=/usr/local/jetty
# Tue, 12 Jun 2018 12:40:35 GMT
ENV PATH=/usr/local/jetty/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Tue, 12 Jun 2018 12:40:36 GMT
RUN mkdir -p "$JETTY_HOME"
# Tue, 12 Jun 2018 12:40:37 GMT
WORKDIR /usr/local/jetty
# Tue, 12 Jun 2018 12:40:37 GMT
ENV JETTY_VERSION=9.2.24.v20180105
# Tue, 12 Jun 2018 12:40:37 GMT
ENV JETTY_TGZ_URL=https://repo1.maven.org/maven2/org/eclipse/jetty/jetty-distribution/9.2.24.v20180105/jetty-distribution-9.2.24.v20180105.tar.gz
# Tue, 12 Jun 2018 12:40:37 GMT
ENV JETTY_GPG_KEYS=AED5EE6C45D0FE8D5D1B164F27DED4BF6216DB8F 	2A684B57436A81FA8706B53C61C3351A438A3B7D 	5989BAF76217B843D66BE55B2D0E1FB8FE4B68B4 	B59B67FD7904984367F931800818D9D68FB67BAC 	BFBB21C246D7776836287A48A04E0C74ABB35FEA 	8B096546B1A8F02656B15D3B1677D141BCF3584D 	FBA2B18D238AB852DF95745C76157BDF03D0DCD6 	5C9579B3DB2E506429319AAEF33B071B29559E1E
# Tue, 12 Jun 2018 12:40:40 GMT
RUN set -xe 	&& curl -SL "$JETTY_TGZ_URL" -o jetty.tar.gz 	&& curl -SL "$JETTY_TGZ_URL.asc" -o jetty.tar.gz.asc 	&& export GNUPGHOME="$(mktemp -d)" 	&& for key in $JETTY_GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; done 	&& gpg --batch --verify jetty.tar.gz.asc jetty.tar.gz 	&& rm -rf "$GNUPGHOME" 	&& tar -xvf jetty.tar.gz --strip-components=1 	&& sed -i '/jetty-logging/d' etc/jetty.conf 	&& rm -fr demo-base javadoc 	&& rm jetty.tar.gz* 	&& rm -rf /tmp/hsperfdata_root
# Tue, 12 Jun 2018 12:40:40 GMT
ENV JETTY_BASE=/var/lib/jetty
# Tue, 12 Jun 2018 12:40:41 GMT
RUN mkdir -p "$JETTY_BASE"
# Tue, 12 Jun 2018 12:40:41 GMT
WORKDIR /var/lib/jetty
# Tue, 12 Jun 2018 12:40:44 GMT
RUN modules="$(grep -- ^--module= "$JETTY_HOME/start.ini" | cut -d= -f2 | paste -d, -s)" 	&& set -xe 	&& java -jar "$JETTY_HOME/start.jar" --add-to-startd="$modules" 	&& chown -R jetty:jetty "$JETTY_BASE" 	&& rm -rf /tmp/hsperfdata_root
# Tue, 12 Jun 2018 12:40:44 GMT
ENV TMPDIR=/tmp/jetty
# Tue, 12 Jun 2018 12:40:45 GMT
RUN set -xe 	&& mkdir -p "$TMPDIR" 	&& chown -R jetty:jetty "$TMPDIR"
# Tue, 12 Jun 2018 12:40:45 GMT
COPY multi:4510ce2f7fb9540fb389937165085b97c71d4b0659b22ddb7dfe601528a7461a in / 
# Tue, 12 Jun 2018 12:40:45 GMT
USER [jetty]
# Tue, 12 Jun 2018 12:40:46 GMT
EXPOSE 8080/tcp
# Tue, 12 Jun 2018 12:40:46 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Tue, 12 Jun 2018 12:40:46 GMT
CMD ["java" "-jar" "/usr/local/jetty/start.jar"]
```

-	Layers:
	-	`sha256:5c478157e28e3c26a0209484edb518799e1c21863d4700579c010b7203e0537f`  
		Last Modified: Sat, 28 Apr 2018 12:10:24 GMT  
		Size: 50.2 MB (50195697 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ec0195f0b71282f9e483da45354cbd4936eb181ab7c78e1b2d06e1a66dfc9314`  
		Last Modified: Sat, 05 May 2018 12:31:38 GMT  
		Size: 16.8 MB (16762537 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:01a752ba200b146188d9aa01696172fdb19550fbbd96898b1cfcd8b6cae83294`  
		Last Modified: Sat, 05 May 2018 13:33:17 GMT  
		Size: 762.7 KB (762721 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6a9c245d978efa7ef2f3262152633e25df59645bb569b0c15b8fca600c4a53cc`  
		Last Modified: Sat, 05 May 2018 13:33:16 GMT  
		Size: 248.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b5915cf16dbfadc7df80208fd30cd4ed6929fb6b93590b4c6f273ee1f8060ace`  
		Last Modified: Sat, 05 May 2018 13:33:15 GMT  
		Size: 130.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:74fed1b6d52af7f21a56f3de2da7052d763b21ac0a7d6797e387e38f7d32556a`  
		Last Modified: Tue, 12 Jun 2018 12:20:21 GMT  
		Size: 70.5 MB (70502480 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:62348913c7597cdd718f823ffad6252d1cbd37606d650fb78a46df0ea171e621`  
		Last Modified: Tue, 12 Jun 2018 12:41:00 GMT  
		Size: 2.1 KB (2086 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ad767b5ce2fb549738f62ec55c2ade16ec95fca58600fa31b59d26c4f8d80fca`  
		Last Modified: Tue, 12 Jun 2018 12:41:01 GMT  
		Size: 183.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8223ae8c91cd5792f4b24ba029cbf16cef46f6b0def8527a909165084b34d644`  
		Last Modified: Tue, 12 Jun 2018 12:41:01 GMT  
		Size: 10.0 MB (10028998 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8f10fbdc1128968d85ee89a523b58a8975cd795bbc541e4b7a1175f0cec16737`  
		Last Modified: Tue, 12 Jun 2018 12:40:59 GMT  
		Size: 171.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:999351642d825d84a424fc226b71a4a4477418f61cbc6deb0c342a333348445e`  
		Last Modified: Tue, 12 Jun 2018 12:41:00 GMT  
		Size: 1.5 KB (1540 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7528bced4369b01991a8f8c2be260b28aff7ccdbbef536e2ec90f522001a53c6`  
		Last Modified: Tue, 12 Jun 2018 12:40:59 GMT  
		Size: 156.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:351a8d3e26eaf1b6a5ba06ffeee00c04ef2280f1fe5d59ed46003497bf2b6e79`  
		Last Modified: Tue, 12 Jun 2018 12:41:01 GMT  
		Size: 1.4 KB (1389 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `jetty:9-jre7` - linux; arm64 variant v8

```console
$ docker pull jetty@sha256:0ce6f61e746ffa59918690c306aaa140ce936524870bd6ae8c307ea46521f5da
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **152.3 MB (152321338 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:0698d680572236f603eb2a774e95ac17668e9747406df8335448d31764999566`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["java","-jar","\/usr\/local\/jetty\/start.jar"]`

```dockerfile
# Mon, 30 Apr 2018 23:21:38 GMT
ADD file:387c83918422a6546379c4d84818ca3949fcd63aec058da562b08c947a9ed571 in / 
# Mon, 30 Apr 2018 23:21:40 GMT
CMD ["bash"]
# Sat, 05 May 2018 09:16:46 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 09:16:48 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Sat, 05 May 2018 12:23:13 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 12:23:13 GMT
ENV LANG=C.UTF-8
# Sat, 05 May 2018 12:23:16 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Sat, 05 May 2018 12:23:19 GMT
RUN ln -svT "/usr/lib/jvm/java-7-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Sat, 05 May 2018 12:23:19 GMT
ENV JAVA_HOME=/docker-java-home/jre
# Tue, 12 Jun 2018 09:27:47 GMT
ENV JAVA_VERSION=7u181
# Tue, 12 Jun 2018 09:27:48 GMT
ENV JAVA_DEBIAN_VERSION=7u181-2.6.14-1~deb8u1
# Tue, 12 Jun 2018 09:33:22 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-7-jre="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Tue, 12 Jun 2018 10:23:09 GMT
RUN groupadd -r jetty && useradd -r -g jetty jetty
# Tue, 12 Jun 2018 10:23:10 GMT
ENV JETTY_HOME=/usr/local/jetty
# Tue, 12 Jun 2018 10:23:11 GMT
ENV PATH=/usr/local/jetty/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Tue, 12 Jun 2018 10:23:14 GMT
RUN mkdir -p "$JETTY_HOME"
# Tue, 12 Jun 2018 10:23:15 GMT
WORKDIR /usr/local/jetty
# Tue, 12 Jun 2018 10:23:16 GMT
ENV JETTY_VERSION=9.2.24.v20180105
# Tue, 12 Jun 2018 10:23:17 GMT
ENV JETTY_TGZ_URL=https://repo1.maven.org/maven2/org/eclipse/jetty/jetty-distribution/9.2.24.v20180105/jetty-distribution-9.2.24.v20180105.tar.gz
# Tue, 12 Jun 2018 10:23:18 GMT
ENV JETTY_GPG_KEYS=AED5EE6C45D0FE8D5D1B164F27DED4BF6216DB8F 	2A684B57436A81FA8706B53C61C3351A438A3B7D 	5989BAF76217B843D66BE55B2D0E1FB8FE4B68B4 	B59B67FD7904984367F931800818D9D68FB67BAC 	BFBB21C246D7776836287A48A04E0C74ABB35FEA 	8B096546B1A8F02656B15D3B1677D141BCF3584D 	FBA2B18D238AB852DF95745C76157BDF03D0DCD6 	5C9579B3DB2E506429319AAEF33B071B29559E1E
# Tue, 12 Jun 2018 10:23:26 GMT
RUN set -xe 	&& curl -SL "$JETTY_TGZ_URL" -o jetty.tar.gz 	&& curl -SL "$JETTY_TGZ_URL.asc" -o jetty.tar.gz.asc 	&& export GNUPGHOME="$(mktemp -d)" 	&& for key in $JETTY_GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; done 	&& gpg --batch --verify jetty.tar.gz.asc jetty.tar.gz 	&& rm -rf "$GNUPGHOME" 	&& tar -xvf jetty.tar.gz --strip-components=1 	&& sed -i '/jetty-logging/d' etc/jetty.conf 	&& rm -fr demo-base javadoc 	&& rm jetty.tar.gz* 	&& rm -rf /tmp/hsperfdata_root
# Tue, 12 Jun 2018 10:23:27 GMT
ENV JETTY_BASE=/var/lib/jetty
# Tue, 12 Jun 2018 10:23:30 GMT
RUN mkdir -p "$JETTY_BASE"
# Tue, 12 Jun 2018 10:23:31 GMT
WORKDIR /var/lib/jetty
# Tue, 12 Jun 2018 10:23:35 GMT
RUN modules="$(grep -- ^--module= "$JETTY_HOME/start.ini" | cut -d= -f2 | paste -d, -s)" 	&& set -xe 	&& java -jar "$JETTY_HOME/start.jar" --add-to-startd="$modules" 	&& chown -R jetty:jetty "$JETTY_BASE" 	&& rm -rf /tmp/hsperfdata_root
# Tue, 12 Jun 2018 10:23:36 GMT
ENV TMPDIR=/tmp/jetty
# Tue, 12 Jun 2018 10:23:38 GMT
RUN set -xe 	&& mkdir -p "$TMPDIR" 	&& chown -R jetty:jetty "$TMPDIR"
# Tue, 12 Jun 2018 10:23:40 GMT
COPY multi:4510ce2f7fb9540fb389937165085b97c71d4b0659b22ddb7dfe601528a7461a in / 
# Tue, 12 Jun 2018 10:23:41 GMT
USER [jetty]
# Tue, 12 Jun 2018 10:23:42 GMT
EXPOSE 8080/tcp
# Tue, 12 Jun 2018 10:23:43 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Tue, 12 Jun 2018 10:23:44 GMT
CMD ["java" "-jar" "/usr/local/jetty/start.jar"]
```

-	Layers:
	-	`sha256:363cfded2ef3921ef972c85cafc77cf16cdcfddfd49782ad4540cb73fd5e57a2`  
		Last Modified: Mon, 30 Apr 2018 23:41:06 GMT  
		Size: 51.4 MB (51446854 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4bc4956efcaf7d30060a373d34961e3c6e71ee0317cb5381a180230a397c5442`  
		Last Modified: Sat, 05 May 2018 09:43:52 GMT  
		Size: 17.2 MB (17213842 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7f5a7eee17f6bef9ce5302547df05502e21dcac9b6267c7278c219ee2c708b37`  
		Last Modified: Sat, 05 May 2018 13:08:41 GMT  
		Size: 789.2 KB (789162 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e6ce7463a7e9eae4cc97131c58d9692029eef5b8f004c62ed65742a00c70773e`  
		Last Modified: Sat, 05 May 2018 13:08:39 GMT  
		Size: 248.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1882b9550551affc5f6b6d20713252201f4d2633d8be9a4763e11fcb60f99f1a`  
		Last Modified: Sat, 05 May 2018 13:08:40 GMT  
		Size: 130.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:67cca9fb180900266ac32872326adbd48d14c1186f2b2571fdfc703a65cd865a`  
		Last Modified: Tue, 12 Jun 2018 09:48:52 GMT  
		Size: 72.8 MB (72836916 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:23e79b899b84a8ac261126b52391fba36a37fca59bb6bc1015c6f2a901b2efe5`  
		Last Modified: Tue, 12 Jun 2018 10:24:26 GMT  
		Size: 2.1 KB (2104 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d9b381842fd30bdc8d3a546a0144a5567bfa9837103bfa7b0863992c5f7d31a6`  
		Last Modified: Tue, 12 Jun 2018 10:24:25 GMT  
		Size: 152.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:99603c4a3cf02055d0ed6daf528dce00fde2e03a6947348e6098d40b88f5874c`  
		Last Modified: Tue, 12 Jun 2018 10:24:25 GMT  
		Size: 10.0 MB (10028810 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:503f4276ebed5d8f7ea94dad2cbe6d99d192a9d7df03b56a6175f541ae01c7ae`  
		Last Modified: Tue, 12 Jun 2018 10:24:23 GMT  
		Size: 139.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:87edab31aa285a97e6468cd0d6d11adca2a8a84bde7ffdee0ffa8504c171941f`  
		Last Modified: Tue, 12 Jun 2018 10:24:22 GMT  
		Size: 1.5 KB (1468 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:63b51a4796e84f95331ef8796d20dc1188a131a6c19481275b607f9a28c62f43`  
		Last Modified: Tue, 12 Jun 2018 10:24:23 GMT  
		Size: 126.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:85ab30f0201e4c91482ff66ef2971a9e56c4bef1b60053b292fa7227579c1f7d`  
		Last Modified: Tue, 12 Jun 2018 10:24:22 GMT  
		Size: 1.4 KB (1387 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `jetty:9-jre7` - linux; 386

```console
$ docker pull jetty@sha256:767cb91c8b382a2e6e16c606570dc8acd80a7c5b610dd34ffbbc9eee64f7f32a
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **177.3 MB (177328350 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:5c1e90a60cc5837552aa11202e517ae76045a62d9537743cc58a5e8b7c1cb261`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["java","-jar","\/usr\/local\/jetty\/start.jar"]`

```dockerfile
# Sat, 28 Apr 2018 10:39:32 GMT
ADD file:ce5174f2b2c155a2421fac3ff37a02d9551d5d79e31a541189bcfd2416a6903a in / 
# Sat, 28 Apr 2018 10:39:32 GMT
CMD ["bash"]
# Wed, 06 Jun 2018 11:33:01 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Wed, 06 Jun 2018 11:33:02 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Wed, 06 Jun 2018 13:30:21 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Wed, 06 Jun 2018 13:30:21 GMT
ENV LANG=C.UTF-8
# Wed, 06 Jun 2018 13:30:22 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Wed, 06 Jun 2018 13:30:23 GMT
RUN ln -svT "/usr/lib/jvm/java-7-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Wed, 06 Jun 2018 13:30:23 GMT
ENV JAVA_HOME=/docker-java-home/jre
# Tue, 12 Jun 2018 10:56:23 GMT
ENV JAVA_VERSION=7u181
# Tue, 12 Jun 2018 10:56:23 GMT
ENV JAVA_DEBIAN_VERSION=7u181-2.6.14-1~deb8u1
# Tue, 12 Jun 2018 10:58:03 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-7-jre="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Tue, 12 Jun 2018 11:31:13 GMT
RUN groupadd -r jetty && useradd -r -g jetty jetty
# Tue, 12 Jun 2018 11:31:13 GMT
ENV JETTY_HOME=/usr/local/jetty
# Tue, 12 Jun 2018 11:31:14 GMT
ENV PATH=/usr/local/jetty/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Tue, 12 Jun 2018 11:31:19 GMT
RUN mkdir -p "$JETTY_HOME"
# Tue, 12 Jun 2018 11:31:20 GMT
WORKDIR /usr/local/jetty
# Tue, 12 Jun 2018 11:31:20 GMT
ENV JETTY_VERSION=9.2.24.v20180105
# Tue, 12 Jun 2018 11:31:20 GMT
ENV JETTY_TGZ_URL=https://repo1.maven.org/maven2/org/eclipse/jetty/jetty-distribution/9.2.24.v20180105/jetty-distribution-9.2.24.v20180105.tar.gz
# Tue, 12 Jun 2018 11:31:20 GMT
ENV JETTY_GPG_KEYS=AED5EE6C45D0FE8D5D1B164F27DED4BF6216DB8F 	2A684B57436A81FA8706B53C61C3351A438A3B7D 	5989BAF76217B843D66BE55B2D0E1FB8FE4B68B4 	B59B67FD7904984367F931800818D9D68FB67BAC 	BFBB21C246D7776836287A48A04E0C74ABB35FEA 	8B096546B1A8F02656B15D3B1677D141BCF3584D 	FBA2B18D238AB852DF95745C76157BDF03D0DCD6 	5C9579B3DB2E506429319AAEF33B071B29559E1E
# Tue, 12 Jun 2018 11:31:25 GMT
RUN set -xe 	&& curl -SL "$JETTY_TGZ_URL" -o jetty.tar.gz 	&& curl -SL "$JETTY_TGZ_URL.asc" -o jetty.tar.gz.asc 	&& export GNUPGHOME="$(mktemp -d)" 	&& for key in $JETTY_GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; done 	&& gpg --batch --verify jetty.tar.gz.asc jetty.tar.gz 	&& rm -rf "$GNUPGHOME" 	&& tar -xvf jetty.tar.gz --strip-components=1 	&& sed -i '/jetty-logging/d' etc/jetty.conf 	&& rm -fr demo-base javadoc 	&& rm jetty.tar.gz* 	&& rm -rf /tmp/hsperfdata_root
# Tue, 12 Jun 2018 11:31:25 GMT
ENV JETTY_BASE=/var/lib/jetty
# Tue, 12 Jun 2018 11:31:26 GMT
RUN mkdir -p "$JETTY_BASE"
# Tue, 12 Jun 2018 11:31:31 GMT
WORKDIR /var/lib/jetty
# Tue, 12 Jun 2018 11:31:32 GMT
RUN modules="$(grep -- ^--module= "$JETTY_HOME/start.ini" | cut -d= -f2 | paste -d, -s)" 	&& set -xe 	&& java -jar "$JETTY_HOME/start.jar" --add-to-startd="$modules" 	&& chown -R jetty:jetty "$JETTY_BASE" 	&& rm -rf /tmp/hsperfdata_root
# Tue, 12 Jun 2018 11:31:33 GMT
ENV TMPDIR=/tmp/jetty
# Tue, 12 Jun 2018 11:31:33 GMT
RUN set -xe 	&& mkdir -p "$TMPDIR" 	&& chown -R jetty:jetty "$TMPDIR"
# Tue, 12 Jun 2018 11:31:34 GMT
COPY multi:4510ce2f7fb9540fb389937165085b97c71d4b0659b22ddb7dfe601528a7461a in / 
# Tue, 12 Jun 2018 11:31:34 GMT
USER [jetty]
# Tue, 12 Jun 2018 11:31:34 GMT
EXPOSE 8080/tcp
# Tue, 12 Jun 2018 11:31:35 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Tue, 12 Jun 2018 11:31:35 GMT
CMD ["java" "-jar" "/usr/local/jetty/start.jar"]
```

-	Layers:
	-	`sha256:05b419d667f793c8c2edf0ff0aec14fc4d66733cdb89957ac89e8bfbeaddd0fa`  
		Last Modified: Sat, 28 Apr 2018 10:44:20 GMT  
		Size: 54.5 MB (54486782 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9ea56a1d0660db2d98662e1123cf4c76981e83fc15a761aae4015085b0d051d7`  
		Last Modified: Wed, 06 Jun 2018 12:12:39 GMT  
		Size: 19.9 MB (19880810 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:66c0d3a4f85b5fd090d0d6affff15606440e71d0811c9d82376bb748f9530022`  
		Last Modified: Wed, 06 Jun 2018 13:58:20 GMT  
		Size: 798.3 KB (798332 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a37e79ab5eaced1035c504dd89f71a511f3e53c293ee01c17c2e394d3fd0e6f2`  
		Last Modified: Wed, 06 Jun 2018 13:58:19 GMT  
		Size: 249.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:36d633cbaedd8e78bac9e9c2c0a64056decfe8f3d373a0dc3b113f4db52ab7e4`  
		Last Modified: Wed, 06 Jun 2018 13:58:18 GMT  
		Size: 130.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1cb2fbbba6b50ba5cf4fcc5b04eda5f3fabef28e498e1cf699b00d6616de69f8`  
		Last Modified: Tue, 12 Jun 2018 11:14:09 GMT  
		Size: 92.1 MB (92127867 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1ab32acb981c82deb35244159416cd997a6eee7050d17760de2a224a56b3b08b`  
		Last Modified: Tue, 12 Jun 2018 11:31:59 GMT  
		Size: 2.1 KB (2087 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:763690bd527fb5d596d4e23d31712a55b2fa7a793bb37dc98da4e7eed9a4d330`  
		Last Modified: Tue, 12 Jun 2018 11:32:00 GMT  
		Size: 152.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0a02d0f618bd7627aa387d81eebd8758aba0f19aeb5e55efb89e97b7719d5633`  
		Last Modified: Tue, 12 Jun 2018 11:31:58 GMT  
		Size: 10.0 MB (10028822 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:aefe1613c28c3ab7cffb8de21fa2970ea04360aa71e3d0f909c33f0236d58b30`  
		Last Modified: Tue, 12 Jun 2018 11:31:57 GMT  
		Size: 139.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:879313984edc1873ea2b2b7e8b03dcd64ddd4f3779517417c76bce4dc8870ce9`  
		Last Modified: Tue, 12 Jun 2018 11:31:56 GMT  
		Size: 1.5 KB (1469 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:aa31cfb11f062bf9c5e793298ed10c7e9414cc6e57e4e12c3e409d92fa849a0b`  
		Last Modified: Tue, 12 Jun 2018 11:31:57 GMT  
		Size: 126.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:88c71b7adee89dc625213a1853a5988e82713a2424a256856d4de948b6a7b416`  
		Last Modified: Tue, 12 Jun 2018 11:31:56 GMT  
		Size: 1.4 KB (1385 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `jetty:9-jre7` - linux; ppc64le

```console
$ docker pull jetty@sha256:607f293088b9595eb6d0d481808c75e31c91a01c37eb8e5b79b529603e263385
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **155.8 MB (155753393 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:ecc5781befa56e4b68025d5c6c68ab9a6e3bc6ca5a046b21fcde138cc95f9d81`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["java","-jar","\/usr\/local\/jetty\/start.jar"]`

```dockerfile
# Sat, 28 Apr 2018 08:17:46 GMT
ADD file:6a4bd4ea54f669286e984ecf8178e1fa7c12c8b6fc0f96e4203ae7a6f99a2279 in / 
# Sat, 28 Apr 2018 08:17:47 GMT
CMD ["bash"]
# Sat, 05 May 2018 08:58:24 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 08:58:32 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Sat, 05 May 2018 14:40:49 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 14:40:50 GMT
ENV LANG=C.UTF-8
# Sat, 05 May 2018 14:40:52 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Sat, 05 May 2018 14:40:54 GMT
RUN ln -svT "/usr/lib/jvm/java-7-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Sat, 05 May 2018 14:40:55 GMT
ENV JAVA_HOME=/docker-java-home/jre
# Tue, 12 Jun 2018 08:54:35 GMT
ENV JAVA_VERSION=7u181
# Tue, 12 Jun 2018 08:54:38 GMT
ENV JAVA_DEBIAN_VERSION=7u181-2.6.14-1~deb8u1
# Tue, 12 Jun 2018 09:00:07 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-7-jre="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Tue, 12 Jun 2018 09:45:07 GMT
RUN groupadd -r jetty && useradd -r -g jetty jetty
# Tue, 12 Jun 2018 09:45:09 GMT
ENV JETTY_HOME=/usr/local/jetty
# Tue, 12 Jun 2018 09:45:10 GMT
ENV PATH=/usr/local/jetty/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Tue, 12 Jun 2018 09:45:13 GMT
RUN mkdir -p "$JETTY_HOME"
# Tue, 12 Jun 2018 09:45:14 GMT
WORKDIR /usr/local/jetty
# Tue, 12 Jun 2018 09:45:16 GMT
ENV JETTY_VERSION=9.2.24.v20180105
# Tue, 12 Jun 2018 09:45:18 GMT
ENV JETTY_TGZ_URL=https://repo1.maven.org/maven2/org/eclipse/jetty/jetty-distribution/9.2.24.v20180105/jetty-distribution-9.2.24.v20180105.tar.gz
# Tue, 12 Jun 2018 09:45:19 GMT
ENV JETTY_GPG_KEYS=AED5EE6C45D0FE8D5D1B164F27DED4BF6216DB8F 	2A684B57436A81FA8706B53C61C3351A438A3B7D 	5989BAF76217B843D66BE55B2D0E1FB8FE4B68B4 	B59B67FD7904984367F931800818D9D68FB67BAC 	BFBB21C246D7776836287A48A04E0C74ABB35FEA 	8B096546B1A8F02656B15D3B1677D141BCF3584D 	FBA2B18D238AB852DF95745C76157BDF03D0DCD6 	5C9579B3DB2E506429319AAEF33B071B29559E1E
# Tue, 12 Jun 2018 09:45:25 GMT
RUN set -xe 	&& curl -SL "$JETTY_TGZ_URL" -o jetty.tar.gz 	&& curl -SL "$JETTY_TGZ_URL.asc" -o jetty.tar.gz.asc 	&& export GNUPGHOME="$(mktemp -d)" 	&& for key in $JETTY_GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; done 	&& gpg --batch --verify jetty.tar.gz.asc jetty.tar.gz 	&& rm -rf "$GNUPGHOME" 	&& tar -xvf jetty.tar.gz --strip-components=1 	&& sed -i '/jetty-logging/d' etc/jetty.conf 	&& rm -fr demo-base javadoc 	&& rm jetty.tar.gz* 	&& rm -rf /tmp/hsperfdata_root
# Tue, 12 Jun 2018 09:45:26 GMT
ENV JETTY_BASE=/var/lib/jetty
# Tue, 12 Jun 2018 09:45:28 GMT
RUN mkdir -p "$JETTY_BASE"
# Tue, 12 Jun 2018 09:45:28 GMT
WORKDIR /var/lib/jetty
# Tue, 12 Jun 2018 09:45:32 GMT
RUN modules="$(grep -- ^--module= "$JETTY_HOME/start.ini" | cut -d= -f2 | paste -d, -s)" 	&& set -xe 	&& java -jar "$JETTY_HOME/start.jar" --add-to-startd="$modules" 	&& chown -R jetty:jetty "$JETTY_BASE" 	&& rm -rf /tmp/hsperfdata_root
# Tue, 12 Jun 2018 09:45:33 GMT
ENV TMPDIR=/tmp/jetty
# Tue, 12 Jun 2018 09:45:35 GMT
RUN set -xe 	&& mkdir -p "$TMPDIR" 	&& chown -R jetty:jetty "$TMPDIR"
# Tue, 12 Jun 2018 09:45:35 GMT
COPY multi:4510ce2f7fb9540fb389937165085b97c71d4b0659b22ddb7dfe601528a7461a in / 
# Tue, 12 Jun 2018 09:45:37 GMT
USER [jetty]
# Tue, 12 Jun 2018 09:45:37 GMT
EXPOSE 8080/tcp
# Tue, 12 Jun 2018 09:45:38 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Tue, 12 Jun 2018 09:45:38 GMT
CMD ["java" "-jar" "/usr/local/jetty/start.jar"]
```

-	Layers:
	-	`sha256:2668401c9f940b1d6b03e5f0086fa248cb957610ef9a7c79983d2fb0707ec76c`  
		Last Modified: Sat, 28 Apr 2018 08:24:36 GMT  
		Size: 53.4 MB (53392811 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c4330bc6a5e0bcfbe95c4a5b5982f6866f41b6cdc2d95042061dac233ebb605c`  
		Last Modified: Sat, 05 May 2018 10:53:05 GMT  
		Size: 17.6 MB (17586999 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:62808c556cbd0edb13c1bdc0672028bc333139d66cdd2f508eb98becf5d5ecd4`  
		Last Modified: Sat, 05 May 2018 15:17:37 GMT  
		Size: 791.0 KB (790978 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d1bd439f7dc98417f8b4e0b334b6a8f3e349b1c8bd81c4af83e0344ee9f9bd0e`  
		Last Modified: Sat, 05 May 2018 15:17:36 GMT  
		Size: 249.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:802e363d6798794314c4626d0bf023452db3024b735b510b634d6d21866d6eda`  
		Last Modified: Sat, 05 May 2018 15:17:36 GMT  
		Size: 132.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:882d4683fa5e55a3169ffd52657f1ee2158e7c4eb6143833439074d9ae4cd59f`  
		Last Modified: Tue, 12 Jun 2018 09:15:01 GMT  
		Size: 73.9 MB (73947674 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7a9b504edee9910b572ac8deebda0f5edc7037227f5b71647daf6e6d26efad90`  
		Last Modified: Tue, 12 Jun 2018 09:46:06 GMT  
		Size: 2.1 KB (2099 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:39e02996b21e4e6d0380a31a8a38a4c2bfbadc18f4abac1e9070f903e75e871e`  
		Last Modified: Tue, 12 Jun 2018 09:46:05 GMT  
		Size: 182.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:99a04dc76c5fa519247dbc842e652528e97b61a3124630f4994d869e4372550b`  
		Last Modified: Tue, 12 Jun 2018 09:46:06 GMT  
		Size: 10.0 MB (10029017 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7aa6d9674c13dff8ebfab3075a204ea98d69443348248c9448687926443b088e`  
		Last Modified: Tue, 12 Jun 2018 09:46:03 GMT  
		Size: 171.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:123c4380ce1023ef397eb53a7fe05693df70972dfeea904e52be1437bce42034`  
		Last Modified: Tue, 12 Jun 2018 09:46:03 GMT  
		Size: 1.5 KB (1538 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ae24bc2694ef2a0fbbd974ff9dcfbeca7a48041e31f2b202528fe48cff3d3888`  
		Last Modified: Tue, 12 Jun 2018 09:46:03 GMT  
		Size: 156.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0c64b23a57a82cccb9b2e7b05baf63b6d0260a20c48343e592f513a42aa78785`  
		Last Modified: Tue, 12 Jun 2018 09:46:03 GMT  
		Size: 1.4 KB (1387 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `jetty:9-jre7` - linux; s390x

```console
$ docker pull jetty@sha256:5190ed86d57a15340c7d19bcbe9111d58da3ce8f685080bd5979eda4acaabbd4
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **156.8 MB (156766827 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:1de3f578923488c77e243d6a26bc8cf95b59ecbb6310d4c4db6deefa5526a522`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["java","-jar","\/usr\/local\/jetty\/start.jar"]`

```dockerfile
# Sat, 28 Apr 2018 11:42:31 GMT
ADD file:ac1cfec75c7e1898f2c9b7d17653da3684fdda7d14440ce16f1939bb66105cdc in / 
# Sat, 28 Apr 2018 11:42:31 GMT
CMD ["bash"]
# Sat, 05 May 2018 12:30:55 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 12:30:56 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Sat, 05 May 2018 13:16:57 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 13:16:57 GMT
ENV LANG=C.UTF-8
# Sat, 05 May 2018 13:16:58 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Sat, 05 May 2018 13:16:58 GMT
RUN ln -svT "/usr/lib/jvm/java-7-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Sat, 05 May 2018 13:16:59 GMT
ENV JAVA_HOME=/docker-java-home/jre
# Tue, 12 Jun 2018 11:55:55 GMT
ENV JAVA_VERSION=7u181
# Tue, 12 Jun 2018 11:55:55 GMT
ENV JAVA_DEBIAN_VERSION=7u181-2.6.14-1~deb8u1
# Tue, 12 Jun 2018 11:56:29 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-7-jre="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Tue, 12 Jun 2018 12:22:19 GMT
RUN groupadd -r jetty && useradd -r -g jetty jetty
# Tue, 12 Jun 2018 12:22:19 GMT
ENV JETTY_HOME=/usr/local/jetty
# Tue, 12 Jun 2018 12:22:19 GMT
ENV PATH=/usr/local/jetty/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Tue, 12 Jun 2018 12:22:20 GMT
RUN mkdir -p "$JETTY_HOME"
# Tue, 12 Jun 2018 12:22:20 GMT
WORKDIR /usr/local/jetty
# Tue, 12 Jun 2018 12:22:20 GMT
ENV JETTY_VERSION=9.2.24.v20180105
# Tue, 12 Jun 2018 12:22:20 GMT
ENV JETTY_TGZ_URL=https://repo1.maven.org/maven2/org/eclipse/jetty/jetty-distribution/9.2.24.v20180105/jetty-distribution-9.2.24.v20180105.tar.gz
# Tue, 12 Jun 2018 12:22:20 GMT
ENV JETTY_GPG_KEYS=AED5EE6C45D0FE8D5D1B164F27DED4BF6216DB8F 	2A684B57436A81FA8706B53C61C3351A438A3B7D 	5989BAF76217B843D66BE55B2D0E1FB8FE4B68B4 	B59B67FD7904984367F931800818D9D68FB67BAC 	BFBB21C246D7776836287A48A04E0C74ABB35FEA 	8B096546B1A8F02656B15D3B1677D141BCF3584D 	FBA2B18D238AB852DF95745C76157BDF03D0DCD6 	5C9579B3DB2E506429319AAEF33B071B29559E1E
# Tue, 12 Jun 2018 12:22:22 GMT
RUN set -xe 	&& curl -SL "$JETTY_TGZ_URL" -o jetty.tar.gz 	&& curl -SL "$JETTY_TGZ_URL.asc" -o jetty.tar.gz.asc 	&& export GNUPGHOME="$(mktemp -d)" 	&& for key in $JETTY_GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; done 	&& gpg --batch --verify jetty.tar.gz.asc jetty.tar.gz 	&& rm -rf "$GNUPGHOME" 	&& tar -xvf jetty.tar.gz --strip-components=1 	&& sed -i '/jetty-logging/d' etc/jetty.conf 	&& rm -fr demo-base javadoc 	&& rm jetty.tar.gz* 	&& rm -rf /tmp/hsperfdata_root
# Tue, 12 Jun 2018 12:22:22 GMT
ENV JETTY_BASE=/var/lib/jetty
# Tue, 12 Jun 2018 12:22:23 GMT
RUN mkdir -p "$JETTY_BASE"
# Tue, 12 Jun 2018 12:22:23 GMT
WORKDIR /var/lib/jetty
# Tue, 12 Jun 2018 12:22:24 GMT
RUN modules="$(grep -- ^--module= "$JETTY_HOME/start.ini" | cut -d= -f2 | paste -d, -s)" 	&& set -xe 	&& java -jar "$JETTY_HOME/start.jar" --add-to-startd="$modules" 	&& chown -R jetty:jetty "$JETTY_BASE" 	&& rm -rf /tmp/hsperfdata_root
# Tue, 12 Jun 2018 12:22:24 GMT
ENV TMPDIR=/tmp/jetty
# Tue, 12 Jun 2018 12:22:25 GMT
RUN set -xe 	&& mkdir -p "$TMPDIR" 	&& chown -R jetty:jetty "$TMPDIR"
# Tue, 12 Jun 2018 12:22:25 GMT
COPY multi:4510ce2f7fb9540fb389937165085b97c71d4b0659b22ddb7dfe601528a7461a in / 
# Tue, 12 Jun 2018 12:22:25 GMT
USER [jetty]
# Tue, 12 Jun 2018 12:22:25 GMT
EXPOSE 8080/tcp
# Tue, 12 Jun 2018 12:22:26 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Tue, 12 Jun 2018 12:22:26 GMT
CMD ["java" "-jar" "/usr/local/jetty/start.jar"]
```

-	Layers:
	-	`sha256:e0524893a6d25f3e36c190fea678ecf1845e7c0d2ba833b077a429d64b943e0a`  
		Last Modified: Sat, 28 Apr 2018 11:47:52 GMT  
		Size: 54.5 MB (54465857 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:37be7fda6df150d239266145f4a84caa9f37d32c535a19acbb408973995140fd`  
		Last Modified: Sat, 05 May 2018 12:45:40 GMT  
		Size: 17.8 MB (17787031 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:08ee0611e7e673e3a0c80e59f3c1428955b30858e5eeb1b9ae8f76b149e0fdaf`  
		Last Modified: Sat, 05 May 2018 13:32:33 GMT  
		Size: 804.0 KB (804004 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3c0f05e4588b7d9986cddfc7fe413479b1207d65cd974d48345294cd4a91ab26`  
		Last Modified: Sat, 05 May 2018 13:32:32 GMT  
		Size: 247.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b5dfe35e52e265c6289d75bd0d3f4d8cd4e97a2d59980978230c597277a93560`  
		Last Modified: Sat, 05 May 2018 13:32:32 GMT  
		Size: 130.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c3d2de52a9757f90b0c0901a60c17b39074186b037e07a5fd69d2a736ed9e9eb`  
		Last Modified: Tue, 12 Jun 2018 12:02:32 GMT  
		Size: 73.7 MB (73675365 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e6f47d8c31fe847fe38c42c5c05993150cbcabe32c15c2d4470796bc8a1a3730`  
		Last Modified: Tue, 12 Jun 2018 12:22:43 GMT  
		Size: 2.1 KB (2104 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a6d99d1b7cc13de476fd72ce63ff54110ecf808d93c9441946b0ce0e5fdac0ed`  
		Last Modified: Tue, 12 Jun 2018 12:22:42 GMT  
		Size: 151.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9cc4d82e9928d446d6e9c8bbde26ea7dd88c81a3b52d62862e5aaeb4a62b185a`  
		Last Modified: Tue, 12 Jun 2018 12:22:42 GMT  
		Size: 10.0 MB (10028816 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9f4f3d67bd036a2bdff39b5d039b92c6e756068eed7311fc31c4a8f8b82d00d4`  
		Last Modified: Tue, 12 Jun 2018 12:22:41 GMT  
		Size: 139.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4b979d16f8d7571e25ccb1747870e130690df440d259ae06351455d9c6e706ba`  
		Last Modified: Tue, 12 Jun 2018 12:22:41 GMT  
		Size: 1.5 KB (1473 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a3559f5c26c37b07dd12fd9af71b77689416d08e92f84e6146c71c3c8cd7236b`  
		Last Modified: Tue, 12 Jun 2018 12:22:40 GMT  
		Size: 124.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ee58fed5c4e3c5b18aa3ae7188abe743c910b0b0431705e3e111747e08b82650`  
		Last Modified: Tue, 12 Jun 2018 12:22:42 GMT  
		Size: 1.4 KB (1386 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
