---
title: /seller/transaction *
position: 4
type: get
description: Generate a new transaction linked to the user seller account.

content_markdown: |-
  Returns the new transaction information.

left_code_blocks:
  - code_block: |-
      curl -u FIRST_PURSE_ADDRESS_HASH:BAA_PASSWORD -d '{"amount":123.45678901}' -X POST https://api.electraproject.org/seller/transaction
    title: curl
    language: bash

right_code_blocks:
  - code_block: |2-
      {
        "data": {
          "id": "da78145f-2028-4eec-8009-5c9d9343d76d",
          "address": "ELPXhJueXfJKA7z3SNBuukxcQSeW2rCbUL",
          "amount": 123.45678901,
          "fee": 0.61728394,
          "feeRatio": 0.005,
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
