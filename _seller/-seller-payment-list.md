---
title: /seller/payments *
position: 6
type: get
description: List the payments related to the authenticated user seller account.

parameters:
  - name: page
    content: |-
      0-indexed page number.<br>
      <em>Optional. Default to `"0"`.</em>

content_markdown: |-
  The payments list is limited to 10 items per page and sorted by date in descending order (from the newest to the

  Please check the [`/seller/payment/:sellerAddressHash *` route](#seller-seller-payment-get) to see the list of the
  possible statuses.

left_code_blocks:
  - code_block: |-
      curl -u FIRST_PURSE_ADDRESS_HASH:BAA_PASSWORD -X GET https://api.electraproject.org/seller/payment/ELPXhJueXfJKA7z3SNBuukxcQSeW2rCbUL
    title: curl
    language: bash

right_code_blocks:
  - code_block: |2-
      {
        "data": [
          {
            "address": "ER9GpoJUrtuNG6A6jWCgwJ7ZkyE667Nb37",
            "amount": 4876.8732,
            "fee": 24.384366,
            "feeRatio": 0.005,
            "status": "PENDING",
            "confirmedAt": "2018-06-22T09:37:13.204Z",
            "createdAt": "2018-06-22T09:37:13.204Z",
            "updatedAt": "2018-06-22T09:37:13.204Z"
          },
          {
            "index": 2,
            "address": "ELPXhJueXfJKA7z3SNBuukxcQSeW2rCbUL",
            "amount": 123.45678901,
            "fee": 0.61728394,
            "feeRatio": 0.005,
            "status": "CONFIRMED",
            "confirmedAt": "2018-06-21T09:37:13.204Z",
            "createdAt": "2018-06-21T09:37:13.204Z",
            "updatedAt": "2018-06-21T09:37:13.204Z"
          }
        ]
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
