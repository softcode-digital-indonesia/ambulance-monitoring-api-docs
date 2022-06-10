## Officer

It's used by super admin or officer to manage officer data at Monitoring System.

### Contents
- [Create Officer](#1-create-officer)
- [Update Officer by Id](#2-update-officer-by-id)
- [Get Officer by Uptd](#3-get-officer-by-uptd)
- [Get Officer by Id](#4-get-officer-by-id)
- [Delete Officer by Id](#5-delete-officer-by-id)
- [Get Officer Type](#6-get-officer-type)

#### 1. Create Officer

##### Request :
- Method : POST
- Endpoint : /officer
- Authentication: Required
- Authorization: Admin
- Header :
    * Content-Type : application/json
    * Authorization : Bearer {{token}}
- Body :

```json
{
  "username": "string",
  "password": "string",
  "name": "string",
  "phone": "string",
  "type": "string"
}
```

| Parameter  | Type   | Required? | Description              |
|------------|--------|-----------|--------------------------|
| `username` | string | required  | Officer account username |
| `password` | string | required  | Officer account password |
| `name`     | string | required  | Officer name             |
| `phone`    | string | required  | Officer phone            |
| `type`     | string | required  | Officer type             |


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
| `201` | Created |

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
| `417` | Expectation Failed    |
| `500` | Internal Server Error |

#### 2. Update Officer by Id

##### Request :
- Method : PUT
- Endpoint : /officer/`officer-id`

| Parameter    | Required | Description           |
|--------------|----------|-----------------------|
| `officer-id` | required | Officer Id to updated |

- Authentication: Required
- Authorization: Admin
- Header :
    * Content-Type : application/json
    * Authorization : Bearer {{token}}
- Body :

```json
{
  "username": "string",
  "password": "string",
  "name": "string",
  "phone": "string",
  "type": "string"
}
```

| Parameter  | Type   | Required? | Description              |
|------------|--------|-----------|--------------------------|
| `username` | string | optional  | Officer account username |
| `password` | string | optional  | Officer account password |
| `name`     | string | optional  | Officer name             |
| `phone`    | string | optional  | Officer phone            |
| `type`     | string | optional  | Officer type             |


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

| Code  | Message               |
|-------|-----------------------|
| `404` | Not Found             |
| `500` | Internal Server Error |

#### 3. Get Officer by Uptd

##### Request :

- Method : GET
- Endpoint : /officer/uptd
- Authentication: Required
- Authorization: Admin
- Header :
    * Content-Type : application/json
    * Authorization : Bearer {{token}}

##### Response :

- Success Response

```json
{
  "code" : "number",
  "message" : "string",
  "payload": [
    {
      "id": "number",
      "uptd_id": "number",
      "username": "string",
      "password": "string",
      "name": "string",
      "phone": "string",
      "type": "string",
      "created_at": "long"
    }
  ]
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
| `404` | Not Found             |
| `500` | Internal Server Error |

#### 4. Get Officer by Id

##### Request :

- Method : GET
- Endpoint : /officer/`officer-id`

| Parameter    | Required | Description          |
|--------------|----------|----------------------|
| `officer-id` | required | Officer Id to search |

- Authentication: Required
- Authorization: Admin, Officer
- Header :
    * Content-Type : application/json
    * Authorization : Bearer {{token}}

##### Response :

- Success Response

```json
{
  "code" : "number",
  "message" : "string",
  "payload": [
    {
      "id": "number",
      "uptd_id": "number",
      "username": "string",
      "password": "string",
      "name": "string",
      "phone": "string",
      "type": "string",
      "created_at": "long"
    }
  ]
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
| `404` | Not Found             |
| `500` | Internal Server Error |

#### 5. Delete Officer by Id

##### Request :
- Method : DELETE
- Endpoint : /officer/`officer-id`

| Parameter    | Required | Description           |
|--------------|----------|-----------------------|
| `officer-id` | required | Officer Id to updated |

- Authentication: Required
- Authorization: Admin
- Header :
    * Content-Type : application/json
    * Authorization : Bearer {{token}}

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

| Code  | Message               |
|-------|-----------------------|
| `404` | Not Found             |
| `500` | Internal Server Error |

#### 6. Get Officer Type

##### Request :

- Method : GET
- Endpoint : /officer/type
- Authentication: Not Required
- Header :
    * Content-Type : application/json

##### Response :

- Success Response

```json
{
  "code" : "number",
  "message" : "string",
  "payload": [
    "string",
    "string",
    "string"
  ]
}
```

Possible Code and Message

| Code  | Message |
|-------|---------|
| `200` | OK      |