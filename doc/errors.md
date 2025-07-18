# ❗ Error Handling in ABC API

The **ABC API** follows conventional HTTP response codes to indicate the outcome of API requests.

- ✅ `2xx`: Success  
- ⚠️ `4xx`: Client Error (e.g., missing parameters, invalid input)  
- ❌ `5xx`: Server Error (unexpected failures on the server)

---

## 🔄 Error Response Examples

### ✅ 200 OK with Partial Failure (Bulk APIs)

For **bulk APIs**, a `200 OK` response may include both **successful** and **failed** items. Failed items will have an `errors` array at the item level:

```json
{
  "responses": [
    {
      "referenceId": "...",
      "status": "SUCCESS"
    },
    {
      "referenceId": "...",
      "status": "ERROR",
      "errors": [
        {
          "code": "REQUEST_INVALID",
          "message": "tokenId must not be null"
        }
      ]
    }
  ]
}

```
### ⚠️ 400 Bad Request (Empty List)
This is returned when the request is syntactically valid but semantically invalid (e.g., missing required data):
```
{
  "statusCode": "BAD_REQUEST",
  "errors": [
    {
      "message": "Request list cannot be empty"
    }
  ]
}

```
### ❌ 500 Internal Server Error
This indicates a problem with the server, usually unexpected and rare:
```
{
  "statusCode": "INTERNAL_SERVER_ERROR",
  "errors": [
    {
      "code": "internal.server",
      "message": "Internal server error"
    }
  ]
}
