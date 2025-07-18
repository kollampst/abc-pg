# Rate limiting

To ensure the security, stability, and scalability of our platform, ABC applies rate limiting to its APIs. This mechanism helps protect our infrastructure from excessive traffic, whether accidental or malicious, while ensuring a consistent experience for all users.

By controlling the number of incoming requests, ABC can maintain high availability and performance across a wide range of applications and developers who depend on our services.

## How ABC Applies Rate Limits

To maintain optimal performance and fair usage across our platform, ABC enforces rate limits based on IP address and account ID.

Production accounts are allowed up to 200 requests per second per account ID.

Test accounts are limited to 10 requests per second per account ID.

```

{
    "message": "Rate limit exceeded! You reached the limit of 3 requests per 1 minutes"
}

```

If the rate limit is exceeded, the API will return a 429 Too Many Requests status code, indicating that further requests are being temporarily throttled.

## Handling 429 Rate Limit Responses

If you receive a 429 Too Many Requests response, it means you've exceeded the allowed request rate for your account. The response includes a header indicating how long to wait before retrying.

To recover gracefully:

Check the Retry-After header to determine the wait time.

Pause your requests accordingly before attempting again.

Consider implementing exponential backoff in your client to handle repeated 429 responses more effectively.
