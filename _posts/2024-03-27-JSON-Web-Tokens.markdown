---
layout: post
title:  "Understanding JSON Web Tokens"
date:   2024-03-27 00:00:00 -0400
categories: class_experience
---

![Json Web Tokens](https://supertokens.com/static/b0172cabbcd583dd4ed222bdb83fc51a/9af93/jwt-structure.png)

What is JWT?
---

JWT is an open standard (RFC 7519) that defines a compact and self-contained way for securely transmitting information between parties as a JSON object. It consists of three parts: a header, a payload, and a signature. These parts are separated by dots (.) and look like this:

`xxxxx.yyyyy.zzzzz`

Parts of JWT:
---

1. *Header:* Contains metadata about the type of token and the signing algorithm being used.

2. *Payload:* Contains the claims. Claims are statements about an entity (typically, the user) and additional data. Claims can be categorized into three types: reserved, public, and private claims.

3. *Signature:* Used to verify that the sender of the JWT is who it says it is and to ensure that the message wasn't changed along the way. The signature is created by encoding the header and payload, combining them with a secret, and then applying a hashing algorithm.

How JWT Works:
---

1. *Authentication:* When a user logs in, the server generates a JWT and sends it back to the client. The client stores the token locally (usually in local storage or a cookie) and sends it along with subsequent requests.

2. *Authorization:* The server verifies the JWT sent by the client. If the token is valid and contains the necessary information (e.g., user ID, role), the server grants access to protected resources.

3. *Token Expiration:* JWTs can have an expiration time, after which they are no longer valid. This helps mitigate the risk of token theft and unauthorized access.

Benefits of JWT:
---

1. *Stateless:* JWTs are self-contained, meaning all the information needed is included in the token itself. This eliminates the need to store session data on the server, making JWTs stateless and scalable.

2. *Security:* JWTs are digitally signed, ensuring that the token hasn't been tampered with. They can also be encrypted for additional security.

3. *Flexibility:* JWTs can be used for various purposes, including authentication, authorization, and information exchange.