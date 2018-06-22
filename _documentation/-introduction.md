---
title: Introduction
position: 1

parameters:
  - name:
    content:

content_markdown: |-
  Welcome to our Electra RESTful API.

  This documentation is intended to help developers interested in interacting with the Electra blockchain.

  _This is a work in progress. The first working version will be publicly announced._
  {: .warning }

  ## Endpoint

  `https://api.electraproject.org`
  {: .info }

  ## Version

  A specific version can be requested by using a `X-Version` header in the request header. The resolved version will be
  returned in the response's header :

  ```bash
  curl https://api.electraproject.org/address/EHFF1iKaqK2bY81SghZz6YxQTKgx47JjDE -I \
   -H "Accept: application/vnd.github.full+json"
  HTTP/1.1 200 OK
  X-Version: v1.0
  ```

  If you don't specify the `X-Version`, the latest stable version available will be used.

left_code_blocks:
  - code_block:
    title:
    language:

right_code_blocks:
  - code_block:
    title:
    language:
---
