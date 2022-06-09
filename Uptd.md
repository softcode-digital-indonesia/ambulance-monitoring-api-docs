## Uptd

It's used by super admin to manage available UPTD at Monitoring System.

### Contents
- [Create UPTD](create-uptd)

#### Create UPTD

Request : 
- Method : POST
- Endpoint : /uptd
- Authentication: Required
- Authorization: Super Admin
- Header : 
  * Content-Type : application/json
- Body : 

```json
{
    "name":"string",
    "address":"string",
    "pic_name":"string",
    "phone":"string"
}
```

| Parameter       | Type     | Required?  | Description   |
| -------------   |----------|------------|---------------|
| `name`          | string   | required   | UPTD name     |
| `address`       | string   | required   | UPTD address  |
| `pic_name`      | string   | required   | UPTD PIC name |
| `phone`         | string   | required   | UPTD phone    |

Response :
- Success Response
```json
{
  "code" : "number",
  "message" : "string"
}
```

Possible Code and Message

|  Code  |  Message  |
| ------ | --------- |
| `201`  | Created   |

- Failed Response
```json
{
  "code" : "number",
  "message" : "string"
}
```

Possible Code and Message

|  Code  |  Message               |
| ------ | ---------------------- |
| `417`  | Expectation Failed     |
| `500`  | Internal Server Error  |
