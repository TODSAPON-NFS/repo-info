## `jetty:latest`

```console
$ docker pull jetty@sha256:a9e16344c514ab86979c23dd317623e0725541392312174be503a80306fcbb6f
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

### `jetty:latest` - linux; amd64

```console
$ docker pull jetty@sha256:0e7975a1ddf8be5511520b5a9adb3ba7c7aca0b5614f11c213a65d4544a5f459
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **192.1 MB (192099423 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:c918abe88f09480452e743cab86e7f23e0cad98405c2664d230a1136d550aff7`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["java","-jar","\/usr\/local\/jetty\/start.jar"]`

```dockerfile
# Sat, 28 Apr 2018 07:08:53 GMT
ADD file:9572fdb59dfbb9b032f3331bbc2a08b31e0aef5fbde44c8f2008d22bf5290cf2 in / 
# Sat, 28 Apr 2018 07:08:53 GMT
CMD ["bash"]
# Tue, 05 Jun 2018 23:13:29 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 05 Jun 2018 23:13:38 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Wed, 06 Jun 2018 18:44:44 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Wed, 06 Jun 2018 18:44:44 GMT
ENV LANG=C.UTF-8
# Wed, 06 Jun 2018 18:44:45 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Wed, 06 Jun 2018 18:44:46 GMT
RUN ln -svT "/usr/lib/jvm/java-8-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Wed, 06 Jun 2018 18:44:46 GMT
ENV JAVA_HOME=/docker-java-home/jre
# Wed, 06 Jun 2018 18:44:46 GMT
ENV JAVA_VERSION=8u171
# Wed, 06 Jun 2018 18:44:46 GMT
ENV JAVA_DEBIAN_VERSION=8u171-b11-1~deb9u1
# Wed, 06 Jun 2018 18:44:46 GMT
ENV CA_CERTIFICATES_JAVA_VERSION=20170531+nmu1
# Wed, 06 Jun 2018 18:45:17 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-8-jre="$JAVA_DEBIAN_VERSION" 		ca-certificates-java="$CA_CERTIFICATES_JAVA_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Wed, 06 Jun 2018 18:45:19 GMT
RUN /var/lib/dpkg/info/ca-certificates-java.postinst configure
# Tue, 12 Jun 2018 01:06:35 GMT
RUN groupadd -r jetty && useradd -r -g jetty jetty
# Tue, 12 Jun 2018 01:06:35 GMT
ENV JETTY_HOME=/usr/local/jetty
# Tue, 12 Jun 2018 01:06:35 GMT
ENV PATH=/usr/local/jetty/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Tue, 12 Jun 2018 01:06:36 GMT
RUN mkdir -p "$JETTY_HOME"
# Tue, 12 Jun 2018 01:06:36 GMT
WORKDIR /usr/local/jetty
# Tue, 12 Jun 2018 01:06:36 GMT
ENV JETTY_VERSION=9.4.9.v20180320
# Tue, 12 Jun 2018 01:06:36 GMT
ENV JETTY_TGZ_URL=https://repo1.maven.org/maven2/org/eclipse/jetty/jetty-home/9.4.9.v20180320/jetty-home-9.4.9.v20180320.tar.gz
# Tue, 12 Jun 2018 01:06:36 GMT
ENV JETTY_GPG_KEYS=AED5EE6C45D0FE8D5D1B164F27DED4BF6216DB8F 	2A684B57436A81FA8706B53C61C3351A438A3B7D 	5989BAF76217B843D66BE55B2D0E1FB8FE4B68B4 	B59B67FD7904984367F931800818D9D68FB67BAC 	BFBB21C246D7776836287A48A04E0C74ABB35FEA 	8B096546B1A8F02656B15D3B1677D141BCF3584D 	FBA2B18D238AB852DF95745C76157BDF03D0DCD6 	5C9579B3DB2E506429319AAEF33B071B29559E1E
# Tue, 12 Jun 2018 01:06:43 GMT
RUN set -xe 	&& curl -SL "$JETTY_TGZ_URL" -o jetty.tar.gz 	&& curl -SL "$JETTY_TGZ_URL.asc" -o jetty.tar.gz.asc 	&& export GNUPGHOME="$(mktemp -d)" 	&& for key in $JETTY_GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; done 	&& gpg --batch --verify jetty.tar.gz.asc jetty.tar.gz 	&& rm -rf "$GNUPGHOME" 	&& tar -xvf jetty.tar.gz --strip-components=1 	&& sed -i '/jetty-logging/d' etc/jetty.conf 	&& rm jetty.tar.gz* 	&& rm -rf /tmp/hsperfdata_root
# Tue, 12 Jun 2018 01:06:43 GMT
ENV JETTY_BASE=/var/lib/jetty
# Tue, 12 Jun 2018 01:06:44 GMT
RUN mkdir -p "$JETTY_BASE"
# Tue, 12 Jun 2018 01:06:44 GMT
WORKDIR /var/lib/jetty
# Tue, 12 Jun 2018 01:06:46 GMT
RUN set -xe 	&& java -jar "$JETTY_HOME/start.jar" --create-startd --add-to-start="server,http,deploy,jsp,jstl,ext,resources,websocket" 	&& chown -R jetty:jetty "$JETTY_BASE" 	&& rm -rf /tmp/hsperfdata_root
# Tue, 12 Jun 2018 01:06:46 GMT
ENV TMPDIR=/tmp/jetty
# Tue, 12 Jun 2018 01:06:47 GMT
RUN set -xe 	&& mkdir -p "$TMPDIR" 	&& chown -R jetty:jetty "$TMPDIR"
# Tue, 12 Jun 2018 01:06:47 GMT
COPY multi:4510ce2f7fb9540fb389937165085b97c71d4b0659b22ddb7dfe601528a7461a in / 
# Tue, 12 Jun 2018 01:06:47 GMT
USER [jetty]
# Tue, 12 Jun 2018 01:06:47 GMT
EXPOSE 8080/tcp
# Tue, 12 Jun 2018 01:06:47 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Tue, 12 Jun 2018 01:06:48 GMT
CMD ["java" "-jar" "/usr/local/jetty/start.jar"]
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
	-	`sha256:e8912f9d0ce2e4accc0eb655a24f8b5def2ed4d1caf9d9dc897a19a4d32faf9f`  
		Last Modified: Wed, 06 Jun 2018 19:05:26 GMT  
		Size: 853.1 KB (853110 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9bafe362f99b9e9353c71496d5dd82907355aafab384360400be4d2715816383`  
		Last Modified: Wed, 06 Jun 2018 19:05:26 GMT  
		Size: 249.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:28b0652112a637ad5505eee5907b395211776ed3bfd3a74743c428605975be78`  
		Last Modified: Wed, 06 Jun 2018 19:05:25 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:da23e1e20eae995da970ffc93d5bd64980d6f6061a0f33bc08cc9d65475c670a`  
		Last Modified: Wed, 06 Jun 2018 19:05:53 GMT  
		Size: 122.1 MB (122141480 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9d809d99b239e4876578052705afd7653615e34b5155028d2206e5ec95e30c96`  
		Last Modified: Wed, 06 Jun 2018 19:05:26 GMT  
		Size: 272.2 KB (272162 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1979e74ccd7333a459d66214f10d7585ea2ddd6b59fb86c26ef4ce1fa1093398`  
		Last Modified: Tue, 12 Jun 2018 01:08:03 GMT  
		Size: 1.7 KB (1749 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7d06818311552eabffa46e6814b938b258beaec49c4474352e37afade8ca14f1`  
		Last Modified: Tue, 12 Jun 2018 01:08:03 GMT  
		Size: 152.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:512c7134594bf8343ffb2e5fc5b2660fdd28fa870508db9ac39a61606070e4f9`  
		Last Modified: Tue, 12 Jun 2018 01:08:03 GMT  
		Size: 8.4 MB (8398512 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:78676f3f41c9583a19ce0a89a99d32ad979774904a910609438e9cf9879139c0`  
		Last Modified: Tue, 12 Jun 2018 01:08:03 GMT  
		Size: 139.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a021b23e77bde05fe6556c3db697af9b6469ebff4e32d0d7b653cfa80574798f`  
		Last Modified: Tue, 12 Jun 2018 01:08:01 GMT  
		Size: 2.0 KB (1994 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:eadb421aa6fe632c343c5d88101caac6117a5081c5ed42653d6cfee12a831ef0`  
		Last Modified: Tue, 12 Jun 2018 01:08:01 GMT  
		Size: 127.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:35c7a38648ccfb02206b56b961d1778fbcbb335ae80037a91f8ff14e4546b1ce`  
		Last Modified: Tue, 12 Jun 2018 01:08:01 GMT  
		Size: 1.4 KB (1389 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `jetty:latest` - linux; arm variant v5

```console
$ docker pull jetty@sha256:e9bb75bcf67a9a4e52e0bbdf1f593d0c386dc5acc73f896d2cd575bff70d082b
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **179.5 MB (179459165 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:99ee30d71f7aa9ba5c350bb12354d3a2921f5885039325fd10931ef379ddd9dc`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["java","-jar","\/usr\/local\/jetty\/start.jar"]`

```dockerfile
# Sat, 28 Apr 2018 08:53:04 GMT
ADD file:bd77176b7f68cf66010ed7d5cd955387a1eb54726e5071bc42ddd831ac56de69 in / 
# Sat, 28 Apr 2018 08:53:04 GMT
CMD ["bash"]
# Sat, 05 May 2018 09:00:47 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 09:00:59 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Sat, 05 May 2018 09:30:49 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 09:30:49 GMT
ENV LANG=C.UTF-8
# Sat, 05 May 2018 09:30:50 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Sat, 05 May 2018 09:30:52 GMT
RUN ln -svT "/usr/lib/jvm/java-8-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Sat, 05 May 2018 09:30:52 GMT
ENV JAVA_HOME=/docker-java-home/jre
# Sat, 05 May 2018 09:30:52 GMT
ENV JAVA_VERSION=8u171
# Sat, 05 May 2018 09:30:53 GMT
ENV JAVA_DEBIAN_VERSION=8u171-b11-1~deb9u1
# Sat, 05 May 2018 09:30:53 GMT
ENV CA_CERTIFICATES_JAVA_VERSION=20170531+nmu1
# Tue, 15 May 2018 09:46:09 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-8-jre="$JAVA_DEBIAN_VERSION" 		ca-certificates-java="$CA_CERTIFICATES_JAVA_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Tue, 15 May 2018 09:46:14 GMT
RUN /var/lib/dpkg/info/ca-certificates-java.postinst configure
# Mon, 21 May 2018 23:59:37 GMT
RUN groupadd -r jetty && useradd -r -g jetty jetty
# Mon, 21 May 2018 23:59:37 GMT
ENV JETTY_HOME=/usr/local/jetty
# Mon, 21 May 2018 23:59:38 GMT
ENV PATH=/usr/local/jetty/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Mon, 21 May 2018 23:59:38 GMT
RUN mkdir -p "$JETTY_HOME"
# Mon, 21 May 2018 23:59:39 GMT
WORKDIR /usr/local/jetty
# Mon, 21 May 2018 23:59:39 GMT
ENV JETTY_VERSION=9.4.9.v20180320
# Mon, 21 May 2018 23:59:39 GMT
ENV JETTY_TGZ_URL=https://repo1.maven.org/maven2/org/eclipse/jetty/jetty-home/9.4.9.v20180320/jetty-home-9.4.9.v20180320.tar.gz
# Mon, 21 May 2018 23:59:40 GMT
ENV JETTY_GPG_KEYS=AED5EE6C45D0FE8D5D1B164F27DED4BF6216DB8F 	2A684B57436A81FA8706B53C61C3351A438A3B7D 	5989BAF76217B843D66BE55B2D0E1FB8FE4B68B4 	B59B67FD7904984367F931800818D9D68FB67BAC 	BFBB21C246D7776836287A48A04E0C74ABB35FEA 	8B096546B1A8F02656B15D3B1677D141BCF3584D 	FBA2B18D238AB852DF95745C76157BDF03D0DCD6 	5C9579B3DB2E506429319AAEF33B071B29559E1E
# Mon, 21 May 2018 23:59:44 GMT
RUN set -xe 	&& curl -SL "$JETTY_TGZ_URL" -o jetty.tar.gz 	&& curl -SL "$JETTY_TGZ_URL.asc" -o jetty.tar.gz.asc 	&& export GNUPGHOME="$(mktemp -d)" 	&& for key in $JETTY_GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; done 	&& gpg --batch --verify jetty.tar.gz.asc jetty.tar.gz 	&& rm -rf "$GNUPGHOME" 	&& tar -xvf jetty.tar.gz --strip-components=1 	&& sed -i '/jetty-logging/d' etc/jetty.conf 	&& rm jetty.tar.gz* 	&& rm -rf /tmp/hsperfdata_root
# Mon, 21 May 2018 23:59:44 GMT
ENV JETTY_BASE=/var/lib/jetty
# Mon, 21 May 2018 23:59:45 GMT
RUN mkdir -p "$JETTY_BASE"
# Mon, 21 May 2018 23:59:46 GMT
WORKDIR /var/lib/jetty
# Mon, 21 May 2018 23:59:49 GMT
RUN set -xe 	&& java -jar "$JETTY_HOME/start.jar" --create-startd --add-to-start="server,http,deploy,jsp,jstl,ext,resources,websocket" 	&& chown -R jetty:jetty "$JETTY_BASE" 	&& rm -rf /tmp/hsperfdata_root
# Mon, 21 May 2018 23:59:50 GMT
ENV TMPDIR=/tmp/jetty
# Mon, 21 May 2018 23:59:51 GMT
RUN set -xe 	&& mkdir -p "$TMPDIR" 	&& chown -R jetty:jetty "$TMPDIR"
# Mon, 21 May 2018 23:59:52 GMT
COPY multi:4510ce2f7fb9540fb389937165085b97c71d4b0659b22ddb7dfe601528a7461a in / 
# Mon, 21 May 2018 23:59:52 GMT
USER [jetty]
# Mon, 21 May 2018 23:59:52 GMT
EXPOSE 8080/tcp
# Mon, 21 May 2018 23:59:52 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Mon, 21 May 2018 23:59:53 GMT
CMD ["java" "-jar" "/usr/local/jetty/start.jar"]
```

-	Layers:
	-	`sha256:c87e62b47a5d3031bbfc66d1b7c178e12dd4b62b36eaa44a879cebbbc558c33d`  
		Last Modified: Sat, 28 Apr 2018 09:01:28 GMT  
		Size: 44.0 MB (44038582 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0b447c1a942c4bbb82a6222d7f5abc3936dfb4b80c399d470515f9956cbc4e93`  
		Last Modified: Sat, 05 May 2018 09:13:26 GMT  
		Size: 9.8 MB (9842386 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:aa0b217d1eda0719b1e84281d8b64839a9a234ee6976bc53a2a031453e60beb2`  
		Last Modified: Sat, 05 May 2018 09:13:23 GMT  
		Size: 4.2 MB (4153388 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b4b0e6b1819c238fd60444cf5836fee5774c120dab476626643b70d701a5cc49`  
		Last Modified: Sat, 05 May 2018 09:56:44 GMT  
		Size: 846.0 KB (846039 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e4f09a5ae1ef091a2bfd31a1d4b84d19d752831b8ab695ca01675dadd1d1f8dc`  
		Last Modified: Sat, 05 May 2018 09:56:44 GMT  
		Size: 247.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c12383fca7a9b5e84e63a26eb8d3846257449267e913f26cd65fc040232f608f`  
		Last Modified: Sat, 05 May 2018 09:56:44 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fd3315e95ab34eddcbd745da795abdce66235606993de1e8c874b1fe1c4c14b1`  
		Last Modified: Tue, 15 May 2018 10:21:50 GMT  
		Size: 111.9 MB (111901878 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9597dc245fb573097ca0ad643542744b6581ac6c0ffd1bad675a50298af175db`  
		Last Modified: Tue, 15 May 2018 10:21:21 GMT  
		Size: 272.2 KB (272202 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:30f17e0485498d53af29423a2c903cac938b501d3bb07d7960239987c8e6bb60`  
		Last Modified: Tue, 22 May 2018 00:01:24 GMT  
		Size: 1.7 KB (1742 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ef9e6e6c47458752df588b3271809ef55332b3e7eb30acc16c794c303dd5082e`  
		Last Modified: Tue, 22 May 2018 00:01:24 GMT  
		Size: 183.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a4dcc8a041bf72f69998cc211847e5e26a947702b93837d9d8c173358e6929c9`  
		Last Modified: Tue, 22 May 2018 00:01:24 GMT  
		Size: 8.4 MB (8398606 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a476e7626119b87b992317ed6c3030921982e494c1c729be70f5080eb4e3dea1`  
		Last Modified: Tue, 22 May 2018 00:01:22 GMT  
		Size: 172.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6d2bcfae84ae3920660acf693441dbd13acf3bf4b7c04df100357aac54f767aa`  
		Last Modified: Tue, 22 May 2018 00:01:22 GMT  
		Size: 2.1 KB (2065 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2da1df2a0bf364769f39e2199021775df3839b49dfed72bcb3963d7e65ba5755`  
		Last Modified: Tue, 22 May 2018 00:01:23 GMT  
		Size: 157.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:216d0026f1418635aa73fdb447e72808b1c3a4eddc95242a2788c621089db916`  
		Last Modified: Tue, 22 May 2018 00:01:23 GMT  
		Size: 1.4 KB (1387 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `jetty:latest` - linux; arm variant v7

```console
$ docker pull jetty@sha256:0df4c25e9b7e0e2560a44f494ac5dcffdec871fa8e606ded9db1d56b180eddc8
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **204.5 MB (204457946 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:fd3b5cf59b52917f1a76250c15d741affd5104e3a3b7192a7dc01e2c190c6789`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["java","-jar","\/usr\/local\/jetty\/start.jar"]`

```dockerfile
# Sat, 28 Apr 2018 12:04:18 GMT
ADD file:c7fba27b02c4bda63faef7eb30156a55feb4c0e9ecd529a24dd8d62942c2f83c in / 
# Sat, 28 Apr 2018 12:04:19 GMT
CMD ["bash"]
# Sat, 05 May 2018 12:13:49 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 12:13:58 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Sat, 05 May 2018 12:59:16 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 12:59:16 GMT
ENV LANG=C.UTF-8
# Sat, 05 May 2018 12:59:17 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Sat, 05 May 2018 12:59:18 GMT
RUN ln -svT "/usr/lib/jvm/java-8-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Sat, 05 May 2018 12:59:18 GMT
ENV JAVA_HOME=/docker-java-home/jre
# Sat, 05 May 2018 12:59:19 GMT
ENV JAVA_VERSION=8u171
# Sat, 05 May 2018 12:59:27 GMT
ENV JAVA_DEBIAN_VERSION=8u171-b11-1~deb9u1
# Sat, 05 May 2018 12:59:27 GMT
ENV CA_CERTIFICATES_JAVA_VERSION=20170531+nmu1
# Sat, 05 May 2018 13:00:26 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y 		openjdk-8-jre="$JAVA_DEBIAN_VERSION" 		ca-certificates-java="$CA_CERTIFICATES_JAVA_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Sat, 05 May 2018 13:00:28 GMT
RUN /var/lib/dpkg/info/ca-certificates-java.postinst configure
# Thu, 31 May 2018 12:51:45 GMT
RUN groupadd -r jetty && useradd -r -g jetty jetty
# Thu, 31 May 2018 12:51:45 GMT
ENV JETTY_HOME=/usr/local/jetty
# Thu, 31 May 2018 12:51:45 GMT
ENV PATH=/usr/local/jetty/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Thu, 31 May 2018 12:51:46 GMT
RUN mkdir -p "$JETTY_HOME"
# Thu, 31 May 2018 12:51:47 GMT
WORKDIR /usr/local/jetty
# Thu, 31 May 2018 12:51:47 GMT
ENV JETTY_VERSION=9.4.9.v20180320
# Thu, 31 May 2018 12:51:48 GMT
ENV JETTY_TGZ_URL=https://repo1.maven.org/maven2/org/eclipse/jetty/jetty-home/9.4.9.v20180320/jetty-home-9.4.9.v20180320.tar.gz
# Thu, 31 May 2018 12:51:48 GMT
ENV JETTY_GPG_KEYS=AED5EE6C45D0FE8D5D1B164F27DED4BF6216DB8F 	2A684B57436A81FA8706B53C61C3351A438A3B7D 	5989BAF76217B843D66BE55B2D0E1FB8FE4B68B4 	B59B67FD7904984367F931800818D9D68FB67BAC 	BFBB21C246D7776836287A48A04E0C74ABB35FEA 	8B096546B1A8F02656B15D3B1677D141BCF3584D 	FBA2B18D238AB852DF95745C76157BDF03D0DCD6 	5C9579B3DB2E506429319AAEF33B071B29559E1E
# Thu, 31 May 2018 12:51:53 GMT
RUN set -xe 	&& curl -SL "$JETTY_TGZ_URL" -o jetty.tar.gz 	&& curl -SL "$JETTY_TGZ_URL.asc" -o jetty.tar.gz.asc 	&& export GNUPGHOME="$(mktemp -d)" 	&& for key in $JETTY_GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; done 	&& gpg --batch --verify jetty.tar.gz.asc jetty.tar.gz 	&& rm -rf "$GNUPGHOME" 	&& tar -xvf jetty.tar.gz --strip-components=1 	&& sed -i '/jetty-logging/d' etc/jetty.conf 	&& rm jetty.tar.gz* 	&& rm -rf /tmp/hsperfdata_root
# Thu, 31 May 2018 12:51:53 GMT
ENV JETTY_BASE=/var/lib/jetty
# Thu, 31 May 2018 12:51:54 GMT
RUN mkdir -p "$JETTY_BASE"
# Thu, 31 May 2018 12:51:55 GMT
WORKDIR /var/lib/jetty
# Thu, 31 May 2018 12:51:57 GMT
RUN set -xe 	&& java -jar "$JETTY_HOME/start.jar" --create-startd --add-to-start="server,http,deploy,jsp,jstl,ext,resources,websocket" 	&& chown -R jetty:jetty "$JETTY_BASE" 	&& rm -rf /tmp/hsperfdata_root
# Thu, 31 May 2018 12:51:57 GMT
ENV TMPDIR=/tmp/jetty
# Thu, 31 May 2018 12:51:58 GMT
RUN set -xe 	&& mkdir -p "$TMPDIR" 	&& chown -R jetty:jetty "$TMPDIR"
# Thu, 31 May 2018 12:51:59 GMT
COPY multi:4510ce2f7fb9540fb389937165085b97c71d4b0659b22ddb7dfe601528a7461a in / 
# Thu, 31 May 2018 12:51:59 GMT
USER [jetty]
# Thu, 31 May 2018 12:51:59 GMT
EXPOSE 8080/tcp
# Thu, 31 May 2018 12:52:00 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Thu, 31 May 2018 12:52:00 GMT
CMD ["java" "-jar" "/usr/local/jetty/start.jar"]
```

-	Layers:
	-	`sha256:5483105d09166836731e940c850827dd1a4fe16b04d1921eea4d8da7c98e99bc`  
		Last Modified: Sat, 28 Apr 2018 12:15:18 GMT  
		Size: 42.1 MB (42063737 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8ed57f83cc7c78757972312a1b5a30524f861523c5390d062845f18c696f48ea`  
		Last Modified: Sat, 05 May 2018 12:35:37 GMT  
		Size: 9.5 MB (9472475 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:859203aede279201e8caf07cf2963456c56bac72a64071079dc9db6fb65ed1a2`  
		Last Modified: Sat, 05 May 2018 12:35:34 GMT  
		Size: 3.9 MB (3912835 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:df26ddf71ea9e82f175e400809b8f06871dd0937c5a90f4ffe95286544a9f719`  
		Last Modified: Sat, 05 May 2018 13:29:05 GMT  
		Size: 830.3 KB (830332 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a2c21322a9c89724512d6ea5faa10299c60c8a605d6f563c84c28177db8d2770`  
		Last Modified: Sat, 05 May 2018 13:29:05 GMT  
		Size: 247.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2270f04a4be61f52577232813fff92e797d3fc190d52f71411afc26b0911f8e4`  
		Last Modified: Sat, 05 May 2018 13:29:04 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:da2dc1aba58c8cd285639cac6b03c823e5fcdb91aa8922652e7d9387aaca6fa4`  
		Last Modified: Sat, 05 May 2018 13:29:37 GMT  
		Size: 139.5 MB (139501760 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:02869ec2bb3864b06abd435610eb6849d5c62426517de1a603ef6fe43c7d3815`  
		Last Modified: Sat, 05 May 2018 13:29:05 GMT  
		Size: 272.1 KB (272082 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:12efdc71b9e99bd7995b3b0f47852504778ff84f64fcb8754e411477c41efbdc`  
		Last Modified: Thu, 31 May 2018 12:55:31 GMT  
		Size: 1.8 KB (1779 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6a6b73c2bee605f60c6c47b42b1fe14e9019a844adc98533a4d356c4decc7e4c`  
		Last Modified: Thu, 31 May 2018 12:55:30 GMT  
		Size: 182.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:87e2a3818be5125048b6579a0b7e595158c4b3050e526bb452625c8f18904c4f`  
		Last Modified: Thu, 31 May 2018 12:55:31 GMT  
		Size: 8.4 MB (8398609 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2a3a5014d4f6beb8a4aad0c1ef07fd44da6306bcde400e99017a93aa1f2d9c32`  
		Last Modified: Thu, 31 May 2018 12:55:30 GMT  
		Size: 172.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0bc2165ef99f440c437554e0fe6f9d0129342c526888975c6757dc5c09d79f4c`  
		Last Modified: Thu, 31 May 2018 12:55:29 GMT  
		Size: 2.1 KB (2065 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fcf341370ed198072015a627cfb40d8394cbb7558458ebdb5920844bd3ca77b7`  
		Last Modified: Thu, 31 May 2018 12:55:29 GMT  
		Size: 155.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:13e951b418449945e1924eb6bbbea8332f173553865f82302ddc507836cf0717`  
		Last Modified: Thu, 31 May 2018 12:55:29 GMT  
		Size: 1.4 KB (1385 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `jetty:latest` - linux; arm64 variant v8

```console
$ docker pull jetty@sha256:522d314b8ef0d20db0a83994a5cf56668e68e90501a16dcc24b7143a81695517
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **179.2 MB (179180900 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:8b3514de3c2f6e0ffe226f9dda1c6b2fc629d2acdd727badc1bf61e107d1626f`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["java","-jar","\/usr\/local\/jetty\/start.jar"]`

```dockerfile
# Mon, 30 Apr 2018 23:31:58 GMT
ADD file:245a8cfe59ea071e4e215a722e0d4b4b14fa95dd6ffd03739fe048433cfaf523 in / 
# Mon, 30 Apr 2018 23:32:00 GMT
CMD ["bash"]
# Sat, 05 May 2018 09:38:42 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 09:39:04 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Sat, 05 May 2018 12:03:33 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 12:03:34 GMT
ENV LANG=C.UTF-8
# Sat, 05 May 2018 12:03:38 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Sat, 05 May 2018 12:03:42 GMT
RUN ln -svT "/usr/lib/jvm/java-8-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Sat, 05 May 2018 12:03:43 GMT
ENV JAVA_HOME=/docker-java-home/jre
# Sat, 05 May 2018 12:03:45 GMT
ENV JAVA_VERSION=8u171
# Sat, 05 May 2018 12:03:46 GMT
ENV JAVA_DEBIAN_VERSION=8u171-b11-1~deb9u1
# Sat, 05 May 2018 12:03:47 GMT
ENV CA_CERTIFICATES_JAVA_VERSION=20170531+nmu1
# Tue, 15 May 2018 09:57:07 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-8-jre="$JAVA_DEBIAN_VERSION" 		ca-certificates-java="$CA_CERTIFICATES_JAVA_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Tue, 15 May 2018 09:57:13 GMT
RUN /var/lib/dpkg/info/ca-certificates-java.postinst configure
# Mon, 21 May 2018 23:59:34 GMT
RUN groupadd -r jetty && useradd -r -g jetty jetty
# Mon, 21 May 2018 23:59:34 GMT
ENV JETTY_HOME=/usr/local/jetty
# Mon, 21 May 2018 23:59:35 GMT
ENV PATH=/usr/local/jetty/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Mon, 21 May 2018 23:59:36 GMT
RUN mkdir -p "$JETTY_HOME"
# Mon, 21 May 2018 23:59:37 GMT
WORKDIR /usr/local/jetty
# Mon, 21 May 2018 23:59:37 GMT
ENV JETTY_VERSION=9.4.9.v20180320
# Mon, 21 May 2018 23:59:38 GMT
ENV JETTY_TGZ_URL=https://repo1.maven.org/maven2/org/eclipse/jetty/jetty-home/9.4.9.v20180320/jetty-home-9.4.9.v20180320.tar.gz
# Mon, 21 May 2018 23:59:39 GMT
ENV JETTY_GPG_KEYS=AED5EE6C45D0FE8D5D1B164F27DED4BF6216DB8F 	2A684B57436A81FA8706B53C61C3351A438A3B7D 	5989BAF76217B843D66BE55B2D0E1FB8FE4B68B4 	B59B67FD7904984367F931800818D9D68FB67BAC 	BFBB21C246D7776836287A48A04E0C74ABB35FEA 	8B096546B1A8F02656B15D3B1677D141BCF3584D 	FBA2B18D238AB852DF95745C76157BDF03D0DCD6 	5C9579B3DB2E506429319AAEF33B071B29559E1E
# Mon, 21 May 2018 23:59:46 GMT
RUN set -xe 	&& curl -SL "$JETTY_TGZ_URL" -o jetty.tar.gz 	&& curl -SL "$JETTY_TGZ_URL.asc" -o jetty.tar.gz.asc 	&& export GNUPGHOME="$(mktemp -d)" 	&& for key in $JETTY_GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; done 	&& gpg --batch --verify jetty.tar.gz.asc jetty.tar.gz 	&& rm -rf "$GNUPGHOME" 	&& tar -xvf jetty.tar.gz --strip-components=1 	&& sed -i '/jetty-logging/d' etc/jetty.conf 	&& rm jetty.tar.gz* 	&& rm -rf /tmp/hsperfdata_root
# Mon, 21 May 2018 23:59:46 GMT
ENV JETTY_BASE=/var/lib/jetty
# Mon, 21 May 2018 23:59:48 GMT
RUN mkdir -p "$JETTY_BASE"
# Mon, 21 May 2018 23:59:48 GMT
WORKDIR /var/lib/jetty
# Mon, 21 May 2018 23:59:52 GMT
RUN set -xe 	&& java -jar "$JETTY_HOME/start.jar" --create-startd --add-to-start="server,http,deploy,jsp,jstl,ext,resources,websocket" 	&& chown -R jetty:jetty "$JETTY_BASE" 	&& rm -rf /tmp/hsperfdata_root
# Mon, 21 May 2018 23:59:53 GMT
ENV TMPDIR=/tmp/jetty
# Mon, 21 May 2018 23:59:54 GMT
RUN set -xe 	&& mkdir -p "$TMPDIR" 	&& chown -R jetty:jetty "$TMPDIR"
# Mon, 21 May 2018 23:59:55 GMT
COPY multi:4510ce2f7fb9540fb389937165085b97c71d4b0659b22ddb7dfe601528a7461a in / 
# Mon, 21 May 2018 23:59:56 GMT
USER [jetty]
# Mon, 21 May 2018 23:59:56 GMT
EXPOSE 8080/tcp
# Mon, 21 May 2018 23:59:57 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Mon, 21 May 2018 23:59:57 GMT
CMD ["java" "-jar" "/usr/local/jetty/start.jar"]
```

-	Layers:
	-	`sha256:142bf25d8d1b3ebc9dfbedd586e70a011594690acf48b2695bfce01e3a2cf0d5`  
		Last Modified: Mon, 30 Apr 2018 23:52:13 GMT  
		Size: 43.1 MB (43109349 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1dd3e9bbb1f760ff8cab41817920c5822422ba1eaab36a233c8f43348791e03d`  
		Last Modified: Sat, 05 May 2018 10:29:53 GMT  
		Size: 9.7 MB (9722189 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5534647756e8399143ad6e1639b6433b9a3364809ac4520f62199ea46e638a2e`  
		Last Modified: Sat, 05 May 2018 10:29:50 GMT  
		Size: 4.1 MB (4088086 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:caabf35448f16b9e3326e8f780f01877aba13f9ec6815f975d4da42043dbf329`  
		Last Modified: Sat, 05 May 2018 13:00:53 GMT  
		Size: 839.3 KB (839299 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0802d24798c77025ece2adb6489409aa0f5789f4e82aa4242a0d9d622696157a`  
		Last Modified: Sat, 05 May 2018 13:00:52 GMT  
		Size: 248.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:32ab48d1ba995a67328f25f0660cdf40027abdd6587d59727f7ba0f72c4beb4b`  
		Last Modified: Sat, 05 May 2018 13:00:53 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1c450eedb74d167d4e5fc41e7d53a2b506218189e9184552476d6a66b9cad348`  
		Last Modified: Tue, 15 May 2018 11:02:00 GMT  
		Size: 112.7 MB (112745447 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e8f571a7544609d6069b1a1275b0c87cd79aace6c30f4537b8860f62b95d6a06`  
		Last Modified: Tue, 15 May 2018 11:01:25 GMT  
		Size: 272.1 KB (272102 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:34b4674fc63d5eff3b6225d3ac6a2964c78ecd76985c7af768ea2d4f8d75cee3`  
		Last Modified: Tue, 22 May 2018 00:03:46 GMT  
		Size: 1.8 KB (1756 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:313a47b9bc01dc6ebe710c4fa5533f658a8294c99e286317668b4ed8235eb02d`  
		Last Modified: Tue, 22 May 2018 00:03:46 GMT  
		Size: 153.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:dfccf602ebd8935455cd091dbbefb382b42de0584638c09b36850b32083bafaf`  
		Last Modified: Tue, 22 May 2018 00:03:45 GMT  
		Size: 8.4 MB (8398494 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:87d48350cf8ad80ccde0a7265bfbf2adb916ec84ab39441ec3454b46062fc2a5`  
		Last Modified: Tue, 22 May 2018 00:03:44 GMT  
		Size: 139.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c089d9983b3b2676887b3ecc4c2a6f39ac56807a56bcc82de4b0743fe11d5089`  
		Last Modified: Tue, 22 May 2018 00:03:43 GMT  
		Size: 2.0 KB (1994 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3b003992c7a1b0f04243967722ebb1995d9ef6487ba9dc911ad4a24173fb79fb`  
		Last Modified: Tue, 22 May 2018 00:03:44 GMT  
		Size: 126.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9028bed29275f46cdd8fc454c9da16a02fa103f4ab7c05e443e180ee5985b2e4`  
		Last Modified: Tue, 22 May 2018 00:03:44 GMT  
		Size: 1.4 KB (1387 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `jetty:latest` - linux; 386

```console
$ docker pull jetty@sha256:6d25a0c2bbd6976168d8e38e610f388b241f1fca7dad573e7525f0b2a5562a06
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **193.5 MB (193503016 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:6b8e9868c2ce8f4fb6e384afcd400bf23d40132115dd756423e3526983974c39`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["java","-jar","\/usr\/local\/jetty\/start.jar"]`

```dockerfile
# Sat, 28 Apr 2018 10:41:35 GMT
ADD file:df99f919c7f5a407abee5c74ea019e497e559a75bdd21b36ae581e81230884c3 in / 
# Sat, 28 Apr 2018 10:41:36 GMT
CMD ["bash"]
# Wed, 06 Jun 2018 11:41:50 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Wed, 06 Jun 2018 11:42:02 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Wed, 06 Jun 2018 13:25:33 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Wed, 06 Jun 2018 13:25:33 GMT
ENV LANG=C.UTF-8
# Wed, 06 Jun 2018 13:25:34 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Wed, 06 Jun 2018 13:25:35 GMT
RUN ln -svT "/usr/lib/jvm/java-8-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Wed, 06 Jun 2018 13:25:35 GMT
ENV JAVA_HOME=/docker-java-home/jre
# Wed, 06 Jun 2018 13:25:36 GMT
ENV JAVA_VERSION=8u171
# Wed, 06 Jun 2018 13:25:36 GMT
ENV JAVA_DEBIAN_VERSION=8u171-b11-1~deb9u1
# Wed, 06 Jun 2018 13:25:36 GMT
ENV CA_CERTIFICATES_JAVA_VERSION=20170531+nmu1
# Wed, 06 Jun 2018 13:27:39 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-8-jre="$JAVA_DEBIAN_VERSION" 		ca-certificates-java="$CA_CERTIFICATES_JAVA_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Wed, 06 Jun 2018 13:27:41 GMT
RUN /var/lib/dpkg/info/ca-certificates-java.postinst configure
# Wed, 06 Jun 2018 15:26:25 GMT
RUN groupadd -r jetty && useradd -r -g jetty jetty
# Wed, 06 Jun 2018 15:26:25 GMT
ENV JETTY_HOME=/usr/local/jetty
# Wed, 06 Jun 2018 15:26:26 GMT
ENV PATH=/usr/local/jetty/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Wed, 06 Jun 2018 15:26:26 GMT
RUN mkdir -p "$JETTY_HOME"
# Wed, 06 Jun 2018 15:26:27 GMT
WORKDIR /usr/local/jetty
# Wed, 06 Jun 2018 15:26:27 GMT
ENV JETTY_VERSION=9.4.9.v20180320
# Wed, 06 Jun 2018 15:26:27 GMT
ENV JETTY_TGZ_URL=https://repo1.maven.org/maven2/org/eclipse/jetty/jetty-home/9.4.9.v20180320/jetty-home-9.4.9.v20180320.tar.gz
# Wed, 06 Jun 2018 15:26:27 GMT
ENV JETTY_GPG_KEYS=AED5EE6C45D0FE8D5D1B164F27DED4BF6216DB8F 	2A684B57436A81FA8706B53C61C3351A438A3B7D 	5989BAF76217B843D66BE55B2D0E1FB8FE4B68B4 	B59B67FD7904984367F931800818D9D68FB67BAC 	BFBB21C246D7776836287A48A04E0C74ABB35FEA 	8B096546B1A8F02656B15D3B1677D141BCF3584D 	FBA2B18D238AB852DF95745C76157BDF03D0DCD6 	5C9579B3DB2E506429319AAEF33B071B29559E1E
# Wed, 06 Jun 2018 15:26:38 GMT
RUN set -xe 	&& curl -SL "$JETTY_TGZ_URL" -o jetty.tar.gz 	&& curl -SL "$JETTY_TGZ_URL.asc" -o jetty.tar.gz.asc 	&& export GNUPGHOME="$(mktemp -d)" 	&& for key in $JETTY_GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; done 	&& gpg --batch --verify jetty.tar.gz.asc jetty.tar.gz 	&& rm -rf "$GNUPGHOME" 	&& tar -xvf jetty.tar.gz --strip-components=1 	&& sed -i '/jetty-logging/d' etc/jetty.conf 	&& rm jetty.tar.gz* 	&& rm -rf /tmp/hsperfdata_root
# Wed, 06 Jun 2018 15:26:42 GMT
ENV JETTY_BASE=/var/lib/jetty
# Wed, 06 Jun 2018 15:26:43 GMT
RUN mkdir -p "$JETTY_BASE"
# Wed, 06 Jun 2018 15:26:43 GMT
WORKDIR /var/lib/jetty
# Wed, 06 Jun 2018 15:26:45 GMT
RUN set -xe 	&& java -jar "$JETTY_HOME/start.jar" --create-startd --add-to-start="server,http,deploy,jsp,jstl,ext,resources,websocket" 	&& chown -R jetty:jetty "$JETTY_BASE" 	&& rm -rf /tmp/hsperfdata_root
# Wed, 06 Jun 2018 15:26:45 GMT
ENV TMPDIR=/tmp/jetty
# Wed, 06 Jun 2018 15:26:46 GMT
RUN set -xe 	&& mkdir -p "$TMPDIR" 	&& chown -R jetty:jetty "$TMPDIR"
# Wed, 06 Jun 2018 15:26:46 GMT
COPY multi:4510ce2f7fb9540fb389937165085b97c71d4b0659b22ddb7dfe601528a7461a in / 
# Wed, 06 Jun 2018 15:26:50 GMT
USER [jetty]
# Wed, 06 Jun 2018 15:26:51 GMT
EXPOSE 8080/tcp
# Wed, 06 Jun 2018 15:26:51 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Wed, 06 Jun 2018 15:26:51 GMT
CMD ["java" "-jar" "/usr/local/jetty/start.jar"]
```

-	Layers:
	-	`sha256:5b858ae16eb844c6834e74a5c76644142d36957121de3f9bccf66d4c10b18816`  
		Last Modified: Sat, 28 Apr 2018 10:48:56 GMT  
		Size: 46.0 MB (46044885 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:45fb0be3608d00a27aadd5246acebfa684875786308e5e07bd72ecedb1ea550e`  
		Last Modified: Wed, 06 Jun 2018 12:17:46 GMT  
		Size: 10.8 MB (10784612 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:109b3030038f2425d43d6f1796554d59323fd256fe621bd3a73249279da3a2e7`  
		Last Modified: Wed, 06 Jun 2018 12:17:44 GMT  
		Size: 4.6 MB (4555092 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ce9368f221b5993380993dea9613572425804a20fb7a28368a6c413c683c4b78`  
		Last Modified: Wed, 06 Jun 2018 13:53:10 GMT  
		Size: 862.0 KB (861961 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:aeb0b6ad7dffce934718a1eece17485c3985405e4b761ef2e415e374233c3bfe`  
		Last Modified: Wed, 06 Jun 2018 13:53:09 GMT  
		Size: 249.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:30b827593226eaebe84f8f5fe0bceefecc60f4fcc7ef359d5f3b243ff5dc2a7a`  
		Last Modified: Wed, 06 Jun 2018 13:53:09 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:baa491a3dfa1d75fa06a5eda7de8d13355b6a33d6f8a1a850145b1ccefeef655`  
		Last Modified: Wed, 06 Jun 2018 13:55:28 GMT  
		Size: 122.6 MB (122579904 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:199c43dfdde147981dba29fa7660f2f61adc4a897a5f821c3c49fedbdbebf13d`  
		Last Modified: Wed, 06 Jun 2018 13:53:09 GMT  
		Size: 272.1 KB (272139 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3804b79adc267847411f085fbdf7fdd140ef1833984b3b15ee193550282f58bd`  
		Last Modified: Wed, 06 Jun 2018 15:28:34 GMT  
		Size: 1.7 KB (1742 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:054e5781cf365159e0530284ebbfdcef90b06bdf57f97cd93ef7830b6eeae3d6`  
		Last Modified: Wed, 06 Jun 2018 15:28:34 GMT  
		Size: 152.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b1d130f6b95b1fa39fb841c582d6a666318882063cf57ebcd0eba5ed1bf7c71c`  
		Last Modified: Wed, 06 Jun 2018 15:28:36 GMT  
		Size: 8.4 MB (8398501 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ffa56e6e02a2f593f915fbe68d3a529c08c1435078cc9a31fc9602802a509a8c`  
		Last Modified: Wed, 06 Jun 2018 15:28:31 GMT  
		Size: 139.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4fb4f6610685ca15e17e06ea21ac99b8ac8b7521386f914ffaf371596fd9a9cf`  
		Last Modified: Wed, 06 Jun 2018 15:28:31 GMT  
		Size: 2.0 KB (1996 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:18e50c48e4dcf43cda6aa3861b0643fe8af1fad643ae9b14845705e4afd2baac`  
		Last Modified: Wed, 06 Jun 2018 15:28:31 GMT  
		Size: 126.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:13a2757915974b33e351af332a9c0a812c99efd2a859e3e5c89ab5366fca783e`  
		Last Modified: Wed, 06 Jun 2018 15:28:32 GMT  
		Size: 1.4 KB (1387 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `jetty:latest` - linux; ppc64le

```console
$ docker pull jetty@sha256:a309d618d56b59cd6d782c38f010f1b543bb7b7bd7a71903084815d9a7035ab7
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **183.9 MB (183929820 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:5b05495264153d702d7a76cac0af9875b1d53a86693bb86f9ba1678105c468bc`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["java","-jar","\/usr\/local\/jetty\/start.jar"]`

```dockerfile
# Sat, 28 Apr 2018 08:20:30 GMT
ADD file:ae8b79396496eb2731c9fe7f159d6f3086ec59dd9c418c6d93780fc8cb685d2b in / 
# Sat, 28 Apr 2018 08:20:31 GMT
CMD ["bash"]
# Sat, 05 May 2018 09:39:52 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 09:40:13 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Sat, 05 May 2018 14:27:10 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 14:27:10 GMT
ENV LANG=C.UTF-8
# Sat, 05 May 2018 14:27:13 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Sat, 05 May 2018 14:27:15 GMT
RUN ln -svT "/usr/lib/jvm/java-8-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Sat, 05 May 2018 14:27:16 GMT
ENV JAVA_HOME=/docker-java-home/jre
# Sat, 05 May 2018 14:27:17 GMT
ENV JAVA_VERSION=8u171
# Sat, 05 May 2018 14:27:18 GMT
ENV JAVA_DEBIAN_VERSION=8u171-b11-1~deb9u1
# Sat, 05 May 2018 14:27:19 GMT
ENV CA_CERTIFICATES_JAVA_VERSION=20170531+nmu1
# Tue, 15 May 2018 08:55:36 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-8-jre="$JAVA_DEBIAN_VERSION" 		ca-certificates-java="$CA_CERTIFICATES_JAVA_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Tue, 15 May 2018 08:55:39 GMT
RUN /var/lib/dpkg/info/ca-certificates-java.postinst configure
# Mon, 21 May 2018 23:51:37 GMT
RUN groupadd -r jetty && useradd -r -g jetty jetty
# Mon, 21 May 2018 23:51:37 GMT
ENV JETTY_HOME=/usr/local/jetty
# Mon, 21 May 2018 23:51:38 GMT
ENV PATH=/usr/local/jetty/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Mon, 21 May 2018 23:51:40 GMT
RUN mkdir -p "$JETTY_HOME"
# Mon, 21 May 2018 23:51:41 GMT
WORKDIR /usr/local/jetty
# Mon, 21 May 2018 23:51:41 GMT
ENV JETTY_VERSION=9.4.9.v20180320
# Mon, 21 May 2018 23:51:42 GMT
ENV JETTY_TGZ_URL=https://repo1.maven.org/maven2/org/eclipse/jetty/jetty-home/9.4.9.v20180320/jetty-home-9.4.9.v20180320.tar.gz
# Mon, 21 May 2018 23:51:42 GMT
ENV JETTY_GPG_KEYS=AED5EE6C45D0FE8D5D1B164F27DED4BF6216DB8F 	2A684B57436A81FA8706B53C61C3351A438A3B7D 	5989BAF76217B843D66BE55B2D0E1FB8FE4B68B4 	B59B67FD7904984367F931800818D9D68FB67BAC 	BFBB21C246D7776836287A48A04E0C74ABB35FEA 	8B096546B1A8F02656B15D3B1677D141BCF3584D 	FBA2B18D238AB852DF95745C76157BDF03D0DCD6 	5C9579B3DB2E506429319AAEF33B071B29559E1E
# Mon, 21 May 2018 23:51:50 GMT
RUN set -xe 	&& curl -SL "$JETTY_TGZ_URL" -o jetty.tar.gz 	&& curl -SL "$JETTY_TGZ_URL.asc" -o jetty.tar.gz.asc 	&& export GNUPGHOME="$(mktemp -d)" 	&& for key in $JETTY_GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; done 	&& gpg --batch --verify jetty.tar.gz.asc jetty.tar.gz 	&& rm -rf "$GNUPGHOME" 	&& tar -xvf jetty.tar.gz --strip-components=1 	&& sed -i '/jetty-logging/d' etc/jetty.conf 	&& rm jetty.tar.gz* 	&& rm -rf /tmp/hsperfdata_root
# Mon, 21 May 2018 23:51:51 GMT
ENV JETTY_BASE=/var/lib/jetty
# Mon, 21 May 2018 23:51:53 GMT
RUN mkdir -p "$JETTY_BASE"
# Mon, 21 May 2018 23:51:54 GMT
WORKDIR /var/lib/jetty
# Mon, 21 May 2018 23:51:58 GMT
RUN set -xe 	&& java -jar "$JETTY_HOME/start.jar" --create-startd --add-to-start="server,http,deploy,jsp,jstl,ext,resources,websocket" 	&& chown -R jetty:jetty "$JETTY_BASE" 	&& rm -rf /tmp/hsperfdata_root
# Mon, 21 May 2018 23:51:59 GMT
ENV TMPDIR=/tmp/jetty
# Mon, 21 May 2018 23:52:01 GMT
RUN set -xe 	&& mkdir -p "$TMPDIR" 	&& chown -R jetty:jetty "$TMPDIR"
# Mon, 21 May 2018 23:52:01 GMT
COPY multi:4510ce2f7fb9540fb389937165085b97c71d4b0659b22ddb7dfe601528a7461a in / 
# Mon, 21 May 2018 23:52:02 GMT
USER [jetty]
# Mon, 21 May 2018 23:52:03 GMT
EXPOSE 8080/tcp
# Mon, 21 May 2018 23:52:03 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Mon, 21 May 2018 23:52:04 GMT
CMD ["java" "-jar" "/usr/local/jetty/start.jar"]
```

-	Layers:
	-	`sha256:5c65288cd974eda27ef2a891c3b15c52c38c5a1c74befed7d569db78cbcb88b4`  
		Last Modified: Sat, 28 Apr 2018 08:29:36 GMT  
		Size: 45.6 MB (45590843 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:49669ce29c6ff5b318515a879172199a17519151b56113a98648e4e5b813e9b0`  
		Last Modified: Sat, 05 May 2018 11:03:44 GMT  
		Size: 10.0 MB (9975625 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d2f38ff4299d23fa1e29678b39bfeb1549f444a54368faf8f03460a72b6951e8`  
		Last Modified: Sat, 05 May 2018 11:03:41 GMT  
		Size: 4.3 MB (4289600 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:17203acf831d7ce3c0083203f72c3b68e4468f55cb133ea3305f88143a073e21`  
		Last Modified: Sat, 05 May 2018 15:10:17 GMT  
		Size: 848.5 KB (848471 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7630f2f73d5d5304426ffaa4f8b6ed757211759ea6dac51fbbc2ebc31da0f6b5`  
		Last Modified: Sat, 05 May 2018 15:10:15 GMT  
		Size: 247.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:147e6c56e0f1ed24316695f6989c7884a847373c348caab3697c9778a99f5f07`  
		Last Modified: Sat, 05 May 2018 15:10:15 GMT  
		Size: 133.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1a03020fe000223738c6fb4c54965bf73e0b405cb6ce49d2929616496a6671ee`  
		Last Modified: Tue, 15 May 2018 09:41:42 GMT  
		Size: 114.5 MB (114548492 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7fcd57884ad8e8f10404947e0a2f6f8f2d8717f6930a1b1e98570b775561a985`  
		Last Modified: Tue, 15 May 2018 09:41:01 GMT  
		Size: 272.1 KB (272081 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9b76dee9fd822817ea8703d06608f1094bca872e94fc20da073d15cb7dc22927`  
		Last Modified: Tue, 22 May 2018 00:00:09 GMT  
		Size: 1.8 KB (1756 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a5ed2bac9736a9acd63747976da13d023ded5ee31098f3cbc2528aef9962fb72`  
		Last Modified: Tue, 22 May 2018 00:00:09 GMT  
		Size: 183.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4e37b333afe8655ea8faf63cd64859d702cbd9a2ef04658244948553969f1af4`  
		Last Modified: Tue, 22 May 2018 00:00:08 GMT  
		Size: 8.4 MB (8398608 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ec4ccd2f6f684b2add7daaca160c4f32e2d5e8ac40b59a0cf7de61d7ca3a2002`  
		Last Modified: Tue, 22 May 2018 00:00:06 GMT  
		Size: 171.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:301621a77ece9a831887327b05f85e8cc6a7f55e5e3fb3f0b80caa732a576d9c`  
		Last Modified: Tue, 22 May 2018 00:00:06 GMT  
		Size: 2.1 KB (2066 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:95fb8af7239f402edab72e4b25e3260cba2ddef00f4532a714b0994d5cff27f7`  
		Last Modified: Tue, 22 May 2018 00:00:06 GMT  
		Size: 157.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ae8f67ed49e791c0a0b51f5cee9ef88b44312ae23de072172b456615a5487173`  
		Last Modified: Tue, 22 May 2018 00:00:06 GMT  
		Size: 1.4 KB (1387 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `jetty:latest` - linux; s390x

```console
$ docker pull jetty@sha256:d1fcd865e15fa961a173af1d6fdf50ef349e957e830304a23954708cfbb3c9dd
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **183.5 MB (183531900 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:e13651cf8fdc91f1dfc215fbbbcadb79265fff9891af12f5ac1cbbe0bd16b047`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["java","-jar","\/usr\/local\/jetty\/start.jar"]`

```dockerfile
# Sat, 28 Apr 2018 11:45:04 GMT
ADD file:cb13df185b5fc36710007c3b4ec6f239ac340ff9c69cbec1e38fcf974766179b in / 
# Sat, 28 Apr 2018 11:45:04 GMT
CMD ["bash"]
# Sat, 05 May 2018 12:35:52 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 12:35:58 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Sat, 05 May 2018 13:12:32 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 13:12:32 GMT
ENV LANG=C.UTF-8
# Sat, 05 May 2018 13:12:33 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Sat, 05 May 2018 13:12:35 GMT
RUN ln -svT "/usr/lib/jvm/java-8-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Sat, 05 May 2018 13:12:38 GMT
ENV JAVA_HOME=/docker-java-home/jre
# Sat, 05 May 2018 13:12:40 GMT
ENV JAVA_VERSION=8u171
# Sat, 05 May 2018 13:12:40 GMT
ENV JAVA_DEBIAN_VERSION=8u171-b11-1~deb9u1
# Sat, 05 May 2018 13:12:40 GMT
ENV CA_CERTIFICATES_JAVA_VERSION=20170531+nmu1
# Tue, 15 May 2018 12:08:10 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-8-jre="$JAVA_DEBIAN_VERSION" 		ca-certificates-java="$CA_CERTIFICATES_JAVA_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Tue, 15 May 2018 12:08:14 GMT
RUN /var/lib/dpkg/info/ca-certificates-java.postinst configure
# Mon, 21 May 2018 23:50:49 GMT
RUN groupadd -r jetty && useradd -r -g jetty jetty
# Mon, 21 May 2018 23:50:49 GMT
ENV JETTY_HOME=/usr/local/jetty
# Mon, 21 May 2018 23:50:49 GMT
ENV PATH=/usr/local/jetty/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Mon, 21 May 2018 23:50:49 GMT
RUN mkdir -p "$JETTY_HOME"
# Mon, 21 May 2018 23:50:50 GMT
WORKDIR /usr/local/jetty
# Mon, 21 May 2018 23:50:50 GMT
ENV JETTY_VERSION=9.4.9.v20180320
# Mon, 21 May 2018 23:50:50 GMT
ENV JETTY_TGZ_URL=https://repo1.maven.org/maven2/org/eclipse/jetty/jetty-home/9.4.9.v20180320/jetty-home-9.4.9.v20180320.tar.gz
# Mon, 21 May 2018 23:50:50 GMT
ENV JETTY_GPG_KEYS=AED5EE6C45D0FE8D5D1B164F27DED4BF6216DB8F 	2A684B57436A81FA8706B53C61C3351A438A3B7D 	5989BAF76217B843D66BE55B2D0E1FB8FE4B68B4 	B59B67FD7904984367F931800818D9D68FB67BAC 	BFBB21C246D7776836287A48A04E0C74ABB35FEA 	8B096546B1A8F02656B15D3B1677D141BCF3584D 	FBA2B18D238AB852DF95745C76157BDF03D0DCD6 	5C9579B3DB2E506429319AAEF33B071B29559E1E
# Mon, 21 May 2018 23:50:54 GMT
RUN set -xe 	&& curl -SL "$JETTY_TGZ_URL" -o jetty.tar.gz 	&& curl -SL "$JETTY_TGZ_URL.asc" -o jetty.tar.gz.asc 	&& export GNUPGHOME="$(mktemp -d)" 	&& for key in $JETTY_GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; done 	&& gpg --batch --verify jetty.tar.gz.asc jetty.tar.gz 	&& rm -rf "$GNUPGHOME" 	&& tar -xvf jetty.tar.gz --strip-components=1 	&& sed -i '/jetty-logging/d' etc/jetty.conf 	&& rm jetty.tar.gz* 	&& rm -rf /tmp/hsperfdata_root
# Mon, 21 May 2018 23:50:54 GMT
ENV JETTY_BASE=/var/lib/jetty
# Mon, 21 May 2018 23:50:55 GMT
RUN mkdir -p "$JETTY_BASE"
# Mon, 21 May 2018 23:50:55 GMT
WORKDIR /var/lib/jetty
# Mon, 21 May 2018 23:50:57 GMT
RUN set -xe 	&& java -jar "$JETTY_HOME/start.jar" --create-startd --add-to-start="server,http,deploy,jsp,jstl,ext,resources,websocket" 	&& chown -R jetty:jetty "$JETTY_BASE" 	&& rm -rf /tmp/hsperfdata_root
# Mon, 21 May 2018 23:50:57 GMT
ENV TMPDIR=/tmp/jetty
# Mon, 21 May 2018 23:50:58 GMT
RUN set -xe 	&& mkdir -p "$TMPDIR" 	&& chown -R jetty:jetty "$TMPDIR"
# Mon, 21 May 2018 23:50:58 GMT
COPY multi:4510ce2f7fb9540fb389937165085b97c71d4b0659b22ddb7dfe601528a7461a in / 
# Mon, 21 May 2018 23:50:58 GMT
USER [jetty]
# Mon, 21 May 2018 23:50:58 GMT
EXPOSE 8080/tcp
# Mon, 21 May 2018 23:50:59 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Mon, 21 May 2018 23:50:59 GMT
CMD ["java" "-jar" "/usr/local/jetty/start.jar"]
```

-	Layers:
	-	`sha256:9793d586559922dfd1f10be65f3cabffaf1d31f81660ef474409da1f4f675fc7`  
		Last Modified: Sat, 28 Apr 2018 11:50:58 GMT  
		Size: 45.2 MB (45185265 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c85f5ec4e23ee12af518c5fcad0035942a1f87ec2088506cee32142c1c65f61a`  
		Last Modified: Sat, 05 May 2018 12:48:28 GMT  
		Size: 10.3 MB (10300914 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9c2eea9e27e3fa96462ebe8337d9b6cdcd7d157804dcc45590711a4a7408f64d`  
		Last Modified: Sat, 05 May 2018 12:48:26 GMT  
		Size: 4.4 MB (4366581 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0166337c6e17b20d7d4fb723da6a535d23154595e4d1ad3d202477443fa0995e`  
		Last Modified: Sat, 05 May 2018 13:27:13 GMT  
		Size: 863.8 KB (863834 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:14f0ee2131874c6a7464bde2461423c039b3b5619213c6d24a854309b8f8d576`  
		Last Modified: Sat, 05 May 2018 13:27:13 GMT  
		Size: 248.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7817f7dd1a5ad263c322f89a143e52039554a9075d064e719b53009e30da9bdd`  
		Last Modified: Sat, 05 May 2018 13:27:13 GMT  
		Size: 132.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:156807582416ebe446a379f304cdbc1ee0fc96975631b0c269060cf8b258a5c9`  
		Last Modified: Tue, 15 May 2018 12:42:53 GMT  
		Size: 114.1 MB (114138683 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fbcd0d7c10c55efd2b652e72817a60f735465b255bc58b9ec5779258434f6f1a`  
		Last Modified: Tue, 15 May 2018 12:42:27 GMT  
		Size: 272.2 KB (272186 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4606bef5727e99a6bddcb7ee80e0fd53312f59ce028a37cb0ff53419be78c0a3`  
		Last Modified: Mon, 21 May 2018 23:59:55 GMT  
		Size: 1.8 KB (1753 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0e1030ae4aa802bb70a6c77028281182ac61cf8dbdc264e1834d4a6059e70acc`  
		Last Modified: Mon, 21 May 2018 23:59:55 GMT  
		Size: 152.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:76861329fad8fd5fe81ea5e093da92909b0fc65634f4e852c0c409677fbb9703`  
		Last Modified: Mon, 21 May 2018 23:59:54 GMT  
		Size: 8.4 MB (8398504 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a42c0770a357401dc2d9a88f62ada9d2296b5da476db80bfb9b7a3e7e22b4039`  
		Last Modified: Mon, 21 May 2018 23:59:53 GMT  
		Size: 139.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3323a0f6020e59ba87cad2098b391525618b52084e4f4ea48d81d8827c556c73`  
		Last Modified: Mon, 21 May 2018 23:59:53 GMT  
		Size: 2.0 KB (1995 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:572d651b01df87de46273a6109c57878f033bfe2ba6f4d5df6c01c20a8fd10f2`  
		Last Modified: Mon, 21 May 2018 23:59:54 GMT  
		Size: 125.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bb23e0a52974fe112577ab9f53aba2fe8248c5620af53a7f9a5b0f0ebb127fd8`  
		Last Modified: Mon, 21 May 2018 23:59:54 GMT  
		Size: 1.4 KB (1389 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
