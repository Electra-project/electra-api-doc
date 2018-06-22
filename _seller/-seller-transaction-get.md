---
title: /seller/transaction/:transactionId *
position: 5
type: post
description: Get a seller transaction information.

content_markdown: |-
  Returns a seller transaction information.

  The `status` can be one of:
  - **PENDING**: The payment has not been broadcast.
  - **BROADCAST**: The payment has been broadcast and is in the transactions pool.
  - **UNCONFIRMED**: The payment has at least one confirmation but less than 10 confirmations.
  - **CONFIRMED**: The payment has 10 confirmations or more.

  The `updatedAt` date can be used as confirmation date for the related transaction.

left_code_blocks:
  - code_block: |-
      curl -u FIRST_PURSE_ADDRESS_HASH:BAA_PASSWORD -X GET https://api.electraproject.org/seller/transaction/da78145f-2028-4eec-8009-5c9d9343d76d
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
          "status": "PENDING",
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
