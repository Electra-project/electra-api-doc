---
title: /user/:purseHash/token
position: 4
type: get
description: Get the BAA token for this user (= HD wallet).

# parameters:
#   - name:
#     content:

content_markdown: |-
  Returns a specific address information from Electra blockchain.

left_code_blocks:
  - code_block: |-
      curl -X GET https://api.electraproject.org/user/ENadfBRVWkm17ni9AKmmAEvhUG54qJjB8J/token
    title: curl
    language: bash

right_code_blocks:
  - code_block: |2-
      {
        "data": {
          "challenge": "wine pony velvet ancient skull holiday popular spoon tobacco gravity weird universe file chat picnic joke plate law measure code swim silver teach area","purseHash":"ENadfBRVWkm17ni9AKmmAEvhUG54qJjB8J","createdAt":"2018-06-22T09:37:13.204Z","updatedAt":"2018-06-22T09:37:13.204Z"
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
