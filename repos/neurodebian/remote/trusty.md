## `neurodebian:trusty`

```console
$ docker pull neurodebian@sha256:468061bd8b34e1f5fc5f89d169b3cee1939f31568c06ddd0ad50ba62fbda691e
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `neurodebian:trusty` - linux; amd64

```console
$ docker pull neurodebian@sha256:660800318f6247ff3200b344388e8248fcb9bc73d8722d4350077395b86c29b1
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **73.2 MB (73240460 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:0433af0f61448bce6f0ca252f8f2dc95e9e38a0c3143fff76f6843f897dde7ba`
-	Default Command: `["\/bin\/bash"]`

```dockerfile
# Tue, 05 Jun 2018 21:21:33 GMT
ADD file:3c65bdbcf1318520e7af157cb00317c8312ec16bcaf181d0db919c45f0d7a85e in / 
# Tue, 05 Jun 2018 21:21:34 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Tue, 05 Jun 2018 21:21:35 GMT
RUN rm -rf /var/lib/apt/lists/*
# Tue, 05 Jun 2018 21:21:35 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Tue, 05 Jun 2018 21:21:36 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Tue, 05 Jun 2018 21:21:36 GMT
CMD ["/bin/bash"]
# Tue, 05 Jun 2018 21:58:07 GMT
RUN set -x 	&& apt-get update 	&& { 		which gpg 		|| apt-get install -y --no-install-recommends gnupg 	; } 	&& { 		gpg --version | grep -q '^gpg (GnuPG) 1\.' 		|| apt-get install -y --no-install-recommends dirmngr 	; } 	&& rm -rf /var/lib/apt/lists/*
# Tue, 05 Jun 2018 21:58:08 GMT
RUN set -x 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys DD95CC430502E37EF840ACEEA5D32F012649A5A9 	&& gpg --export DD95CC430502E37EF840ACEEA5D32F012649A5A9 > /etc/apt/trusted.gpg.d/neurodebian.gpg 	&& rm -rf "$GNUPGHOME" 	&& apt-key list | grep neurodebian
# Tue, 05 Jun 2018 21:58:08 GMT
RUN { 	echo 'deb http://neuro.debian.net/debian trusty main'; 	echo 'deb http://neuro.debian.net/debian data main'; 	echo '#deb-src http://neuro.debian.net/debian-devel trusty main'; } > /etc/apt/sources.list.d/neurodebian.sources.list
```

-	Layers:
	-	`sha256:28bfaceaff9b7464b1e768b0af7e1efe7877a34f238f935c36978a1ecf82c9b1`  
		Last Modified: Mon, 04 Jun 2018 14:56:53 GMT  
		Size: 73.2 MB (73162466 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ac540055f2f8da75b6587a88763021178d876a2b789ff0c696fbdb62485b62cd`  
		Last Modified: Tue, 05 Jun 2018 21:24:10 GMT  
		Size: 72.7 KB (72656 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2965585ef8b8370dc8c443e35c743ba723ee427c515535e3ff35d898804cacf9`  
		Last Modified: Tue, 05 Jun 2018 21:24:10 GMT  
		Size: 631.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2416bb9f3ad2b5b0c700a4412e2ffbb671f001c45b4b7433ecdcc9c352847814`  
		Last Modified: Tue, 05 Jun 2018 21:24:10 GMT  
		Size: 849.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:93b55a6a680757144baae1671d00d4328eee63e790ab36b27d8d52ceb62b179f`  
		Last Modified: Tue, 05 Jun 2018 21:24:12 GMT  
		Size: 162.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8bfe03761c0c8255267669fd9db82cfd1006445faeb0017ce0fe2953d149d57f`  
		Last Modified: Tue, 05 Jun 2018 22:02:38 GMT  
		Size: 309.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:95305fed7940884de04ef0ac16b2d0d00bc041822d003efb07dffea17cf60010`  
		Last Modified: Tue, 05 Jun 2018 22:02:38 GMT  
		Size: 3.1 KB (3143 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:32a07f3b562669eab64113e0ea6c3f590a6144fb809186cdd2b7e0a5dbb92bd3`  
		Last Modified: Tue, 05 Jun 2018 22:02:38 GMT  
		Size: 244.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
