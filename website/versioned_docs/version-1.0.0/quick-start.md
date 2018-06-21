---
id: version-1.0.0-quick-start
title: Quick Start
original_id: quick-start
---

## Starter Code ##
Example usage
```js
const app = require('express')()
const responseEnhancer = require('express-response-formatter')

// Add formatter functions to "res" object via "responseEnhancer()"
app.use(responseEnhancer())

app.get('/success', (req, res) => {
  const users = [
    { name: 'Dana Kennedy' },
    { name: 'Warren Young' },
  ]

  // It's enhance "res" with "formatter" which contain formatter functions
  res.formatter.ok(users)
})

app.listen(3000, () => console.log('Start at http://localhost:3000'))
```
Result
```json
HTTP/1.1 200 Ok
{
  "data": [
    {
      "name": "Dana Kennedy"
    },
    {
      "name": "Warren Young"
    }
  ]
}
```

## More usages ##
### 200 OK with "meta field" ###
```js
app.get('/success-with-meta', (req, res) => {
  const users = [
    { name: 'Dana Kennedy' },
    { name: 'Warren Young' },
  ]

  const meta = {
    total: 2,
    limit: 10,
    offset: 0,
  }

  res.formatter.ok(users, meta)
})
```
```json
HTTP/1.1 200 Ok
{
  "meta": {
    "total": 2,
    "limit": 10,
    "offset": 0,
  },
  "data": [
    {
      "name": "Dana Kennedy"
    },
    {
      "name": "Warren Young"
    }
  ]
}
```
### 400 Bad Request with "multiple errors" ###
```js
app.get('/bad-request', (req, res) => {
  const errors = [
    { detail: 'Field id is required.' },
    { detail: 'Field foo is required.' },
  ]

  res.formatter.badRequest(errors)
})
```
```json
HTTP/1.1 400 Bad Request
{
  "errors": [
    {
      "detail": "Field id is required."
    },
    {
      "detail": "Field foo is required."
    }
  ]
}
```
