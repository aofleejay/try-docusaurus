---
id: quick-start
title: เริ่มแบบรวดเร็ว
---
## โค้ดเริ่มต้น

ใช้เป็น express middleware

```js
import express from 'express'
import responseEnhancer from 'expressjs-response'

const app = express()

// use in express middleware
app.use(responseEnhancer({
  withStatusCode: true, // Include status code in response body.
  withStatusMessage: true, // Include status message in response body.
}))

// example usage
app.get('/success', (req, res) => res.ok({ name: 'John Doe' }))
app.get('/badrequest', (req, res) => res.badRequest('Invalid parameter.'))
app.get('/badgateway', (req, res) => res.badGateway())

app.listen(3000, () => console.log('Start at http://localhost:3000'))
```

## ตัวอย่างการใช้งานและผลลัพธ์

### 200 OK

```js
res.ok({ name: 'John Doe' })
```

```json
HTTP/1.1 200 Ok
{
    "status": "success",
    "data": {
        "name": "John Doe"
    }
}
```

### 400 Bad Request

```js
res.badRequest()
```

```json
HTTP/1.1 400 Bad Request
{
    "status": "fail",
    "error": {
        "code": "400",
        "message": "Bad Request"
    }
}
```

### 400 Bad Request แบบส่ง Parameter

```js
res.badRequest('Invalid parameter.')
```

```json
HTTP/1.1 400 Bad Request
{
    "status": "fail",
    "error": {
        "code": "400",
        "message": "Bad Request",
        "detail": "Invalid parameter."
    }
}
```

### 502 Bad Gateway

```js
res.badGateway()
```

```json
HTTP/1.1 502 Bad Gateway
{
    "status": "error",
    "error": {
        "code": "502",
        "message": "Bad Gateway"
    }
}
```