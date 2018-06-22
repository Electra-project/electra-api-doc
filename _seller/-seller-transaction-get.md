---
title: /seller/transaction/:sellerAddressHash *
position: 5
type: post
description: Get a seller transaction information.

content_markdown: |-
  Returns a seller transaction information.

  The `status` can be one of:
  - **PENDING**: No transaction to this seller address has not been broadcast.
  - **BROADCAST**: The transaction(s) to this seller address have been broadcast and are in the transactions pool.
  - **UNCONFIRMED**: All of the transaction(s) to this seller address have at least one confirmation and at least one of
  them has less than 10 confirmations.
  - **CONFIRMED**:  All of the transaction(s) to this seller address have at least 10 confirmations.
  - **PARTIAL**: One or multiple transactions have been broadcast and sent to this seller address but the balance
  doesn't match the required amount.

  The `updatedAt` date can be used as confirmation date for the related transaction.

left_code_blocks:
  - code_block: |-
      curl -u FIRST_PURSE_ADDRESS_HASH:BAA_PASSWORD -X GET https://api.electraproject.org/seller/transaction/ELPXhJueXfJKA7z3SNBuukxcQSeW2rCbUL
    title: curl
    language: bash

right_code_blocks:
  - code_block: |2-
      {
        "data": {
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
