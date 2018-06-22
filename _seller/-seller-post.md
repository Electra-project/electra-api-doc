---
title: /seller *
position: 2
type: post
description: Register the authenticated user as a seller.

content_markdown: |-
  Creates a new API entry as a seller for the authenticated user. This will also turn the related user entry `isSeller`
  property to `true`.

  To cipher the CA Seller account private key, you need to:
  1. Get use the `token` provided by the `GET /user` route response body.
  2. Hash this token using **SHA-3-256** to generate a `key`.
  3. Cipher the CA Seller Account (`m/$44'/0'/3`) private key hexaecimal string with this `key` using **AES-256-ECB**.

left_code_blocks:
  - code_block: |-
      curl -d '{"sellerAccountPrivateKeyX": "CIPHERED_SELLER_ACCOUNT_PRIVATE_KEY"}' -X POST https://api.electraproject.org/seller
    title: curl
    language: bash

right_code_blocks:
  - code_block: |2-
      {
        "message": "Seller created."
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
