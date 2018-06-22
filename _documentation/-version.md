---
title: Version
position: 3

parameters:
  - name:
    content:

content_markdown: |-
  A specific version can be requested by using a `X-Version` header in the request header. The resolved version will be
  returned in the response's header.

  If you don't specify the `X-Version`, the latest stable version available will be used.

left_code_blocks:
  - code_block: |-
      curl https://api.electraproject.org/address/EHFF1iKaqK2bY81SghZz6YxQTKgx47JjDE -I -H "X-Version: 1.0"
      HTTP/1.1 200 OK
      X-Version: v1.0
    title: curl
    language: bash

right_code_blocks:
  - code_block:
    title:
    language:
---
