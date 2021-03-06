## `python:rc-windowsservercore-1709`

```console
$ docker pull python@sha256:77e775224ac363362a607dc1675c24392658b5ba7d8be8045e0990cb688ea9d7
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	windows version 10.0.16299.431; amd64

### `python:rc-windowsservercore-1709` - windows version 10.0.16299.431; amd64

```console
$ docker pull python@sha256:6c0aee9520ae1204d33a8b65a81acfd3a30c9c24db374ec577b70ec84e7ed327
```

-	Docker Version: 17.10.0-ee-preview-3
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **3.1 GB (3137829689 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:61b50ff6799698bf315cd0a487cef60d6f84519ebc2b6ddc965e8ea1951cce48`
-	Default Command: `["python"]`
-	`SHELL`: `["powershell","-Command","$ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';"]`

```dockerfile
# Fri, 29 Sep 2017 14:43:28 GMT
RUN Apply image 10.0.16299.15
# Sat, 05 May 2018 14:37:10 GMT
RUN Install update 10.0.16299.431
# Thu, 10 May 2018 09:50:49 GMT
SHELL [powershell -Command $ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';]
# Thu, 07 Jun 2018 09:20:32 GMT
ENV PYTHON_VERSION=3.7.0b5
# Thu, 07 Jun 2018 09:20:33 GMT
ENV PYTHON_RELEASE=3.7.0
# Thu, 07 Jun 2018 09:23:04 GMT
RUN $url = ('https://www.python.org/ftp/python/{0}/python-{1}-amd64.exe' -f $env:PYTHON_RELEASE, $env:PYTHON_VERSION); 	Write-Host ('Downloading {0} ...' -f $url); 	[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; 	Invoke-WebRequest -Uri $url -OutFile 'python.exe'; 		Write-Host 'Installing ...'; 	Start-Process python.exe -Wait 		-ArgumentList @( 			'/quiet', 			'InstallAllUsers=1', 			'TargetDir=C:\Python', 			'PrependPath=1', 			'Shortcuts=0', 			'Include_doc=0', 			'Include_pip=0', 			'Include_test=0' 		); 		$env:PATH = [Environment]::GetEnvironmentVariable('PATH', [EnvironmentVariableTarget]::Machine); 		Write-Host 'Verifying install ...'; 	Write-Host '  python --version'; python --version; 		Write-Host 'Removing ...'; 	Remove-Item python.exe -Force; 		Write-Host 'Complete.';
# Thu, 07 Jun 2018 09:23:05 GMT
ENV PYTHON_PIP_VERSION=10.0.1
# Thu, 07 Jun 2018 09:24:33 GMT
RUN Write-Host ('Installing pip=={0} ...' -f $env:PYTHON_PIP_VERSION); 	[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; 	Invoke-WebRequest -Uri 'https://bootstrap.pypa.io/get-pip.py' -OutFile 'get-pip.py'; 	python get-pip.py 		--disable-pip-version-check 		--no-cache-dir 		('pip=={0}' -f $env:PYTHON_PIP_VERSION) 	; 	Remove-Item get-pip.py -Force; 		Write-Host 'Verifying pip install ...'; 	pip --version; 		Write-Host 'Complete.';
# Thu, 07 Jun 2018 09:24:35 GMT
CMD ["python"]
```

-	Layers:
	-	`sha256:5847a47b8593f7c39aa5e3db09e50b76d42aa8898c0440c70cc9c69747d4c479`  
		Last Modified: Tue, 17 Oct 2017 15:51:05 GMT  
		Size: 2.3 GB (2274300585 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:af675e5054a0dfb3eb70b140f566a5dbe612b5212e4a4ef2a2991308740d1006`  
		Last Modified: Tue, 08 May 2018 18:45:22 GMT  
		Size: 805.9 MB (805944217 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:b0d3f2c48ca5c41c53fe84071bb55725c2d6c36c8840dcef5297cc048ffe39aa`  
		Last Modified: Thu, 10 May 2018 10:18:48 GMT  
		Size: 1.2 KB (1174 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ed3e6ad204381048428447014f319818b49ab2951d0017773952bdba66171406`  
		Last Modified: Thu, 07 Jun 2018 09:26:02 GMT  
		Size: 1.2 KB (1187 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:12f2d8c7f984b7869b54e69f83e6a3504f8065269b4ba601493e7a1e01ec36ef`  
		Last Modified: Thu, 07 Jun 2018 09:26:00 GMT  
		Size: 1.2 KB (1192 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c7928c54c82924333992c4669bd311d5ebc6735cfb2f2f18e29a5300de93790d`  
		Last Modified: Thu, 07 Jun 2018 09:26:23 GMT  
		Size: 48.1 MB (48148839 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:80c48d52ca501f7706ffd8f63d5db0fe332e5f77c7999cbbd1d656cb5a0d0275`  
		Last Modified: Thu, 07 Jun 2018 09:25:58 GMT  
		Size: 1.2 KB (1177 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:789aedc1037b7c0cb782d0667a3c8e07cc7bfe3fc6e0abfe12b976036acaf7ea`  
		Last Modified: Thu, 07 Jun 2018 09:26:09 GMT  
		Size: 9.4 MB (9430147 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6bdd83734abddf9ff823b8b90b29e171a5e1504a29f6d828edee7a2ec15a8dfe`  
		Last Modified: Thu, 07 Jun 2018 09:25:58 GMT  
		Size: 1.2 KB (1171 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
