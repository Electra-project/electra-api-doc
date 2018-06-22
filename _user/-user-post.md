---
title: /user *
position: 2
type: post
description: Register the autheticated user.

content_markdown: |-
  Creates a new API entry for the authenticated user.

left_code_blocks:
  - code_block: |-
      curl -X POST https://api.electraproject.org/user
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
