### 🔐 Authentication

Authentication to the API is always performed using a **Bearer token**.

For details on obtaining a token, refer to the [Authentication Documentation](https://secure.dev.30preprod.com/api/secure-authorization/docs/index.html).

Present the token in the `Authorization` header of your API requests:

```http
Authorization: Bearer {TOKEN_VALUE}
