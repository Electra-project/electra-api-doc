---
title: Authentication
position: 4

parameters:
  - name:
    content:

content_markdown: |-
  Electra API doesn't use OAuth authentication but a custom Basic Access Authentication related to the Comprehensive
  Accounts designed in the EIP-0001 in order to guarantee the anonymity of any Electra user.

  You can read the [Authentication Background](#documentation-authentication_background) to get a better understanding of
  the process.

  The **first Purse account external address hash** is the username (ID) used in across any authenticated service
  provided by the Electra Project.
  {: .info }

  What is called a "User" in this documentation can be misleading since a "User" is in fact a "HD Wallet".
  {: .warning }

  **Step 1: Get the Challenge for this user**

  ```bash
  curl -X GET https://api.electraproject.org/user/FIRST_PURSE_ADDRESS_HASH/token
  ```

  If this request returns a `HTTP/1.1 404 Not Found`, this means that you need to create a new token for this user since
  it has never been previously registered:

  ```bash
  curl -X POST https://api.electraproject.org/user/FIRST_PURSE_ADDRESS_HASH/token
  ```

  In both case, the response will be:

  ```json
  {
    "data": {
      "challenge": "CHALLENGE",
      "purseHash": "FIRST_PURSE_ADDRESS_HASH",
      "createdAt": "2018-06-19T08:17:32.313Z",
      "updatedAt": "2018-06-19T08:17:32.313Z"
    }
  }
  ```

  **Step 2: Generate a Basic Access Authentication Password**

  You know need to sign a message using the Electra daemon with the RPC command:

  ```text
  signmessage FIRST_PURSE_ADDRESS_HASH CHALLENGE
  ```

  The response will give you a string which will be our Basic Access Authentication Password: `BAA_PASSWORD`.

  **Step 3: Verify the Basic Access Authentication Password**

  The BAA Username will always be the user's `FIRST_PURSE_ADDRESS_HASH`.

  In order to verify the `BAA_PASSWORD`, we will use it to check if this user is already registered on the API:

  ```bash
  curl -u FIRST_PURSE_ADDRESS_HASH:BAA_PASSWORD -X GET https://api.electraproject.org/user/FIRST_PURSE_ADDRESS_HASH
  ```

  If this request returns a `HTTP/1.1 404 Not Found`, this means that you need to create a new user for this user since
  it has never been previously registered:

  ```bash
  curl -u FIRST_PURSE_ADDRESS_HASH:BAA_PASSWORD -X POST https://api.electraproject.org/user/FIRST_PURSE_ADDRESS_HASH
  ```

  If the library you are using to make requests doesn't have specific settings to setup the Basic Authentication
  username and password, you can encode the string `FIRST_PURSE_ADDRESS_HASH:BAA_PASSWORD` in **Base64** and send it as
  the value of the header `Authorization` prefixed with `Basic `, i.e.: `Authorization: Basic QWxhZGRpbjpPcGVuU2VzYW1l`.
  {: .info }

left_code_blocks:
  - code_block:
    title:
    language:

right_code_blocks:
  - code_block:
    title:
    language:
---
