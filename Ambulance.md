## Ambulance

It's used by UPTD admin to manage ambulance data at Monitoring System.

### Contents
- [Create Ambulance](#1-create-ambulance)
- [Update Ambulance by Id](#2-update-ambulance-by-id)
- [Get Ambulance by Id](#3-get-ambulance-by-id)
- [Get Ambulance by Uptd](#4-get-ambulance-by-uptd)
- [Get Ambulance Report by Uptd](#5-get-ambulance-report-by-uptd)
- [Delete Ambulance by Id](#6-delete-ambulance-by-id)
- [Get Ambulance Status](#7-get-ambulance-status)

#### 1. Create Ambulance

##### Request :
- Method : POST
- Endpoint : /ambulance
- Authentication: Required
- Authorization: Admin
- Header :
    * Content-Type : application/json
    * Authorization : Bearer {{token}}
- Body :

```json
{
  "ambulance_type_id":"number",
  "name":"string",
  "license_plate":"string"
}
```

| Parameter           | Type   | Required? | Description                |
|---------------------|--------|-----------|----------------------------|
| `ambulance_type_id` | number | required  | Selected ambulance type id |
| `name`              | string | required  | Ambulance name             |
| `license_plate`     | string | required  | Ambulance license plate    |

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

#### 2. Update Ambulance by Id

##### Request :
- Method : PUT
- Endpoint : /ambulance/`ambulance-id`

| Parameter      | Required | Description            |
|----------------|----------|------------------------|
| `ambulance-id` | required | Ambulance Id to update |

- Authentication: Required
- Authorization: Admin
- Header :
  * Content-Type : application/json
  * Authorization : Bearer {{token}}
- Body :

```json
{
  "ambulance_type_id":"number",
  "name":"string",
  "license_plate":"string",
  "status": "string"
}
```

| Parameter           | Type   | Required? | Description                                          |
|---------------------|--------|-----------|------------------------------------------------------|
| `ambulance_type_id` | number | optional  | Selected ambulance type id                           |
| `name`              | string | optional  | Ambulance name                                       |
| `license_plate`     | string | optional  | Ambulance license plate                              |
| `status`            | string | optional  | Ambulance status (accepted only [On Duty, Off Duty]) |


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

#### 3. Get Ambulance by Id

##### Request :
- Method : GET
- Endpoint : /ambulance/`ambulance-id`

| Parameter      | Required | Description            |
|----------------|----------|------------------------|
| `ambulance-id` | required | Ambulance Id to search |

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
  "payload" : {
    "id": "number",
    "uptd_id": "number",
    "name": "string",
    "license_plate": "string",
    "status": "string",
    "ambulance_type": {
      "id": "number",
      "name": "string"
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
| `404` | Not Found             |
| `500` | Internal Server Error |

#### 4. Get Ambulance by Uptd

##### Request :
- Method : GET
- Endpoint : /ambulance/uptd
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
  "payload" : [
    {
      "id": "number",
      "uptd_id": "number",
      "name": "string",
      "license_plate": "string",
      "status": "string",
      "ambulance_type": {
        "id": "number",
        "name": "string"
      }
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

#### 5. Get Ambulance Report by Uptd

Not Yet Implemented

#### 6. Delete Ambulance by Id

##### Request :
- Method : DELETE
- Endpoint : /ambulance/`ambulance-id`

| Parameter      | Required | Description            |
|----------------|----------|------------------------|
| `ambulance-id` | required | Ambulance Id to search |

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

#### 7. Get Ambulance Status

##### Request :

- Method : GET
- Endpoint : /ambulance/status
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
    "string"
  ]
}
```

Possible Code and Message

| Code  | Message |
|-------|---------|
| `200` | OK      |