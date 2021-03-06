## `golang:1-nanoserver-sac2016`

```console
$ docker pull golang@sha256:1771fa371ec5f742ccea7f01676e5141b06d0dab7e1f099e677c147449acda38
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	windows version 10.0.14393.2248; amd64

### `golang:1-nanoserver-sac2016` - windows version 10.0.14393.2248; amd64

```console
$ docker pull golang@sha256:b0f9d634b73cdc441928c453a10349bfc142a7527c4ec2fc40b7e5af2b7219b9
```

-	Docker Version: 17.10.0-ee-preview-3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **554.2 MB (554190052 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:a6ce20c487f84301bb9a0b5a0bf289aec636ab94c757d93412e4106efa69a745`
-	Default Command: `["c:\\windows\\system32\\cmd.exe"]`
-	`SHELL`: `["powershell","-Command","$ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';"]`

```dockerfile
# Tue, 13 Dec 2016 10:47:17 GMT
RUN Apply image 10.0.14393.0
# Mon, 07 May 2018 18:11:43 GMT
RUN Install update 10.0.14393.2248
# Thu, 10 May 2018 09:55:16 GMT
SHELL [powershell -Command $ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';]
# Sat, 09 Jun 2018 09:41:57 GMT
ENV GOPATH=C:\gopath
# Sat, 09 Jun 2018 09:43:02 GMT
RUN $newPath = ('{0}\bin;C:\go\bin;{1}' -f $env:GOPATH, $env:PATH); 	Write-Host ('Updating PATH: {0}' -f $newPath); 	setx /M PATH $newPath;
# Sat, 09 Jun 2018 09:43:03 GMT
ENV GOLANG_VERSION=1.10.3
# Sat, 09 Jun 2018 09:47:30 GMT
RUN $url = ('https://golang.org/dl/go{0}.windows-amd64.zip' -f $env:GOLANG_VERSION); 	Write-Host ('Downloading {0} ...' -f $url); 	Invoke-WebRequest -Uri $url -OutFile 'go.zip'; 		$sha256 = 'a3f19d4fc0f4b45836b349503e347e64e31ab830dedac2fc9c390836d4418edb'; 	Write-Host ('Verifying sha256 ({0}) ...' -f $sha256); 	if ((Get-FileHash go.zip -Algorithm sha256).Hash -ne $sha256) { 		Write-Host 'FAILED!'; 		exit 1; 	}; 		Write-Host 'Expanding ...'; 	Expand-Archive go.zip -DestinationPath C:\; 		Write-Host 'Verifying install ("go version") ...'; 	go version; 		Write-Host 'Removing ...'; 	Remove-Item go.zip -Force; 		Write-Host 'Complete.';
# Sat, 09 Jun 2018 09:47:32 GMT
WORKDIR C:\gopath
```

-	Layers:
	-	`sha256:bce2fbc256ea437a87dadac2f69aabd25bed4f56255549090056c1131fad0277`  
		Last Modified: Tue, 13 Dec 2016 10:47:17 GMT  
		Size: 252.7 MB (252691002 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:58518d66816013a4ae1ec4ef454beff05e957b515f6c364b45fe76b8a527e022`  
		Last Modified: Mon, 07 May 2018 18:11:43 GMT  
		Size: 164.9 MB (164879119 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:5103fe12c5d5b7e7e3ac7c4ccd5eb2bb702cda6e059223bed89c8286737936de`  
		Last Modified: Thu, 10 May 2018 10:19:37 GMT  
		Size: 926.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:38862e7999ca3af579f46a1337c644ddf29e323299b678d144fbe0082b3bb9c0`  
		Last Modified: Sat, 09 Jun 2018 10:18:33 GMT  
		Size: 947.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bf4ed2e0ae3b8e4ed9252adf1050223e80bf81088e938e465b60e070fbe57483`  
		Last Modified: Sat, 09 Jun 2018 10:18:34 GMT  
		Size: 927.0 KB (926981 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6a4cb430068615d640288f96c3be6d82a84267520bc71e6425bd6989e1e8ed3b`  
		Last Modified: Sat, 09 Jun 2018 10:18:33 GMT  
		Size: 946.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:df38b51aa9bf7242e02452bcc5096a97b2efcef452d3994ad4cd6a1998f355ae`  
		Last Modified: Sat, 09 Jun 2018 10:20:11 GMT  
		Size: 135.7 MB (135689000 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:578c6e24a34537373b1d376abaf306ab851e2ee07c4dd5d5927dd3c3100ce3c4`  
		Last Modified: Sat, 09 Jun 2018 10:18:33 GMT  
		Size: 1.1 KB (1131 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
