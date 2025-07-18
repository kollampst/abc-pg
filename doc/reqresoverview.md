### Request/Response Overview

#### Schema

All data is sent and received as **JSON**. Blank fields are omitted from the response. All timestamps return in **ISO 8601 format**:  `YYYY-MM-DDTHH:MM:SSZ`

---

#### HTTP Verbs

| Verb   | Description |
|--------|-------------|
| POST | Used for creating resources and various relationships between resources. |

---

#### Request Headers

| Header | Description |
|----------|-----------------|
| `Authorization: Bearer dbcfb1ab-9096-44b3-8583-a20b4e103641` | Bearer token used to authenticate and authorize the request |
| `Content-Type: application/json;charset=UTF-8`  | Should always be JSON. Used to specify the content type of the request body |
| `Accept: application/json;charset=UTF-8`  | Should always be JSON. Can also be used to request a specific version of the response schema |
| `Accept-Language: en-US` | Language used to generate application constants like error messages. Defaults to `en-US`. |

---

#### Response Headers

| Header | Description |
|----------|---------------|
| `Warning` | Will display API warnings, including deprecation notices. |

---

#### Standard Request Responses

| HTTP Code | Description |
|---------------|---------------|
| 200 | Successfully processed the request. |
| 400 | Invalid data types or broken business rules (majority of validation errors). |
| 401 | Attempt to access a resource without proper credentials. |
| 403 | Attempt to access a resource with credentials that lack permission. |
| 404 | Attempt to access a resource that does not exist. |
| 500 | Any uncaught server-side exception. Should not happen under normal flows. |
| 503 | Service is either down for maintenance or an internal dependency is down. |

---

#### Typical POST Request Responses

| HTTP Code | Description |
|---------------|---------------|
| 200  | Successfully processed the request. For bulk APIs, `200` is returned for both full and partial success.  |
| 400  | Invalid data types or broken business rules (majority of validation errors). |
| 401  | Attempt to access a resource without proper credentials. |
| 403  | Attempt to access a resource with credentials that lack permission. |
| 404  | Attempt to access a resource that does not exist. |
| 500  | Any uncaught server-side exception. Should not happen under normal flows. |
| 503  | Service is either down for maintenance or an internal dependency is down. |
