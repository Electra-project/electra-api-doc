---
title: /seller/address *
position: 3
type: get
description: Get a new Seller address index for the authenticated user.

content_markdown: |-
  Returns a new, unused, CA Seller account address index for the authenticated user.

left_code_blocks:
  - code_block: |-
      curl -X GET https://api.electraproject.org/seller/address
    title: curl
    language: bash

right_code_blocks:
  - code_block: |2-
      {
        "data": {
          "sellerAccountAddressIndex": 32
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
