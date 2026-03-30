---
sidebar_position: 6
---

# Secure Api Requests

To maintain secure and verified communication between systems, all requests made between our API and operators must adhere to the following security requirements. The specifics below outline how requests should be validated, whether initiated by the API or the operator.

### Security Requirements for API Requests

For requests originating from our API to operators, operators should validate each incoming request by checking the following headers. Similarly, operators should add these headers to requests they initiate to our API.

### Generating the X-Client-signature Header

The x-Client-Signature ensures request authenticity by following these steps to create a signature:

1. Concatenate the following values:
   - `Timestamp` (X-Client-TS): Timestamp at the time of the request.
   - `Request URI`: URL path with ordered and encoded query parameters (without the domain).
   - `Request Body`: For POST and PUT requests, include the request body as a string. Omit this for GET and DELETE requests.

2. Hash the concatenated string: Use the SHA256 HMAC algorithm, with the operator's Client Secret as the key, to hash the concatenated string.

:::warning[Important!]

    When generating the HMAC-SHA-256 signature, the JSON string used must have parameters in the exact same order as in the request body. Changing the field order will result in a different hash.

:::

### Validation Process

Upon receiving a request, the server (operator's or ours) should validate the X-Client-Signature by:

1. Retrieving the Client Secret based on X-Client-ID.
2. Repeating the signature creation process using the headers and parameters.
3. Comparing the generated signature to the received X-Client-Signature header. A match indicates the request is verified.
