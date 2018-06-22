---
title: /seller *
position: 1
type: get
description: Get the authenticated user seller information.

content_markdown: |-
  Returns the authenticated user seller account information.

left_code_blocks:
  - code_block: |-
      curl -X GET https://api.electraproject.org/seller
    title: curl
    language: bash

right_code_blocks:
  - code_block: |2-
      {
        "data": {
          "company": "Support Ninjas Inc.",
          "addressL1": "19 Manor Station St.",
          "addressL2": "",
          "addressL3": "",
          "code": "95820",
          "city": "Sacramento",
          "area": "2018-06-22T09:37:13.204Z",
          "country": "2018-06-22T09:37:13.204Z",
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
