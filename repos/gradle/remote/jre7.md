## `gradle:jre7`

```console
$ docker pull gradle@sha256:4a4266974879ea6451e3d52e47f35b3fb0b1b8a07db849f3e087d8366561cc71
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

### `gradle:jre7` - linux; amd64

```console
$ docker pull gradle@sha256:346d016406891e7f9b542f7033e486f20eed46311fb4e8fb07546656a35f697a
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **230.8 MB (230798526 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:b08ccf729b522aff3c7d8ca12925f4f131c505ce0cda45dee90c9fb301b2f26d`
-	Default Command: `["gradle"]`

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
# Tue, 19 Jun 2018 18:22:57 GMT
CMD ["gradle"]
# Tue, 19 Jun 2018 18:22:57 GMT
ENV GRADLE_HOME=/opt/gradle
# Tue, 19 Jun 2018 18:22:57 GMT
ENV GRADLE_VERSION=4.8
# Tue, 19 Jun 2018 18:22:57 GMT
ARG GRADLE_DOWNLOAD_SHA256=f3e29692a8faa94eb0b02ebf36fa263a642b3ae8694ef806c45c345b8683f1ba
# Tue, 19 Jun 2018 18:23:58 GMT
# ARGS: GRADLE_DOWNLOAD_SHA256=f3e29692a8faa94eb0b02ebf36fa263a642b3ae8694ef806c45c345b8683f1ba
RUN set -o errexit -o nounset 	&& echo "Downloading Gradle" 	&& wget --no-verbose --output-document=gradle.zip "https://services.gradle.org/distributions/gradle-${GRADLE_VERSION}-bin.zip" 		&& echo "Checking download hash" 	&& echo "${GRADLE_DOWNLOAD_SHA256} *gradle.zip" | sha256sum --check - 		&& echo "Installing Gradle" 	&& unzip gradle.zip 	&& rm gradle.zip 	&& mv "gradle-${GRADLE_VERSION}" "${GRADLE_HOME}/" 	&& ln --symbolic "${GRADLE_HOME}/bin/gradle" /usr/bin/gradle 		&& echo "Adding gradle user and group" 	&& groupadd --system --gid 1000 gradle 	&& useradd --system --gid gradle --uid 1000 --shell /bin/bash --create-home gradle 	&& mkdir /home/gradle/.gradle 	&& chown --recursive gradle:gradle /home/gradle 		&& echo "Symlinking root Gradle cache to gradle Gradle cache" 	&& ln -s /home/gradle/.gradle /root/.gradle
# Tue, 19 Jun 2018 18:23:58 GMT
USER [gradle]
# Tue, 19 Jun 2018 18:23:58 GMT
VOLUME [/home/gradle/.gradle]
# Tue, 19 Jun 2018 18:23:58 GMT
WORKDIR /home/gradle
# Tue, 19 Jun 2018 18:24:01 GMT
# ARGS: GRADLE_DOWNLOAD_SHA256=f3e29692a8faa94eb0b02ebf36fa263a642b3ae8694ef806c45c345b8683f1ba
RUN set -o errexit -o nounset 	&& echo "Testing Gradle installation" 	&& gradle --version
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
	-	`sha256:4c903cd4cc1d3199babac70671cf8343c83fb1bb8d6fc306b6c7743669f44135`  
		Last Modified: Tue, 19 Jun 2018 18:32:26 GMT  
		Size: 75.9 MB (75872982 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b2634d51501575e9e7dc896c4cac06bc6699de397d981ccc301147c8ebbea427`  
		Last Modified: Tue, 19 Jun 2018 18:29:55 GMT  
		Size: 140.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `gradle:jre7` - linux; arm variant v5

```console
$ docker pull gradle@sha256:cf531fe519c06e6efff1159d27e17948a9ea897ba5edf0da0809175846475860
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **218.2 MB (218164666 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:3d385997dcd7c933fbd1b2bf2c273fc69ec14195d358084b76fa7d6a83046cb6`
-	Default Command: `["gradle"]`

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
# Wed, 20 Jun 2018 08:49:21 GMT
CMD ["gradle"]
# Wed, 20 Jun 2018 08:49:21 GMT
ENV GRADLE_HOME=/opt/gradle
# Wed, 20 Jun 2018 08:49:22 GMT
ENV GRADLE_VERSION=4.8
# Wed, 20 Jun 2018 08:49:22 GMT
ARG GRADLE_DOWNLOAD_SHA256=f3e29692a8faa94eb0b02ebf36fa263a642b3ae8694ef806c45c345b8683f1ba
# Wed, 20 Jun 2018 08:49:28 GMT
# ARGS: GRADLE_DOWNLOAD_SHA256=f3e29692a8faa94eb0b02ebf36fa263a642b3ae8694ef806c45c345b8683f1ba
RUN set -o errexit -o nounset 	&& echo "Downloading Gradle" 	&& wget --no-verbose --output-document=gradle.zip "https://services.gradle.org/distributions/gradle-${GRADLE_VERSION}-bin.zip" 		&& echo "Checking download hash" 	&& echo "${GRADLE_DOWNLOAD_SHA256} *gradle.zip" | sha256sum --check - 		&& echo "Installing Gradle" 	&& unzip gradle.zip 	&& rm gradle.zip 	&& mv "gradle-${GRADLE_VERSION}" "${GRADLE_HOME}/" 	&& ln --symbolic "${GRADLE_HOME}/bin/gradle" /usr/bin/gradle 		&& echo "Adding gradle user and group" 	&& groupadd --system --gid 1000 gradle 	&& useradd --system --gid gradle --uid 1000 --shell /bin/bash --create-home gradle 	&& mkdir /home/gradle/.gradle 	&& chown --recursive gradle:gradle /home/gradle 		&& echo "Symlinking root Gradle cache to gradle Gradle cache" 	&& ln -s /home/gradle/.gradle /root/.gradle
# Wed, 20 Jun 2018 08:49:28 GMT
USER [gradle]
# Wed, 20 Jun 2018 08:49:29 GMT
VOLUME [/home/gradle/.gradle]
# Wed, 20 Jun 2018 08:49:29 GMT
WORKDIR /home/gradle
# Wed, 20 Jun 2018 08:49:32 GMT
# ARGS: GRADLE_DOWNLOAD_SHA256=f3e29692a8faa94eb0b02ebf36fa263a642b3ae8694ef806c45c345b8683f1ba
RUN set -o errexit -o nounset 	&& echo "Testing Gradle installation" 	&& gradle --version
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
	-	`sha256:2cf0a1d105c8861cdbe0313584ae208180363713b0cf71db884166d994e256f6`  
		Last Modified: Wed, 20 Jun 2018 08:52:29 GMT  
		Size: 75.9 MB (75873063 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9f267efd59023682a1113c39b43d78415972991e470da063565a0b9ab876f747`  
		Last Modified: Wed, 20 Jun 2018 08:52:20 GMT  
		Size: 236.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `gradle:jre7` - linux; arm variant v7

```console
$ docker pull gradle@sha256:3e6eb41c98a41829dc5111a7a222ff1d17fd295a44dcb0f498f4937ffde6320e
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **214.1 MB (214097114 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:258f0871560b5f098b9085f81c00d0b289e109c53f60fbc4b800606d44427a02`
-	Default Command: `["gradle"]`

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
# Wed, 20 Jun 2018 12:01:19 GMT
CMD ["gradle"]
# Wed, 20 Jun 2018 12:01:19 GMT
ENV GRADLE_HOME=/opt/gradle
# Wed, 20 Jun 2018 12:01:19 GMT
ENV GRADLE_VERSION=4.8
# Wed, 20 Jun 2018 12:01:20 GMT
ARG GRADLE_DOWNLOAD_SHA256=f3e29692a8faa94eb0b02ebf36fa263a642b3ae8694ef806c45c345b8683f1ba
# Wed, 20 Jun 2018 12:01:28 GMT
# ARGS: GRADLE_DOWNLOAD_SHA256=f3e29692a8faa94eb0b02ebf36fa263a642b3ae8694ef806c45c345b8683f1ba
RUN set -o errexit -o nounset 	&& echo "Downloading Gradle" 	&& wget --no-verbose --output-document=gradle.zip "https://services.gradle.org/distributions/gradle-${GRADLE_VERSION}-bin.zip" 		&& echo "Checking download hash" 	&& echo "${GRADLE_DOWNLOAD_SHA256} *gradle.zip" | sha256sum --check - 		&& echo "Installing Gradle" 	&& unzip gradle.zip 	&& rm gradle.zip 	&& mv "gradle-${GRADLE_VERSION}" "${GRADLE_HOME}/" 	&& ln --symbolic "${GRADLE_HOME}/bin/gradle" /usr/bin/gradle 		&& echo "Adding gradle user and group" 	&& groupadd --system --gid 1000 gradle 	&& useradd --system --gid gradle --uid 1000 --shell /bin/bash --create-home gradle 	&& mkdir /home/gradle/.gradle 	&& chown --recursive gradle:gradle /home/gradle 		&& echo "Symlinking root Gradle cache to gradle Gradle cache" 	&& ln -s /home/gradle/.gradle /root/.gradle
# Wed, 20 Jun 2018 12:01:28 GMT
USER [gradle]
# Wed, 20 Jun 2018 12:01:29 GMT
VOLUME [/home/gradle/.gradle]
# Wed, 20 Jun 2018 12:01:29 GMT
WORKDIR /home/gradle
# Wed, 20 Jun 2018 12:01:33 GMT
# ARGS: GRADLE_DOWNLOAD_SHA256=f3e29692a8faa94eb0b02ebf36fa263a642b3ae8694ef806c45c345b8683f1ba
RUN set -o errexit -o nounset 	&& echo "Testing Gradle installation" 	&& gradle --version
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
	-	`sha256:ace97bed112b27357ac209fec978177ffd8ad578dbe7b56ebf18e6135c45dd78`  
		Last Modified: Wed, 20 Jun 2018 12:04:50 GMT  
		Size: 75.9 MB (75873065 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3568b2a46bcbb199ca78630f9199c23f0f23822b441c646c6d45774bca830931`  
		Last Modified: Wed, 20 Jun 2018 12:04:40 GMT  
		Size: 236.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `gradle:jre7` - linux; arm64 variant v8

```console
$ docker pull gradle@sha256:7f29ad8573cf9f5a4a79ee0db7077627f879583d66ae4038ac63fe089d7eb25f
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **218.2 MB (218160332 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:6e28a704533007f0080da0a8d5a2d77274d58abca87caba7b67cccdc2668d902`
-	Default Command: `["gradle"]`

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
# Wed, 20 Jun 2018 09:26:47 GMT
CMD ["gradle"]
# Wed, 20 Jun 2018 09:26:48 GMT
ENV GRADLE_HOME=/opt/gradle
# Wed, 20 Jun 2018 09:26:48 GMT
ENV GRADLE_VERSION=4.8
# Wed, 20 Jun 2018 09:26:49 GMT
ARG GRADLE_DOWNLOAD_SHA256=f3e29692a8faa94eb0b02ebf36fa263a642b3ae8694ef806c45c345b8683f1ba
# Wed, 20 Jun 2018 09:26:59 GMT
# ARGS: GRADLE_DOWNLOAD_SHA256=f3e29692a8faa94eb0b02ebf36fa263a642b3ae8694ef806c45c345b8683f1ba
RUN set -o errexit -o nounset 	&& echo "Downloading Gradle" 	&& wget --no-verbose --output-document=gradle.zip "https://services.gradle.org/distributions/gradle-${GRADLE_VERSION}-bin.zip" 		&& echo "Checking download hash" 	&& echo "${GRADLE_DOWNLOAD_SHA256} *gradle.zip" | sha256sum --check - 		&& echo "Installing Gradle" 	&& unzip gradle.zip 	&& rm gradle.zip 	&& mv "gradle-${GRADLE_VERSION}" "${GRADLE_HOME}/" 	&& ln --symbolic "${GRADLE_HOME}/bin/gradle" /usr/bin/gradle 		&& echo "Adding gradle user and group" 	&& groupadd --system --gid 1000 gradle 	&& useradd --system --gid gradle --uid 1000 --shell /bin/bash --create-home gradle 	&& mkdir /home/gradle/.gradle 	&& chown --recursive gradle:gradle /home/gradle 		&& echo "Symlinking root Gradle cache to gradle Gradle cache" 	&& ln -s /home/gradle/.gradle /root/.gradle
# Wed, 20 Jun 2018 09:27:00 GMT
USER [gradle]
# Wed, 20 Jun 2018 09:27:01 GMT
VOLUME [/home/gradle/.gradle]
# Wed, 20 Jun 2018 09:27:03 GMT
WORKDIR /home/gradle
# Wed, 20 Jun 2018 09:27:07 GMT
# ARGS: GRADLE_DOWNLOAD_SHA256=f3e29692a8faa94eb0b02ebf36fa263a642b3ae8694ef806c45c345b8683f1ba
RUN set -o errexit -o nounset 	&& echo "Testing Gradle installation" 	&& gradle --version
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
	-	`sha256:376f6a3a7b691da2d65f456614d06735c0ea6b2639d8e8f9b6a2374dcfa6c248`  
		Last Modified: Wed, 20 Jun 2018 09:33:36 GMT  
		Size: 75.9 MB (75872972 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1e20cc56d788ec77a33a6d10972b6f6661122cb85fb71244a655365c04e62eea`  
		Last Modified: Wed, 20 Jun 2018 09:33:23 GMT  
		Size: 208.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `gradle:jre7` - linux; 386

```console
$ docker pull gradle@sha256:09397aa4182be9812de5e19b592f80f579ce07072732ee1a54062c70c940b51a
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **243.2 MB (243167290 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:d4f25f58af10968550e1ac7df3153f033cd3e473b85b7bedd4011ebdb18fe96b`
-	Default Command: `["gradle"]`

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
# Wed, 20 Jun 2018 11:08:11 GMT
CMD ["gradle"]
# Wed, 20 Jun 2018 11:08:11 GMT
ENV GRADLE_HOME=/opt/gradle
# Wed, 20 Jun 2018 11:08:11 GMT
ENV GRADLE_VERSION=4.8
# Wed, 20 Jun 2018 11:08:11 GMT
ARG GRADLE_DOWNLOAD_SHA256=f3e29692a8faa94eb0b02ebf36fa263a642b3ae8694ef806c45c345b8683f1ba
# Wed, 20 Jun 2018 11:08:22 GMT
# ARGS: GRADLE_DOWNLOAD_SHA256=f3e29692a8faa94eb0b02ebf36fa263a642b3ae8694ef806c45c345b8683f1ba
RUN set -o errexit -o nounset 	&& echo "Downloading Gradle" 	&& wget --no-verbose --output-document=gradle.zip "https://services.gradle.org/distributions/gradle-${GRADLE_VERSION}-bin.zip" 		&& echo "Checking download hash" 	&& echo "${GRADLE_DOWNLOAD_SHA256} *gradle.zip" | sha256sum --check - 		&& echo "Installing Gradle" 	&& unzip gradle.zip 	&& rm gradle.zip 	&& mv "gradle-${GRADLE_VERSION}" "${GRADLE_HOME}/" 	&& ln --symbolic "${GRADLE_HOME}/bin/gradle" /usr/bin/gradle 		&& echo "Adding gradle user and group" 	&& groupadd --system --gid 1000 gradle 	&& useradd --system --gid gradle --uid 1000 --shell /bin/bash --create-home gradle 	&& mkdir /home/gradle/.gradle 	&& chown --recursive gradle:gradle /home/gradle 		&& echo "Symlinking root Gradle cache to gradle Gradle cache" 	&& ln -s /home/gradle/.gradle /root/.gradle
# Wed, 20 Jun 2018 11:08:22 GMT
USER [gradle]
# Wed, 20 Jun 2018 11:08:23 GMT
VOLUME [/home/gradle/.gradle]
# Wed, 20 Jun 2018 11:08:23 GMT
WORKDIR /home/gradle
# Wed, 20 Jun 2018 11:08:25 GMT
# ARGS: GRADLE_DOWNLOAD_SHA256=f3e29692a8faa94eb0b02ebf36fa263a642b3ae8694ef806c45c345b8683f1ba
RUN set -o errexit -o nounset 	&& echo "Testing Gradle installation" 	&& gradle --version
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
	-	`sha256:ad0e955b97c746fc9eaee71dae1c1459ac43958e4df44de4a13abf8cb0d5675d`  
		Last Modified: Wed, 20 Jun 2018 11:14:16 GMT  
		Size: 75.9 MB (75872981 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:50952f33a6cb62ddfe8fe2dbf728d55021fd72f90eea232922893987bc9980d4`  
		Last Modified: Wed, 20 Jun 2018 11:14:00 GMT  
		Size: 139.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `gradle:jre7` - linux; ppc64le

```console
$ docker pull gradle@sha256:c9e712e4ab7ef26a610ff0ac3798fcfc3fb3687cd5e3ba8b0bd4fc741d1fc194
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **221.6 MB (221592181 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:15fd4da96424fc372facfffa3357e5ebb265750b2d4b30f6c93ad048b2f488f7`
-	Default Command: `["gradle"]`

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
# Wed, 20 Jun 2018 08:17:45 GMT
CMD ["gradle"]
# Wed, 20 Jun 2018 08:17:47 GMT
ENV GRADLE_HOME=/opt/gradle
# Wed, 20 Jun 2018 08:17:48 GMT
ENV GRADLE_VERSION=4.8
# Wed, 20 Jun 2018 08:17:48 GMT
ARG GRADLE_DOWNLOAD_SHA256=f3e29692a8faa94eb0b02ebf36fa263a642b3ae8694ef806c45c345b8683f1ba
# Wed, 20 Jun 2018 08:18:00 GMT
# ARGS: GRADLE_DOWNLOAD_SHA256=f3e29692a8faa94eb0b02ebf36fa263a642b3ae8694ef806c45c345b8683f1ba
RUN set -o errexit -o nounset 	&& echo "Downloading Gradle" 	&& wget --no-verbose --output-document=gradle.zip "https://services.gradle.org/distributions/gradle-${GRADLE_VERSION}-bin.zip" 		&& echo "Checking download hash" 	&& echo "${GRADLE_DOWNLOAD_SHA256} *gradle.zip" | sha256sum --check - 		&& echo "Installing Gradle" 	&& unzip gradle.zip 	&& rm gradle.zip 	&& mv "gradle-${GRADLE_VERSION}" "${GRADLE_HOME}/" 	&& ln --symbolic "${GRADLE_HOME}/bin/gradle" /usr/bin/gradle 		&& echo "Adding gradle user and group" 	&& groupadd --system --gid 1000 gradle 	&& useradd --system --gid gradle --uid 1000 --shell /bin/bash --create-home gradle 	&& mkdir /home/gradle/.gradle 	&& chown --recursive gradle:gradle /home/gradle 		&& echo "Symlinking root Gradle cache to gradle Gradle cache" 	&& ln -s /home/gradle/.gradle /root/.gradle
# Wed, 20 Jun 2018 08:18:01 GMT
USER [gradle]
# Wed, 20 Jun 2018 08:18:02 GMT
VOLUME [/home/gradle/.gradle]
# Wed, 20 Jun 2018 08:18:03 GMT
WORKDIR /home/gradle
# Wed, 20 Jun 2018 08:18:10 GMT
# ARGS: GRADLE_DOWNLOAD_SHA256=f3e29692a8faa94eb0b02ebf36fa263a642b3ae8694ef806c45c345b8683f1ba
RUN set -o errexit -o nounset 	&& echo "Testing Gradle installation" 	&& gradle --version
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
	-	`sha256:9b4df5253806d4e17698881094b3566b7632996ba585dc09085c7017a7c505d7`  
		Last Modified: Wed, 20 Jun 2018 08:25:18 GMT  
		Size: 75.9 MB (75873105 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ad0d9620b477124c05ff1d0c481a707f05a9ccd46f4482e3305e51de354d4342`  
		Last Modified: Wed, 20 Jun 2018 08:25:03 GMT  
		Size: 233.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `gradle:jre7` - linux; s390x

```console
$ docker pull gradle@sha256:278f5b2d7a27217332d64114aa1168d4472a0b6be792b3d40dc9cba03aa57597
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **222.6 MB (222605824 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:d3256c4545632edade81b74303d321a3abacbe501232cc0a228ef6d4361db656`
-	Default Command: `["gradle"]`

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
# Wed, 20 Jun 2018 11:42:40 GMT
CMD ["gradle"]
# Wed, 20 Jun 2018 11:42:40 GMT
ENV GRADLE_HOME=/opt/gradle
# Wed, 20 Jun 2018 11:42:42 GMT
ENV GRADLE_VERSION=4.8
# Wed, 20 Jun 2018 11:42:42 GMT
ARG GRADLE_DOWNLOAD_SHA256=f3e29692a8faa94eb0b02ebf36fa263a642b3ae8694ef806c45c345b8683f1ba
# Wed, 20 Jun 2018 11:42:46 GMT
# ARGS: GRADLE_DOWNLOAD_SHA256=f3e29692a8faa94eb0b02ebf36fa263a642b3ae8694ef806c45c345b8683f1ba
RUN set -o errexit -o nounset 	&& echo "Downloading Gradle" 	&& wget --no-verbose --output-document=gradle.zip "https://services.gradle.org/distributions/gradle-${GRADLE_VERSION}-bin.zip" 		&& echo "Checking download hash" 	&& echo "${GRADLE_DOWNLOAD_SHA256} *gradle.zip" | sha256sum --check - 		&& echo "Installing Gradle" 	&& unzip gradle.zip 	&& rm gradle.zip 	&& mv "gradle-${GRADLE_VERSION}" "${GRADLE_HOME}/" 	&& ln --symbolic "${GRADLE_HOME}/bin/gradle" /usr/bin/gradle 		&& echo "Adding gradle user and group" 	&& groupadd --system --gid 1000 gradle 	&& useradd --system --gid gradle --uid 1000 --shell /bin/bash --create-home gradle 	&& mkdir /home/gradle/.gradle 	&& chown --recursive gradle:gradle /home/gradle 		&& echo "Symlinking root Gradle cache to gradle Gradle cache" 	&& ln -s /home/gradle/.gradle /root/.gradle
# Wed, 20 Jun 2018 11:42:46 GMT
USER [gradle]
# Wed, 20 Jun 2018 11:42:46 GMT
VOLUME [/home/gradle/.gradle]
# Wed, 20 Jun 2018 11:42:46 GMT
WORKDIR /home/gradle
# Wed, 20 Jun 2018 11:42:49 GMT
# ARGS: GRADLE_DOWNLOAD_SHA256=f3e29692a8faa94eb0b02ebf36fa263a642b3ae8694ef806c45c345b8683f1ba
RUN set -o errexit -o nounset 	&& echo "Testing Gradle installation" 	&& gradle --version
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
	-	`sha256:8a14fffa161952cfb7803605927829e8732c0c690958c696c189551df2f3cf8e`  
		Last Modified: Wed, 20 Jun 2018 11:45:58 GMT  
		Size: 75.9 MB (75872988 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:059221b134e0a75cd945710bb08c012d6b6d3b1bc378e7ee80e196e2d089e6f0`  
		Last Modified: Wed, 20 Jun 2018 11:45:53 GMT  
		Size: 202.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
