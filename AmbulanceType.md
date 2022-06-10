## Ambulance Type

It's used to manage available ambulance type data at Monitoring System.

### Contents
- [Create Ambulance Type](#1-create-ambulance-type)
- [Update Ambulance Type by Id](#2-update-ambulance-type-by-id)
- [Get All Ambulance Type](#3-get-all-ambulance-type)
- [Delete Ambulance Type by Id](#4-delete-ambulance-type-by-id)

#### 1. Create Ambulance Type

##### Request :
- Method : POST
- Endpoint : /ambulance/type
- Authentication: Required
- Authorization: Super Admin
- Header :
    * Content-Type : application/json
    * Authorization : Bearer {{token}}
- Body :

```json
{
    "name":"string"
}
```

| Parameter  | Type   | Required? | Description         |
|------------|--------|-----------|---------------------|
| `name`     | string | required  | Ambulance Type name |

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

#### 2. Update Ambulance Type by Id

##### Request :
- Method : PUT
- Endpoint : /ambulance/type/`ambulance-type-id`

| Parameter           | Required | Description                 |
|---------------------|----------|-----------------------------|
| `ambulance-type-id` | required | Ambulance Type Id to update |

- Authentication: Required
- Authorization: Super Admin
- Header :
  * Content-Type : application/json
  * Authorization : Bearer {{token}}
- Body :

```json
{
    "name":"string"
}
```

| Parameter  | Type   | Required? | Description         |
|------------|--------|-----------|---------------------|
| `name`     | string | required  | Ambulance Type name |

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

#### 3. Get All Ambulance Type

##### Request :
- Method : GET
- Endpoint : /ambulance/type
- Authentication: Not Required
- Header :
  * Content-Type : application/json

##### Response :

- Success Response
```json
{
  "code" : "number",
  "message" : "string",
  "payload" : [
    {
      "id" : "number",
      "name" : "string"
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
| `500` | Internal Server Error |

#### 4. Delete Ambulance Type by Id

##### Request :
- Method : DELETE
- Endpoint : /ambulance/type/`ambulance-type-id`

| Parameter           | Required | Description                 |
|---------------------|----------|-----------------------------|
| `ambulance-type-id` | required | Ambulance Type Id to delete |

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
| `404` | Not Found             |
| `500` | Internal Server Error |