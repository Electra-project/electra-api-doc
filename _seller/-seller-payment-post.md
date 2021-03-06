---
title: /seller/payment *
position: 5
type: post
description: Generate a new payment linked to the user seller account.

parameters:
  - name: amount
    content: |-
      Positive float number with a maximum of 8 decimals.<br>
      <em>Mandatory.</em>

content_markdown: |-
  Returns the new payment information. This will generate a unique address for each payment.

left_code_blocks:
  - code_block: |-
      curl -u FIRST_PURSE_ADDRESS_HASH:BAA_PASSWORD -d '{"amount":123.45678901}' -X POST https://api.electraproject.org/seller/payment
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
