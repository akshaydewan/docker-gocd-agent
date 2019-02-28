# GoCD Agent Docker image

This repository is the parent repository for the following docker images

* [gocd/gocd-agent-alpine-3.6](https://github.com/gocd/docker-gocd-agent-alpine-3.6)
* [gocd/gocd-agent-alpine-3.7](https://github.com/gocd/docker-gocd-agent-alpine-3.7)
* [gocd/gocd-agent-alpine-3.8](https://github.com/gocd/docker-gocd-agent-alpine-3.8)
* [gocd/gocd-agent-alpine-3.9](https://github.com/gocd/docker-gocd-agent-alpine-3.9)
* [gocd/gocd-agent-centos-6](https://github.com/gocd/docker-gocd-agent-centos-6)
* [gocd/gocd-agent-centos-7](https://github.com/gocd/docker-gocd-agent-centos-7)
* [gocd/gocd-agent-debian-8](https://github.com/gocd/docker-gocd-agent-debian-8)
* [gocd/gocd-agent-debian-9](https://github.com/gocd/docker-gocd-agent-debian-9)
* [gocd/gocd-agent-docker-dind](https://github.com/gocd/gocd-agent-docker-dind)
* [gocd/gocd-agent-ubuntu-14.04](https://github.com/gocd/docker-gocd-agent-ubuntu-14.04)
* [gocd/gocd-agent-ubuntu-16.04](https://github.com/gocd/docker-gocd-agent-ubuntu-16.04)
* [gocd/gocd-agent-ubuntu-18.04](https://github.com/gocd/docker-gocd-agent-ubuntu-18.04)
* [gocd/docker-gocd-agent-fedora-28](https://github.com/gocd/docker-gocd-agent-fedora-28)
* [gocd/docker-gocd-agent-fedora-29](https://github.com/gocd/docker-gocd-agent-fedora-29)

# Usage
*The build process uses the `Rakefile` to build different tasks. There are three tasks that
you could build: __all images__, __specific image__, and __publish__ the docker images.*

The URL for environment variable `GOCD_AGENT_DOWNLOAD_URL` is under the Zip tab from
this [`download`][0] webpage.

## 1. Building all images

```bash
GOCD_VERSION=X.Y.Z \
GOCD_AGENT_DOWNLOAD_URL=https://download.gocd.io/binaries/X.Y.Z-PPPP/generic/go-agent-X.Y.Z-PPPP.zip \
rake build_image [--trace]
```

## 2. Building a specific image
**List all targets**
```bash
GOCD_VERSION=X.Y.Z \
GOCD_AGENT_DOWNLOAD_URL=https://download.gocd.io/binaries/X.Y.Z-PPPP/generic/go-agent-X.Y.Z-PPPP.zip \
rake -T build_image
```

**Build a specific image, ubuntu 16.04, gocd version 17.3.0**
```bash
GOCD_VERSION=17.3.0 \
GOCD_AGENT_DOWNLOAD_URL=https://download.gocd.io/binaries/17.3.0-4704/generic/go-agent-17.3.0-4704.zip \
rake gocd-agent-ubuntu-16.04:build_image
```

## 3. Publishing all docker images
```bash
GOCD_VERSION=X.Y.Z GOCD_AGENT_DOWNLOAD_URL=https://download.gocd.io/binaries/X.Y.Z-PPPP/generic/go-agent-X.Y.Z-PPPP.zip
rake publish [--trace]
```
**_Note:_** *_Image will be removed from machine post push. To disable auto cleanup add env `CLEAN_IMAGES=false`_*


# License

```plain
Copyright 2018 ThoughtWorks, Inc.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```

[0]: https://www.gocd.io/download/
