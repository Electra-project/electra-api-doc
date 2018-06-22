---
title: /transaction/:id
# position: 1.0
type: get
description: Get a transaction.

content_markdown: |-
  Get the detailed information about the current transaction id.

left_code_blocks:
  - code_block: |-
      curl -X GET https://api.electraproject.org/transaction/86837426211c609ca3108e0e1d98bf5f6646f96bebc6189fde97511a497d1905
    title: curl
    language: bash

right_code_blocks:
  - code_block: |2-
      {
        "data": {
          "id": "868...905",
          "isUnspent": true,
          "confirmations": 2107,
          "fee": 0.00001000,
          "date": 1524425645,
          "from": [
            {
              "address": "EHFF1iKaqK2bY81SghZz6YxQTKgx47JjDE",
              "transactionId": "f8c...d48",
              "index": 1,
              "amount": 0.08999000
            }
          ],
          "to": [
            {
              "address": "ENy1M8AbqAyvgYX7pYYd8GR8q2nF9FNSGM",
              "transactionId": "868...905",
              "index": 0,
              "amount": 0.01000000
            },
            {
              "address": "EHFF1iKaqK2bY81SghZz6YxQTKgx47JjDE",
              "transactionId": "868...905",
              "index": 1,
              "amount": 0.07998000
            }
          ],
          "fromAddresses": [
            "EHFF1iKaqK2bY81SghZz6YxQTKgx47JjDE"
          ],
          "toAddresses": [
            "ENy1M8AbqAyvgYX7pYYd8GR8q2nF9FNSGM",
            "EHFF1iKaqK2bY81SghZz6YxQTKgx47JjDE"
          ]
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
