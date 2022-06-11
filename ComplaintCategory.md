## Complaint Category

It's used to manage complaint category data at Monitoring System.

### Contents
- [Get Complaint Category Type](#1-get-complaint-category-type)
- [Create Complaint Category](#2-create-complaint-category)
- [Get All Complaint Category](#3-get-all-complaint-catgory)
- [Update Complaint Category by Id](#4-update-complaint-category-by-id)
- [Delete Complaint Category by Id](#5-delete-complaint-category-by-id)

#### 1. Get Complaint Category Type

##### Request :

- Method : GET
- Endpoint : /complaint/category/type
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

#### 2. Create Complaint Category

##### Request :
- Method : POST
- Endpoint : /complaint/category
- Authentication: Required
- Header :
    * Content-Type : application/json
    * Authorization : Bearer {{token}}
- Body :

```json
{
  "name": "string",
  "complaint_type": "string"
}
```

| Parameter        | Type   | Required? | Description             |
|------------------|--------|-----------|-------------------------|
| `name`           | string | required  | Complaint category name |
| `complaint_type` | string | required  | Complaint category type |

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

#### 3. Get All Complaint Category

##### Request :
- Method : GET
- Endpoint : /complaint/category
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
      "id": "number",
      "name": "string",
      "complaint_type": "string"
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

#### 4. Update Complaint Category by Id

##### Request :
- Method : PUT
- Endpoint : /complaint/category/`complaint-category-id`

| Parameter               | Required | Description                     |
|-------------------------|----------|---------------------------------|
| `complaint-category-id` | required | Complaint Category Id to update |

- Authentication: Required
- Header :
  * Content-Type : application/json
  * Authorization : Bearer {{token}}
- Body :

```json
{
  "name": "string",
  "complaint_type": "string"
}
```

| Parameter        | Type   | Required? | Description             |
|------------------|--------|-----------|-------------------------|
| `name`           | string | optional  | Complaint category name |
| `complaint_type` | string | optional  | Complaint category type |

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

#### 5. Delete Complaint Category by Id

##### Request :
- Method : DELETE
- Endpoint : /complaint/category/`complaint-category-id`

| Parameter               | Required | Description                     |
|-------------------------|----------|---------------------------------|
| `complaint-category-id` | required | Complaint Category Id to delete |

- Authentication: Required
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