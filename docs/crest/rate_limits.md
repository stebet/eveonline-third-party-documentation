# Rate Limits

CREST utilizes two rate limiting schemes: a basic per IP rate limit and a secondary per access token rate limit. If the rate limits are overstepped, requests will fail with a 503 error code.

## Per IP Rate Limit

- **Rate limit:** 150 requests per second
- **Burst limit:** 400 requests
- **Maximum concurrent connections:** 20

This rate limit is applied per IPv4 address. All requests count against this limit. If multiple clients are making requests from the same public IPv4 address, they will be subject to a common rate limit.

Maximum concurrent connections refers to the number of separate HTTP keep-alive connections which a client may use for requests. Attempts to start more connections than the limit will result in requests sent over them failing.

## Access Token Rate Limit

- **Rate limit:** 20 requests per second
- **Burst limit:** 100 requests

This rate limit is applied per SSO access token. Unauthenticated requests (those without an Authorization header) do not count against this limit. If multiple clients are making requests using the same access token, they may or may not be subject to a common rate limit.

## Burst Limits

Burst limits allow clients to make extra requests over the rate limits. Requests made over the rate limit will still be processed immediately, but if the number of extra requests reaches the burst limit, any further requests will fail.
