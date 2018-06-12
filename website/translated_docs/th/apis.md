---
id: apis
title: APIs
---
| METHOD                    | CODE | PARAMS                         |
| ------------------------- | ---- | ------------------------------ |
| res.ok()                  | 200  | res.ok(data)                   |
| res.created()             | 201  | res.created(data)              |
| res.noContent()           | 204  | -                              |
| res.badRequest()          | 400  | res.badRequest(error)          |
| res.unauthorized()        | 401  | res.unauthorized(error)        |
| res.forbidden()           | 403  | res.forbidden(error)           |
| res.notFound()            | 404  | res.notFound(error)            |
| res.methodNotAllowed()    | 405  | res.methodNotAllowed(error)    |
| res.unprocessableEntity() | 422  | res.unprocessableEntity(error) |
| res.internalServerError() | 500  | res.internalServerError(error) |
| res.badGateway()          | 502  | res.badGateway(error)          |
| res.serviceUnavailable()  | 503  | res.serviceUnavailable(error)  |
| res.gatewayTimeout()      | 504  | res.gatewayTimeout(error)      |