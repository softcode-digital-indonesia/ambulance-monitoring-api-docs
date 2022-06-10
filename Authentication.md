## Authentication

It's used by Monitoring System entities to get authorization access or detach their access.

### Contents
- [Login](#1-login)
- [Logout](#2-logout)

#### 1. Login

##### Request :
- Method : POST
- Endpoint : /authentication/login
- Authentication: Not Required
- Header :
    * Content-Type : application/json
- Body :

```json
{
    "username":"string",
    "password":"string"
}
```

| Parameter  | Type   | Required? | Description      |
|------------|--------|-----------|------------------|
| `username` | string | required  | Officer username |
| `password` | string | required  | Officer password |

##### Response :

- Success Response
```json
{
  "code" : "number",
  "message" : "string",
  "payload": "string (jwt token)"
}
```

Possible Code and Message

| Code  | Message |
|-------|---------|
| `200` | OK      |

- Failed Response
```json
{
  "code" : "number",
  "message" : "string"
}
```

Possible Code and Message

| Code  | Message               |
|-------|-----------------------|
| `401` | Password Not Match    |
| `404` | Not Found             |
| `500` | Internal Server Error |

#### 2. Logout

##### Request :
- Method : DELETE
- Endpoint : /authentication/logout
- Authentication: Required
- Header :
    * Content-Type : application/json
    * Authentication : Bearer {{token}}

##### Response :

- Success Response
```json
{
  "code" : "number",
  "message" : "string"
}
```

Possible Code and Message

| Code  | Message |
|-------|---------|
| `200` | OK      |

- Failed Response
```json
{
  "code" : "number",
  "message" : "string"
}
```

Possible Code and Message

| Code  | Message           |
|-------|-------------------|
| `401` | Session Inactive  |
| `404` | Session Not Found |
| `500` | Server Error      |