---
title: /user *
position: 1
type: get
description: Get the authenticated user information.

content_markdown: |-
  Returns the authenticated user information.

left_code_blocks:
  - code_block: |-
      curl -u FIRST_PURSE_ADDRESS_HASH:BAA_PASSWORD -X GET https://api.electraproject.org/user
    title: curl
    language: bash

right_code_blocks:
  - code_block: |2-
      {
        "data": {
          "purseHash": "ENadfBRVWkm17ni9AKmmAEvhUG54qJjB8J",
          "token": "",
          "hasAutoUpdate": true,
          "isSeller": true,
          "isSynchronized": true,
          "twitterUsername": "",
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
