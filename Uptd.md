## Uptd

It's used by super admin to manage available UPTD at Monitoring System.

### Contents
- [Create UPTD](#1-create-uptd)
- [Update UPTD](#2-update-uptd)
- [Get All UPTD](#3-get-all-uptd)
- [Get UPTD by Id](#4-get-uptd-by-id)
- [Delete UPTD by Id](#5-delete-uptd-by-id)


#### 1. Create UPTD

##### Request : 
- Method : POST
- Endpoint : /uptd
- Authentication: Required
- Authorization: Super Admin
- Header : 
  * Content-Type : application/json
  * Authorization : Bearer {{token}}
- Body : 

```json
{
    "name":"string",
    "address":"string",
    "pic_name":"string",
    "phone":"string"
}
```

| Parameter  | Type   | Required? | Description   |
|------------|--------|-----------|---------------|
| `name`     | string | required  | UPTD name     |
| `address`  | string | required  | UPTD address  |
| `pic_name` | string | required  | UPTD PIC name |
| `phone`    | string | required  | UPTD phone    |

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


#### 2. Update UPTD

##### Request : 
- Method : PUT
- Endpoint : /uptd/`uptd-id`

| Parameter | Required | Description        |
|-----------|----------|--------------------|
| `uptd-id` | required | UPTD Id to updated |

- Authentication: Required
- Authorization: Super Admin
- Header : 
  * Content-Type : application/json
  * Authorization : Bearer {{token}}
- Body : 

```json
{
    "name":"string",
    "address":"string",
    "pic_name":"string",
    "phone":"string"
}
```

| Parameter  | Type   | Required? | Description   |
|------------|--------|-----------|---------------|
| `name`     | string | optional  | UPTD name     |
| `address`  | string | optional  | UPTD address  |
| `pic_name` | string | optional  | UPTD PIC name |
| `phone`    | string | optional  | UPTD phone    |

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
| `417` | Expectation Failed    |
| `500` | Internal Server Error |


#### 3. Get All UPTD

##### Request :
- Method : GET
- Endpoint : /uptd
- Authentication: Required
- Authorization: Super Admin
- Header :
  * Content-Type : application/json
  * Authorization : Bearer {{token}}
  
##### Response :

- Success Response
```json
{
  "code" : "number",
  "message" : "string",
  "payload" : [
    {
      "id" : "number",
      "name" : "string",
      "address" : "string",
      "pic_name" : "string",
      "phone" : "string"
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
| `417` | Expectation Failed    |
| `500` | Internal Server Error |


#### 4. Get UPTD by Id

##### Request :
- Method : GET
- Endpoint : /uptd/`uptd-id`

| Parameter | Required | Description       |
|-----------|----------|-------------------|
| `uptd-id` | required | UPTD Id to search |

- Authentication: Required
- Authorization: Super Admin
- Header :
  * Content-Type : application/json
  * Authorization : Bearer {{token}}

##### Response :

- Success Response
```json
{
  "code" : "number",
  "message" : "string",
  "payload" : {
    "id": "number",
    "name": "string",
    "address": "string",
    "pic_name": "string",
    "phone": "string",
    "generated_officer": {
      "id": "number",
      "uptd_id": "number",
      "username": "string",
      "password": "string",
      "name": "string",
      "type": "string",
      "created_at": "long"
    }
  }
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
| `400` | Not Found             |
| `500` | Internal Server Error |


#### 5. Delete UPTD by Id

##### Request :
- Method : DELETE
- Endpoint : /uptd/`uptd-id`

| Parameter | Required | Description       |
|-----------|----------|-------------------|
| `uptd-id` | required | UPTD Id to delete |

- Authentication: Required
- Authorization: Super Admin
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
| `400` | Not Found             |
| `500` | Internal Server Error |