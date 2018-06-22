---
title: /address/:hash/transactions
# position: 1.0
type: get
description: List the transactions related to this address hash.

parameters:
  - name: page
    content: |-
      0-indexed page number.<br>
      <em>Optional. Default to `"0"`.</em>
  - name: onlyConfirmed
    content: |-
      Select only the transactions with at least 10 confirmations if set to `"1"`.<br>
      <em>Optional. Default to `"0"`.</em>
  - name: onlyUnconfirmed
    content: |-
      Select only the transactions with less than 10 confirmations if set to `"1"`.<br>
      <em>Optional. Default to `"0"`.</em>
  - name: onlyUnspent
    content: |-
      Select only the unspent transactions if set to `"1"`.<br>
      <em>Optional. Default to `"0"`.</em>

content_markdown: |-
  The transactions list is limited to 10 items per page and sorted by date in descending order (from the newest to the
  oldest). This can't be customized.

left_code_blocks:
  - code_block: |-
      curl -X GET https://api.electraproject.org/address/EHFF1iKaqK2bY81SghZz6YxQTKgx47JjDE/transactions
    title: curl
    language: bash

right_code_blocks:
  - code_block: |2-
      {
        "data": {
          "address": "EHFF1iKaqK2bY81SghZz6YxQTKgx47JjDE",
          "page": 0,
          "count": 3,
          "transactions": [
            {
              "id": "704...a3d",
              "isUnspent": true,
              "confirmations": 2107,
              "fee": 0.00001000,
              "date": 1524425645,
              "from": [
                {
                  "address": "EHFF1iKaqK2bY81SghZz6YxQTKgx47JjDE",
                  "amount": 0.16777000
                }
              ]
              "to": [
                {
                  "address": "EHFF1iKaqK2bY81SghZz6YxQTKgx47JjDE",
                  "amount": 0.16776000
                }
              ]
            },
            {
              "transactionId": "0f4...b0f",
              "isUnspent": false,
              "confirmations": 2408,
              "fee": 0.00001000,
              "date": 1524425645,
              "from": [
                {
                  "address": "EHFF1iKaqK2bY81SghZz6YxQTKgx47JjDE",
                  "amount": 0.12998000
                },
                {
                  "address": "EacCKNppSXkgMfLi8U1UpMdYp5jQ32Bjqk",
                  "amount": 0.03780000
                }
              ]
              "to": [
                {
                  "address": "EHFF1iKaqK2bY81SghZz6YxQTKgx47JjDE",
                  "amount": 0.16777000
                }
              ]
            },
            {
              "transactionId": "868...905",
              "isUnspent": false,
              "confirmations": 12398,
              "fee": 0.00001000,
              "date": 1524425645,
              "from": [
                {
                  "address": "EHFF1iKaqK2bY81SghZz6YxQTKgx47JjDE",
                  "amount": 0.08999000
                }
              ]
              "to": [
                {
                  "address": "ENy1M8AbqAyvgYX7pYYd8GR8q2nF9FNSGM",
                  "amount": 0.01000000
                },
                {
                  "address": "EHFF1iKaqK2bY81SghZz6YxQTKgx47JjDE",
                  "amount": 0.07998000
                }
              ]
            }
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
