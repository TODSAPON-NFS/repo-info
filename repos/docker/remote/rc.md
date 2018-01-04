## `docker:rc`

```console
$ docker pull docker@sha256:c1773783b2ca4cfcca552ef69f0bf3aa813716bf0c74e8fc587e7efb83871db1
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `docker:rc` - linux; amd64

```console
$ docker pull docker@sha256:020452ded7794c75665ac5d0d0d9977ebcb411b65916489c5d0aa584a0f7af8c
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **41.1 MB (41148865 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:196369f7600e5fee3030f400603c18f7b2dd5134f6aa014285866c563901ac13`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["sh"]`

```dockerfile
# Fri, 01 Dec 2017 18:48:48 GMT
ADD file:2b00f26f6004576e2f8faeb3fb0517a14f79ea89a059fe096b54cbecf5da512e in / 
# Fri, 01 Dec 2017 18:48:48 GMT
CMD ["/bin/sh"]
# Thu, 28 Dec 2017 00:52:44 GMT
RUN apk add --no-cache 		ca-certificates
# Thu, 28 Dec 2017 00:52:51 GMT
RUN [ ! -e /etc/nsswitch.conf ] && echo 'hosts: files dns' > /etc/nsswitch.conf
# Thu, 04 Jan 2018 22:20:00 GMT
ENV DOCKER_CHANNEL=test
# Thu, 04 Jan 2018 22:20:01 GMT
ENV DOCKER_VERSION=18.01.0-ce-rc1
# Thu, 04 Jan 2018 22:20:07 GMT
RUN set -ex; 	apk add --no-cache --virtual .fetch-deps 		curl 		tar 	; 		apkArch="$(apk --print-arch)"; 	case "$apkArch" in 		x86_64) dockerArch='x86_64' ;; 		aarch64) dockerArch='aarch64' ;; 		ppc64le) dockerArch='ppc64le' ;; 		s390x) dockerArch='s390x' ;; 		*) echo >&2 "error: unsupported architecture ($apkArch)"; exit 1 ;;	esac; 		if ! curl -fL -o docker.tgz "https://download.docker.com/linux/static/${DOCKER_CHANNEL}/${dockerArch}/docker-${DOCKER_VERSION}.tgz"; then 		echo >&2 "error: failed to download 'docker-${DOCKER_VERSION}' from '${DOCKER_CHANNEL}' for '${dockerArch}'"; 		exit 1; 	fi; 		tar --extract 		--file docker.tgz 		--strip-components 1 		--directory /usr/local/bin/ 	; 	rm docker.tgz; 		apk del .fetch-deps; 		dockerd -v; 	docker -v
# Thu, 04 Jan 2018 22:20:08 GMT
COPY file:016ebcc5aefa6b28f6c484a299057d5b236e1d4f3baf44cc76eb4cd578821691 in /usr/local/bin/modprobe 
# Thu, 04 Jan 2018 22:20:08 GMT
COPY file:0d94e1cd679f133aab807891a1b00b6aef1a9f1f884108e7a17ddf50ab88f1fb in /usr/local/bin/ 
# Thu, 04 Jan 2018 22:20:08 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Thu, 04 Jan 2018 22:20:09 GMT
CMD ["sh"]
```

-	Layers:
	-	`sha256:2fdfe1cd78c20d05774f0919be19bc1a3e4729bce219968e4188e7e0f1af679d`  
		Last Modified: Fri, 01 Dec 2017 18:50:32 GMT  
		Size: 2.1 MB (2064911 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ce5c13ed5ec7edeacb70aab480d9b1c29729d758a333abb7ed331a3b58e8a5c5`  
		Last Modified: Thu, 28 Dec 2017 00:54:34 GMT  
		Size: 308.0 KB (308018 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2078331aa194699c56e73fab217e7d9391a8ae4f7ec6e63980977dffa55d023a`  
		Last Modified: Thu, 28 Dec 2017 00:54:34 GMT  
		Size: 153.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b6f5b3e5721740cc141d714d8d67f926ed1e3a8b3e7f83ad1f11af5043844eda`  
		Last Modified: Thu, 04 Jan 2018 22:36:47 GMT  
		Size: 38.8 MB (38774493 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f6a058b055fa821dff78e6ac6572ae946d137e1f096c3357932bce1e3bd93908`  
		Last Modified: Thu, 04 Jan 2018 22:36:37 GMT  
		Size: 548.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:69a8d741812aba9c628b9e3b60fc48b640a0f4864a419152c9e30a7e72a53cde`  
		Last Modified: Thu, 04 Jan 2018 22:36:36 GMT  
		Size: 742.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip