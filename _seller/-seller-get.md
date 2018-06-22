---
title: /seller *
position: 1
type: get
description: Get the authenticated seller information.

content_markdown: |-
  Returns the authenticated seller information.

left_code_blocks:
  - code_block: |-
      curl -X GET https://api.electraproject.org/seller
    title: curl
    language: bash

right_code_blocks:
  - code_block: |2-
      {
        "data": {
          "lastSellerAccountAddressIndex": 31,
          "createdAt": "2018-06-22T09:37:13.204Z",
          "updatedAt": "2018-06-22T09:37:13.204Z"
        }
      }
    title: Response
    language: json

  - code_block: |2-
      {
        "message": "Error message."
      }
    title: Error
    language: json
---
