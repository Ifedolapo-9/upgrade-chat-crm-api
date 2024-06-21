

# Rate Limits

To prevent abuse and ensure fair usage, the Upgrade Chat CRM API enforces rate limits on requests. The rate limits are as follows:

- **50 requests per minute per API key**
- **10,000 requests per day per API key**

## Handling Rate Limits

If you exceed the rate limit, the API will respond with an HTTP status code of `429 Too Many Requests` and include relevant headers indicating when you can retry your requests. Here's an example response:

```
HTTP/1.1 429 Too Many Requests
X-RateLimit-Limit: 50
X-RateLimit-Remaining: 0
X-RateLimit-Reset: 1624617600
```

In this example, the `X-RateLimit-Reset` header indicates the Unix timestamp when the rate limit window resets, allowing you to make new requests.

To handle rate limiting, you should implement a retry mechanism in your application. When you receive a `429` status code, wait until the rate limit window resets before retrying your requests. You can also consider spacing out your requests more evenly to avoid hitting the rate limit.