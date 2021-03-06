## `couchbase:enterprise-4.6.5`

```console
$ docker pull couchbase@sha256:550c724fd0f8f5b3c115a7b64ffd2e214e519ebe0f9d4d9947ccdd50aef672b2
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `couchbase:enterprise-4.6.5` - linux; amd64

```console
$ docker pull couchbase@sha256:9884d5e8e15ac4f8b89c5357e3383d2733fc82072372ef9226032562120ac177
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **219.1 MB (219112182 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:b2d8260d376c14a50a8b8f7f9bdaa1f53ba72cf66069723c2526dc9f2a6c1a4e`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["couchbase-server"]`

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
# Tue, 05 Jun 2018 21:37:42 GMT
MAINTAINER Couchbase Docker Team <docker@couchbase.com>
# Thu, 14 Jun 2018 05:22:44 GMT
RUN apt-get update &&     apt-get install -yq runit wget python-httplib2 chrpath tzdata     lsof lshw sysstat net-tools numactl  &&     apt-get autoremove && apt-get clean &&     rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
# Thu, 14 Jun 2018 05:22:44 GMT
ARG CB_VERSION=4.6.5
# Thu, 14 Jun 2018 05:22:44 GMT
ARG CB_RELEASE_URL=https://packages.couchbase.com/releases
# Thu, 14 Jun 2018 05:22:44 GMT
ARG CB_PACKAGE=couchbase-server-enterprise_4.6.5-ubuntu14.04_amd64.deb
# Thu, 14 Jun 2018 05:22:45 GMT
ARG CB_SHA256=f1629c70ea9a13f88ddf70923dcfb6e05f9840a1bfee0b7150a80c930d25917f
# Thu, 14 Jun 2018 05:22:45 GMT
ENV PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/opt/couchbase/bin:/opt/couchbase/bin/tools:/opt/couchbase/bin/install
# Thu, 14 Jun 2018 05:22:46 GMT
# ARGS: CB_PACKAGE=couchbase-server-enterprise_4.6.5-ubuntu14.04_amd64.deb CB_RELEASE_URL=https://packages.couchbase.com/releases CB_SHA256=f1629c70ea9a13f88ddf70923dcfb6e05f9840a1bfee0b7150a80c930d25917f CB_VERSION=4.6.5
RUN groupadd -g 1000 couchbase && useradd couchbase -u 1000 -g couchbase -M
# Thu, 14 Jun 2018 05:23:14 GMT
# ARGS: CB_PACKAGE=couchbase-server-enterprise_4.6.5-ubuntu14.04_amd64.deb CB_RELEASE_URL=https://packages.couchbase.com/releases CB_SHA256=f1629c70ea9a13f88ddf70923dcfb6e05f9840a1bfee0b7150a80c930d25917f CB_VERSION=4.6.5
RUN export INSTALL_DONT_START_SERVER=1 &&     wget -N $CB_RELEASE_URL/$CB_VERSION/$CB_PACKAGE &&     echo "$CB_SHA256  $CB_PACKAGE" | sha256sum -c - &&     dpkg -i ./$CB_PACKAGE && rm -f ./$CB_PACKAGE
# Thu, 14 Jun 2018 05:23:14 GMT
COPY file:9a90647aed4e88ee15c7efe9abbafbf7a89c3174cbe85d6b5492cde1aa9c6355 in /etc/service/couchbase-server/run 
# Thu, 14 Jun 2018 05:23:15 GMT
# ARGS: CB_PACKAGE=couchbase-server-enterprise_4.6.5-ubuntu14.04_amd64.deb CB_RELEASE_URL=https://packages.couchbase.com/releases CB_SHA256=f1629c70ea9a13f88ddf70923dcfb6e05f9840a1bfee0b7150a80c930d25917f CB_VERSION=4.6.5
RUN chown -R couchbase:couchbase /etc/service
# Thu, 14 Jun 2018 05:23:15 GMT
COPY file:8196fd8e201c5fc3873a0faa3cec28b0d85633e363c0c5788434f5b9a81cfa5b in /usr/local/bin/ 
# Thu, 14 Jun 2018 05:23:16 GMT
# ARGS: CB_PACKAGE=couchbase-server-enterprise_4.6.5-ubuntu14.04_amd64.deb CB_RELEASE_URL=https://packages.couchbase.com/releases CB_SHA256=f1629c70ea9a13f88ddf70923dcfb6e05f9840a1bfee0b7150a80c930d25917f CB_VERSION=4.6.5
RUN ln -s dummy.sh /usr/local/bin/iptables-save &&     ln -s dummy.sh /usr/local/bin/lvdisplay &&     ln -s dummy.sh /usr/local/bin/vgdisplay &&     ln -s dummy.sh /usr/local/bin/pvdisplay
# Thu, 14 Jun 2018 05:23:17 GMT
# ARGS: CB_PACKAGE=couchbase-server-enterprise_4.6.5-ubuntu14.04_amd64.deb CB_RELEASE_URL=https://packages.couchbase.com/releases CB_SHA256=f1629c70ea9a13f88ddf70923dcfb6e05f9840a1bfee0b7150a80c930d25917f CB_VERSION=4.6.5
RUN chrpath -r '$ORIGIN/../lib' /opt/couchbase/bin/curl
# Thu, 14 Jun 2018 05:23:17 GMT
COPY file:5d67fa23771c82cbce2e1a74900e7c0ce4d1466a002273f57ab13d52d6b844b3 in / 
# Thu, 14 Jun 2018 05:23:17 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Thu, 14 Jun 2018 05:23:18 GMT
CMD ["couchbase-server"]
# Thu, 14 Jun 2018 05:23:18 GMT
EXPOSE 11207/tcp 11210/tcp 11211/tcp 18091/tcp 18092/tcp 18093/tcp 18094/tcp 8091/tcp 8092/tcp 8093/tcp 8094/tcp
# Thu, 14 Jun 2018 05:23:18 GMT
VOLUME [/opt/couchbase/var]
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
	-	`sha256:c65043da38bf6d1125f0a3258db417dbf91e4da9da1003de91112f359bf19742`  
		Last Modified: Thu, 14 Jun 2018 05:27:14 GMT  
		Size: 11.4 MB (11391228 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b9c351a3e138faf5520e7ad3290bf9e0bd8b706fd251ff325ed6ed0afe4f5ee4`  
		Last Modified: Thu, 14 Jun 2018 05:27:10 GMT  
		Size: 1.9 KB (1914 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e84a722d459890b0599884905c05555c56b27a5051b79d1f3eec00b830b4cdb1`  
		Last Modified: Thu, 14 Jun 2018 05:27:34 GMT  
		Size: 134.4 MB (134374746 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a0af4d5487acd65b08fb029754afddb3ea4823fbf8e4f703aeab0efab14f2bed`  
		Last Modified: Thu, 14 Jun 2018 05:27:10 GMT  
		Size: 401.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f9dd86a7126f9cdf6fccaa11bcb2b044fdb66df3be47e23df401f697df926a2a`  
		Last Modified: Thu, 14 Jun 2018 05:27:08 GMT  
		Size: 410.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:722393181e191a951634447c84a6dc7dda72f909aaf70f94e089996ded422e0f`  
		Last Modified: Thu, 14 Jun 2018 05:27:08 GMT  
		Size: 237.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:821d9683905c42ecac1b56a728af5e09bbde43a96bfe61a50c67bed21c7c6a9d`  
		Last Modified: Thu, 14 Jun 2018 05:27:09 GMT  
		Size: 218.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:931dfec6483f07646de752e3ccb5fa42651d7678d95e975539eaec2eaa33a578`  
		Last Modified: Thu, 14 Jun 2018 05:27:08 GMT  
		Size: 105.4 KB (105407 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:da356de10db9b123938c144d217cc465860b1620264b45badd102e0d2bd0f784`  
		Last Modified: Thu, 14 Jun 2018 05:27:08 GMT  
		Size: 857.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
