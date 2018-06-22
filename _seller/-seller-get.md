---
title: /seller *
position: 1
type: get
description: Get the authenticated user seller information.

content_markdown: |-
  Returns the authenticated user seller account information.

left_code_blocks:
  - code_block: |-
      curl -u FIRST_PURSE_ADDRESS_HASH:BAA_PASSWORD -X GET https://api.electraproject.org/seller
    title: curl
    language: bash

right_code_blocks:
  - code_block: |2-
      {
        "data": {
          "sellerHash": "ELPXhJueXfJKA7z3SNBuukxcQSeW2rCbUL",
          "feeRate": 0.005,
          "company": "Support Ninjas Inc.",
          "addressL1": "19 Manor Station St.",
          "addressL2": "",
          "addressL3": "",
          "code": "95820",
          "city": "Sacramento",
          "area": "2018-06-22T09:37:13.204Z",
          "country": "2018-06-22T09:37:13.204Z",
          "email": "contact@example.com",
          "website": "https://example.com",
          "isActivated": true,
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
