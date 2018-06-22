---
title: HTTP Status Codes
position: 4

parameters:
  - name:
    content:

content_markdown: |-
  We are following strict conventions regarding the HTTP Status Codes that we send in our responses' headers. So we
  strongly suggest any developer using our API to take advantage of that in order to handle them accordingly.

  Here is a memo of what status codes you can expect:

  **Successful Reponses**

  | Method | Code       | Note |
  | ------ | ---------- | - |
  | GET    | 200        | |
  | POST   | 201        | |
  | PUT    | 200 or 204 | 200 if a content is returned, 204 if not. |
  | DELETE | 204        | DELETE will never return any content. |

  **Failed Reponses**

  | Code       | Possible reasons |
  | ---------- | - |
  | 422        | Attempt to send malformed body data, missing properties or wrong properties values. |
  | 409        | Attempt to create an already existing resource or to update a busy resource. |
  | 404        | Either the route does not exist or the requested resource was not found. |
  | 403        | Your Basic Access Authentication succeeded **but** this user is not allowed to access this resource. |
  | 401        | Your Basic Access Authentication failed. |
  | 500        | Something went wrong on the server side. Please open an issue if this happens. |

  If you request a list of entities and that this list is empty, you will not receive a `404` but a `2XX` status code
  with an empty list.
  {: .warning }

left_code_blocks:
  - code_block:
    title:
    language:

right_code_blocks:
  - code_block:
    title:
    language:
---
