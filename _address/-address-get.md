---
title: /address/:hash
# position: 1.0
type: get
description: Get an address information.

# parameters:
#   - name:
#     content:

content_markdown: |-
  Returns a specific address information from Electra blockchain.

left_code_blocks:
  - code_block: |-
      curl -X GET https://api.electraproject.org/address/EHFF1iKaqK2bY81SghZz6YxQTKgx47JjDE
    title: curl
    language: bash

right_code_blocks:
  - code_block: |2-
      {
        "data": {
          "hash": "EHFF1iKaqK2bY81SghZz6YxQTKgx47JjDE",
          "balance": 0.16776000
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
