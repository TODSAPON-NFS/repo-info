## `openjdk:10-jdk`

```console
$ docker pull openjdk@sha256:6e1c1df57ab62aef815fe9130806c2a25a2f5b7bafd585d8308ca4ba43e48c75
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

### `openjdk:10-jdk` - linux; amd64

```console
$ docker pull openjdk@sha256:278d0c45e5e84c7a15f0f70087ffa529f8340d33e36f5bb03096fe4dfa6a0aea
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **383.2 MB (383223889 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:1d2f2353dcff259eff97409e4e619e780bb6364fb1ffd07df4d165c75a0aa5c6`
-	Default Command: `["jshell"]`

```dockerfile
# Sat, 28 Apr 2018 06:49:58 GMT
ADD file:229ad62fdc5e079bf925fb084264841ce27bf7125beb1fd821cbd6ed5132b37c in / 
# Sat, 28 Apr 2018 06:49:59 GMT
CMD ["bash"]
# Tue, 05 Jun 2018 23:11:03 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 05 Jun 2018 23:11:14 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Tue, 05 Jun 2018 23:11:42 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
# Wed, 06 Jun 2018 18:37:07 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Wed, 06 Jun 2018 18:37:07 GMT
ENV LANG=C.UTF-8
# Wed, 06 Jun 2018 18:37:08 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Wed, 06 Jun 2018 18:41:05 GMT
RUN ln -svT "/usr/lib/jvm/java-10-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Wed, 06 Jun 2018 18:41:05 GMT
ENV JAVA_HOME=/docker-java-home
# Wed, 06 Jun 2018 18:41:06 GMT
ENV JAVA_VERSION=10.0.1+10
# Wed, 06 Jun 2018 18:41:06 GMT
ENV JAVA_DEBIAN_VERSION=10.0.1+10-4
# Wed, 06 Jun 2018 18:41:56 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		ln -svT /docker-java-home/bin/java /usr/local/bin/java; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-10-jdk="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		rm -v /usr/local/bin/java; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Wed, 06 Jun 2018 18:41:58 GMT
CMD ["jshell"]
```

-	Layers:
	-	`sha256:e7cb83f94a464daabb5fa4e63ae521d65d7956bfcb3619bc75857f7d598ff12c`  
		Last Modified: Sat, 28 Apr 2018 08:58:22 GMT  
		Size: 48.3 MB (48303234 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ea75eac4dae2f20cbd6fa1d55bc23e09e128934c845cd07f16ce17d88bf39af5`  
		Last Modified: Tue, 05 Jun 2018 23:39:45 GMT  
		Size: 7.0 MB (7030508 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:45c35a0f820b4b715ac0c1825dacb71e27c6e5bbbc9320b94c42a479cb1f55eb`  
		Last Modified: Tue, 05 Jun 2018 23:39:49 GMT  
		Size: 10.3 MB (10334570 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:13e481985cd9dca6c878949c3145def08ffe2ba39481efa8dc57e2c0b89a0c59`  
		Last Modified: Tue, 05 Jun 2018 23:40:23 GMT  
		Size: 54.2 MB (54212985 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6c942941f5ce00ee2e081e13dd67ff5fed2948620fbc15b681b5300b463ebca7`  
		Last Modified: Wed, 06 Jun 2018 18:49:42 GMT  
		Size: 894.6 KB (894567 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e28271fcddffcd2ea90dab95cb35ad34560319bc7020318ea43c4d2eb967b7c3`  
		Last Modified: Wed, 06 Jun 2018 18:49:42 GMT  
		Size: 239.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7ae09137d16eb2f446014174e18af023b5133b533c925a607d026e62e1f8d6ce`  
		Last Modified: Wed, 06 Jun 2018 18:57:40 GMT  
		Size: 130.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3469457e729fe8b69d85043096815338213a0e5fde462f71b69bdb77b519fb59`  
		Last Modified: Wed, 06 Jun 2018 18:58:28 GMT  
		Size: 262.4 MB (262447656 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `openjdk:10-jdk` - linux; arm variant v5

```console
$ docker pull openjdk@sha256:6b6d4408be1cd745eb1d5f9399d9e8d413f9db187722e8256bf2427b794956d0
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **347.2 MB (347174637 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:a965c95f501b7d6c41959e768db12a736d5da402fd689c19ac669007c9e1d6cd`
-	Default Command: `["jshell"]`

```dockerfile
# Sat, 28 Apr 2018 08:51:39 GMT
ADD file:289dd78ee91d70cba0d1bc2f296c3c14565c2fc5a7545ded07d727de72e2c7af in / 
# Sat, 28 Apr 2018 08:51:39 GMT
CMD ["bash"]
# Sat, 05 May 2018 08:57:49 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 08:57:59 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Sat, 05 May 2018 08:58:33 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 09:21:49 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 09:21:49 GMT
ENV LANG=C.UTF-8
# Sat, 05 May 2018 09:21:50 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Sat, 05 May 2018 09:26:03 GMT
RUN ln -svT "/usr/lib/jvm/java-10-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Sat, 05 May 2018 09:26:03 GMT
ENV JAVA_HOME=/docker-java-home
# Sat, 05 May 2018 09:26:04 GMT
ENV JAVA_VERSION=10.0.1+10
# Thu, 10 May 2018 08:56:00 GMT
ENV JAVA_DEBIAN_VERSION=10.0.1+10-4
# Tue, 15 May 2018 09:39:11 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		ln -svT /docker-java-home/bin/java /usr/local/bin/java; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-10-jdk="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		rm -v /usr/local/bin/java; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Tue, 15 May 2018 09:39:12 GMT
CMD ["jshell"]
```

-	Layers:
	-	`sha256:e55988127988d265ae9a533cadc5ee50c9a724a2602f8677daa3d5ca1354a4c8`  
		Last Modified: Sat, 28 Apr 2018 08:59:59 GMT  
		Size: 46.3 MB (46298645 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:aafc48823c28e5748b4391dec0c3ace05a68f5a65301bb16529fbf5cfdcf4ba2`  
		Last Modified: Sat, 05 May 2018 09:11:24 GMT  
		Size: 7.8 MB (7807554 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fab5f6db056b1ea7d4547374cc334a044271698f505521bb613b98b4e9d62fff`  
		Last Modified: Sat, 05 May 2018 09:11:25 GMT  
		Size: 9.2 MB (9194241 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ec4a548afcc00660ef6218b8d28d348b5de3b94fefc87bef82631c42056e8ee6`  
		Last Modified: Sat, 05 May 2018 09:11:57 GMT  
		Size: 50.2 MB (50176924 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ae6ec5ea4e73a466f57a6b546a9cad55615bd6493881162d69fcfbb397d6b75a`  
		Last Modified: Sat, 05 May 2018 09:43:09 GMT  
		Size: 888.9 KB (888926 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6c28e493916dad869bef88266b645a09302349c9f0452455f2ef5ed2a9d423a4`  
		Last Modified: Sat, 05 May 2018 09:43:08 GMT  
		Size: 235.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d37338fb29dd7da20721d69f3938756bbebee06803e38164d58c3b7a25736ed2`  
		Last Modified: Sat, 05 May 2018 09:49:31 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6f25ed4b476f8f7ed7678913d34e1196a93c5ca318b9ebf7076f6684b993765a`  
		Last Modified: Tue, 15 May 2018 10:06:33 GMT  
		Size: 232.8 MB (232807981 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `openjdk:10-jdk` - linux; arm variant v7

```console
$ docker pull openjdk@sha256:78c988a2ac5610aeaa66b1bdc5e25209eeb0f9c87be66e012fb1a8ab369e272f
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **343.1 MB (343142171 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:69dba11c6783638dd166b35fe2e2acf38b5c6d5c043035f800736d785f1981aa`
-	Default Command: `["jshell"]`

```dockerfile
# Sat, 28 Apr 2018 12:02:19 GMT
ADD file:b8fa078b9ddc39737b1c9eaeea11c4d1a71fb53d2ac6747fa0eab346280119a5 in / 
# Sat, 28 Apr 2018 12:02:20 GMT
CMD ["bash"]
# Sat, 05 May 2018 12:10:42 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 12:10:53 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Sat, 05 May 2018 12:11:25 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 12:50:09 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 12:50:09 GMT
ENV LANG=C.UTF-8
# Sat, 05 May 2018 12:50:10 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Sat, 05 May 2018 12:54:19 GMT
RUN ln -svT "/usr/lib/jvm/java-10-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Sat, 05 May 2018 12:54:20 GMT
ENV JAVA_HOME=/docker-java-home
# Sat, 05 May 2018 12:54:20 GMT
ENV JAVA_VERSION=10.0.1+10
# Thu, 10 May 2018 12:11:38 GMT
ENV JAVA_DEBIAN_VERSION=10.0.1+10-4
# Tue, 15 May 2018 12:11:14 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		ln -svT /docker-java-home/bin/java /usr/local/bin/java; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-10-jdk="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		rm -v /usr/local/bin/java; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Tue, 15 May 2018 12:11:24 GMT
CMD ["jshell"]
```

-	Layers:
	-	`sha256:bd36ef86ab3a0249a38384d63e39dbf85bd3f64d4e9ae0179795e2da5754d3fc`  
		Last Modified: Sat, 28 Apr 2018 12:13:46 GMT  
		Size: 44.2 MB (44193727 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f2182099ef994efdc26b1608eeb96ebb41405847c6f253e40c752ec9246cce60`  
		Last Modified: Sat, 05 May 2018 12:33:28 GMT  
		Size: 7.5 MB (7535807 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f5fedbfebaf2860a81e319ee9a8c18137fb801f56d7729af7b4698f98e05c62b`  
		Last Modified: Sat, 05 May 2018 12:33:28 GMT  
		Size: 8.9 MB (8899307 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:496b1250aadf8322a3300af60aa0258966c4b2c12109c11bd182477c5514ef26`  
		Last Modified: Sat, 05 May 2018 12:34:02 GMT  
		Size: 47.9 MB (47926773 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:629e5fac21e671f199fc1cac252e622d21a20f37e79fe3630532931d2bb40e5f`  
		Last Modified: Sat, 05 May 2018 13:12:55 GMT  
		Size: 871.5 KB (871492 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fa7a7248d3ef3e6ee57ebcf46bc34d79eb8c65a74f73193128b9736553a5e46d`  
		Last Modified: Sat, 05 May 2018 13:12:55 GMT  
		Size: 237.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:18de89152980cab32e413ac53ff8e637b08ae9e52e2faee33192d07438741943`  
		Last Modified: Sat, 05 May 2018 13:20:03 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9cc4eff30625d836150eed97c5e420c0c2745a20fabe5324c028fc7c8a284ca4`  
		Last Modified: Tue, 15 May 2018 12:44:25 GMT  
		Size: 233.7 MB (233714697 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `openjdk:10-jdk` - linux; arm64 variant v8

```console
$ docker pull openjdk@sha256:5848a33b14fad33def8709b1231a62233b5d50ba16ffa6e87062395fdbc0a4bd
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **352.4 MB (352403982 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:7292b7f9f694cbcb77ffd5dbfcac6730b4d979eb2b3d88416c3a9ec8b6542d0a`
-	Default Command: `["jshell"]`

```dockerfile
# Mon, 30 Apr 2018 23:27:31 GMT
ADD file:ebaa7f02c60ac8138d085ce979847d36a1a8ce243bcef9b7e81e3e667d060dcb in / 
# Mon, 30 Apr 2018 23:27:34 GMT
CMD ["bash"]
# Sat, 05 May 2018 09:27:56 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 09:28:24 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Sat, 05 May 2018 09:30:21 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 11:20:10 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 11:20:11 GMT
ENV LANG=C.UTF-8
# Sat, 05 May 2018 11:20:15 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Sat, 05 May 2018 11:39:58 GMT
RUN ln -svT "/usr/lib/jvm/java-10-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Sat, 05 May 2018 11:39:59 GMT
ENV JAVA_HOME=/docker-java-home
# Sat, 05 May 2018 11:40:00 GMT
ENV JAVA_VERSION=10.0.1+10
# Thu, 10 May 2018 10:24:33 GMT
ENV JAVA_DEBIAN_VERSION=10.0.1+10-4
# Tue, 15 May 2018 09:25:05 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		ln -svT /docker-java-home/bin/java /usr/local/bin/java; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-10-jdk="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		rm -v /usr/local/bin/java; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Tue, 15 May 2018 09:25:09 GMT
CMD ["jshell"]
```

-	Layers:
	-	`sha256:ed5c004c8effeb24e6eee983af18662b0d28341fbbd46983746399c6df3358c8`  
		Last Modified: Mon, 30 Apr 2018 23:47:36 GMT  
		Size: 45.6 MB (45610129 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8023415c45ba32335bb869e25328b3b2c70e3ad264f1129bb133addb1fbfef4a`  
		Last Modified: Sat, 05 May 2018 10:25:46 GMT  
		Size: 7.9 MB (7867437 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2793192206e4ab032f5152356b71ea402af9d6cfd3812ad4e29857c76a039af6`  
		Last Modified: Sat, 05 May 2018 10:25:45 GMT  
		Size: 9.2 MB (9190303 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:04e033c04a8296917467f1a5f58f33424a0c62e7f1ad7bc521d1a04a30491463`  
		Last Modified: Sat, 05 May 2018 10:26:49 GMT  
		Size: 50.8 MB (50809602 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8751d53eb40e199ecd3910be45e09c6c039df9cf93ff8d670dbeea5b482f73af`  
		Last Modified: Sat, 05 May 2018 12:42:04 GMT  
		Size: 881.3 KB (881341 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1938d575c214b836cf8b48efd7a34cc415cc6910744792cbf930f8a0db1a557d`  
		Last Modified: Sat, 05 May 2018 12:42:04 GMT  
		Size: 238.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f233056ca4e8e4182f4e424772fe1bbb116f4a12222adeaaceec03a398d5f3b1`  
		Last Modified: Sat, 05 May 2018 12:51:39 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9f4fa745d17ac9138fc1e54a324706492b6c90e4e9dfcfed08c3f31c95eac537`  
		Last Modified: Tue, 15 May 2018 10:45:44 GMT  
		Size: 238.0 MB (238044801 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `openjdk:10-jdk` - linux; 386

```console
$ docker pull openjdk@sha256:6016acd62e853b92901140056489a54bf3c8cf8f74a469e9d4f37f5094b05a2f
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **393.0 MB (392956369 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:56b741fc6c4f24e780c75ac06144d05a44d8ab67a2aac0b09ca14b664d3293b1`
-	Default Command: `["jshell"]`

```dockerfile
# Sat, 28 Apr 2018 10:40:49 GMT
ADD file:cb21908d8f286f1381ea180209120314676afa1ce4d5d480e0310fe70a4c96d4 in / 
# Sat, 28 Apr 2018 10:40:49 GMT
CMD ["bash"]
# Wed, 06 Jun 2018 11:38:33 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Wed, 06 Jun 2018 11:38:47 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Wed, 06 Jun 2018 11:39:21 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
# Wed, 06 Jun 2018 13:17:33 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Wed, 06 Jun 2018 13:17:33 GMT
ENV LANG=C.UTF-8
# Wed, 06 Jun 2018 13:17:34 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Wed, 06 Jun 2018 13:22:12 GMT
RUN ln -svT "/usr/lib/jvm/java-10-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Wed, 06 Jun 2018 13:22:12 GMT
ENV JAVA_HOME=/docker-java-home
# Wed, 06 Jun 2018 13:22:12 GMT
ENV JAVA_VERSION=10.0.1+10
# Wed, 06 Jun 2018 13:22:12 GMT
ENV JAVA_DEBIAN_VERSION=10.0.1+10-4
# Wed, 06 Jun 2018 13:24:16 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		ln -svT /docker-java-home/bin/java /usr/local/bin/java; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-10-jdk="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		rm -v /usr/local/bin/java; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Wed, 06 Jun 2018 13:24:17 GMT
CMD ["jshell"]
```

-	Layers:
	-	`sha256:33fb16074d5de3f73c0e2941c01c03e5dc69cfb8f568b7fbc3e29926b575fef0`  
		Last Modified: Sat, 28 Apr 2018 10:47:25 GMT  
		Size: 49.1 MB (49090181 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a686f4eb752c82ac41a17df9c6701b1f073f7a2d9e420555cd2a5cb0dcbbea8a`  
		Last Modified: Wed, 06 Jun 2018 12:14:55 GMT  
		Size: 7.2 MB (7182217 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:de9c2ebf9e0747fb0a03a84261c3698af2618b3c2fb833bdee559337f846c39f`  
		Last Modified: Wed, 06 Jun 2018 12:14:53 GMT  
		Size: 10.7 MB (10657958 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b1fde487e4c90bba22453b5178624bff1a2fa7bd6f0b83fb4d605b1f4198e932`  
		Last Modified: Wed, 06 Jun 2018 12:15:40 GMT  
		Size: 56.0 MB (55957246 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bdc753c52779b4d5229b7f48908ad306e4cff4aff3c6b3cbb29cbd7de06a0c29`  
		Last Modified: Wed, 06 Jun 2018 13:39:40 GMT  
		Size: 902.9 KB (902867 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b779bb512bf82746866821a79e233f33fea211925f996d9fc3d7a48ef50841fd`  
		Last Modified: Wed, 06 Jun 2018 13:39:39 GMT  
		Size: 237.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a1bdab517a7dd05a6a815053bb8daa7d096e0fb4a15a5eab75c632ce4ccd17a6`  
		Last Modified: Wed, 06 Jun 2018 13:47:37 GMT  
		Size: 130.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:dda47556b65b7f444fe9f61737a8bd4346ab480681065ac35048b7545a6a89ef`  
		Last Modified: Wed, 06 Jun 2018 13:50:03 GMT  
		Size: 269.2 MB (269165533 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `openjdk:10-jdk` - linux; ppc64le

```console
$ docker pull openjdk@sha256:beee18ec72b0b28bd32b526c69906974f5d7fc5caaaecf1ea73af0c106584a6a
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **369.7 MB (369692424 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:dd888fc351628f091d32d957dd26691fbf76942829a54f2e63c5cc39c3d73eb7`
-	Default Command: `["jshell"]`

```dockerfile
# Sat, 28 Apr 2018 08:19:13 GMT
ADD file:320268259acdc4e2a105be735ea4ee0cb1398bb05ce729d46f4a54fa3c3c84e3 in / 
# Sat, 28 Apr 2018 08:19:15 GMT
CMD ["bash"]
# Sat, 05 May 2018 09:16:25 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 09:16:49 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Sat, 05 May 2018 09:21:27 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 13:48:57 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 13:48:57 GMT
ENV LANG=C.UTF-8
# Sat, 05 May 2018 13:49:00 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Sat, 05 May 2018 14:16:26 GMT
RUN ln -svT "/usr/lib/jvm/java-10-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Sat, 05 May 2018 14:16:27 GMT
ENV JAVA_HOME=/docker-java-home
# Sat, 05 May 2018 14:16:27 GMT
ENV JAVA_VERSION=10.0.1+10
# Sat, 12 May 2018 09:57:57 GMT
ENV JAVA_DEBIAN_VERSION=10.0.1+10-4
# Tue, 15 May 2018 08:36:06 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		ln -svT /docker-java-home/bin/java /usr/local/bin/java; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-10-jdk="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		rm -v /usr/local/bin/java; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Tue, 15 May 2018 08:36:07 GMT
CMD ["jshell"]
```

-	Layers:
	-	`sha256:354f055c313d4d07201e01fd4de9af4aca89e3df17572870e56c5b8945e48443`  
		Last Modified: Sat, 28 Apr 2018 08:27:42 GMT  
		Size: 49.8 MB (49754912 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f77e4d2b61d28a226758713bae6bf933182cc9aa5eea6834696ef5865b36a2d2`  
		Last Modified: Sat, 05 May 2018 10:56:29 GMT  
		Size: 8.3 MB (8252158 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ee38bf91c1472a5fafe06a2f5ba7ea5bf20d82e4c77308ccb3bb26c3068d95c5`  
		Last Modified: Sat, 05 May 2018 10:56:40 GMT  
		Size: 9.7 MB (9711623 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:68a774996e1e41e16b05c537334faa52f62da8dc20585016b4be6783eecbfa27`  
		Last Modified: Sat, 05 May 2018 10:57:37 GMT  
		Size: 55.8 MB (55781554 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e73d6946d81354ab550331ff9f689d3cf70de0f32d141b34ea750d442597d8e1`  
		Last Modified: Sat, 05 May 2018 14:53:16 GMT  
		Size: 890.5 KB (890501 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1fec613ebf835d7057b5111fe9afdbbb25415edc834a99e8b38022dd88922555`  
		Last Modified: Sat, 05 May 2018 14:53:15 GMT  
		Size: 237.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e2e1da8caedef517259a3bfdf3ff479246903cf0545881bdd3b51864acc1046c`  
		Last Modified: Sat, 05 May 2018 15:01:04 GMT  
		Size: 132.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7aaa6cf73c488b469afb8ca16bdefb7af8d9e24a01e90818759de55dbbcb9688`  
		Last Modified: Tue, 15 May 2018 09:29:19 GMT  
		Size: 245.3 MB (245301307 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `openjdk:10-jdk` - linux; s390x

```console
$ docker pull openjdk@sha256:c4986c3788469975d95f170cc1911e7bffd89166ecb7289fd2f8e215ace0fdbb
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **338.2 MB (338188624 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:d7aa169a3d9997e84247abfada77a7538e0a4b862f7d140741f7821371a0723e`
-	Default Command: `["jshell"]`

```dockerfile
# Sat, 28 Apr 2018 11:43:52 GMT
ADD file:2ebc77cf35fadaf6ffd85f0d203bf60b217e15aa3c15737aac14f71008535107 in / 
# Sat, 28 Apr 2018 11:43:52 GMT
CMD ["bash"]
# Sat, 05 May 2018 12:33:51 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		netbase 		wget 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 12:34:01 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
# Sat, 05 May 2018 12:34:24 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 13:05:56 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Sat, 05 May 2018 13:05:56 GMT
ENV LANG=C.UTF-8
# Sat, 05 May 2018 13:05:57 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Sat, 05 May 2018 13:08:24 GMT
RUN ln -svT "/usr/lib/jvm/java-10-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Sat, 05 May 2018 13:08:24 GMT
ENV JAVA_HOME=/docker-java-home
# Sat, 05 May 2018 13:08:24 GMT
ENV JAVA_VERSION=10.0.1+10
# Thu, 10 May 2018 13:05:47 GMT
ENV JAVA_DEBIAN_VERSION=10.0.1+10-4
# Tue, 15 May 2018 12:00:16 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		ln -svT /docker-java-home/bin/java /usr/local/bin/java; 		apt-get update; 	apt-get install -y --no-install-recommends 		openjdk-10-jdk="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		rm -v /usr/local/bin/java; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Tue, 15 May 2018 12:00:17 GMT
CMD ["jshell"]
```

-	Layers:
	-	`sha256:893cc85742608c84d1d6314416656d650a83dae134d0d1e22a839b39a03cbf3e`  
		Last Modified: Sat, 28 Apr 2018 11:49:42 GMT  
		Size: 47.4 MB (47350246 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6465ae4acbbbfe22cde44168d0262178f375ac945898fbe73420bec2cc2ccbe0`  
		Last Modified: Sat, 05 May 2018 12:46:57 GMT  
		Size: 8.1 MB (8124442 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e47a8c562fcb2d700f3403a2f6b5d1c62f5961afce859416ff6a03520adf95a5`  
		Last Modified: Sat, 05 May 2018 12:46:57 GMT  
		Size: 9.4 MB (9414344 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:481f2ac0d700bc88441da57f26f2253a495063e8fcf46706e8462f4b16292b84`  
		Last Modified: Sat, 05 May 2018 12:47:23 GMT  
		Size: 52.3 MB (52257848 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:755b496e7ed5d1a4f90f69efc1653169b1cf721f0fd65832ce1c7c1838017e19`  
		Last Modified: Sat, 05 May 2018 13:21:22 GMT  
		Size: 906.4 KB (906357 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:340cd0adda5f0114369ab22dee2566c26d88ac2264cba92eb697d1858f314b95`  
		Last Modified: Sat, 05 May 2018 13:21:22 GMT  
		Size: 237.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2ae3dee5b02480fe3a064cdf817b8111c5e6cd2bd97ed60fd277206e31ea2b4e`  
		Last Modified: Sat, 05 May 2018 13:21:22 GMT  
		Size: 132.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c2f1b98c041ce23391ce2c4badb32705c919e7f174f8450928b1207642e9f9c0`  
		Last Modified: Tue, 15 May 2018 12:28:11 GMT  
		Size: 220.1 MB (220135018 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
