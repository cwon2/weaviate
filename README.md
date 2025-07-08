<h1>Weaviate <img alt='Weaviate logo' src='https://weaviate.io/img/site/weaviate-logo-light.png' width='148' align='right' /></h1>

[![Go Reference](https://pkg.go.dev/badge/github.com/weaviate/weaviate.svg)](https://pkg.go.dev/github.com/weaviate/weaviate)
[![Build Status](https://github.com/weaviate/weaviate/actions/workflows/.github/workflows/pull_requests.yaml/badge.svg?branch=main)](https://github.com/weaviate/weaviate/actions/workflows/.github/workflows/pull_requests.yaml)
[![Go Report Card](https://goreportcard.com/badge/github.com/weaviate/weaviate)](https://goreportcard.com/report/github.com/weaviate/weaviate)
[![Coverage Status](https://codecov.io/gh/weaviate/weaviate/branch/main/graph/badge.svg)](https://codecov.io/gh/weaviate/weaviate)
[![Slack](https://img.shields.io/badge/slack--channel-blue?logo=slack)](https://weaviate.io/slack)
[![GitHub Tutorials](https://img.shields.io/badge/Weaviate_Tutorials-green)](https://github.com/weaviate-tutorials/)

## Overview

Weaviate is a cloud-native, **open source vector database** that is robust, fast, and scalable.

To get started quickly, have a look at one of these pages:

- [Quickstart tutorial](https://weaviate.io/developers/weaviate/quickstart) To see Weaviate in action
- [Contributor guide](https://weaviate.io/developers/contributor-guide) To contribute to this project

For more details, read through the summary on this page or see the system [documentation](https://weaviate.io/developers/weaviate/).

---

## 커스텀 변경 사항
- 내부 네트워크 용도로 `192.102.0.0/16`, `192.103.0.0/16` IP 대역을 사용할 수 있도록 허용

---

## 사전 요구 사항
- Docker
- Git
- Go >= 1.21 (로컬 개발 시)

---

## Docker 이미지 빌드
```
docker build \
  --platform linux/amd64 \
  --build-arg TARGETARCH=amd64 \
  --build-arg GIT_BRANCH=$(git rev-parse --abbrev-ref HEAD) \
  --build-arg GIT_REVISION=$(git rev-parse HEAD) \
  --build-arg BUILD_USER=$(whoami) \
  --build-arg BUILD_DATE=$(date -u +"%Y-%m-%dT%H:%M:%SZ") \
  --build-arg EXTRA_BUILD_ARGS="-tags static" \
  -t mncregistry:30500/weaviate:v1.30.9-bok \
  .
```
