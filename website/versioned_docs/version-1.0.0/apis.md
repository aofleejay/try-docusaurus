---
id: version-1.0.0-apis
title: APIs
original_id: apis
---

|                   METHOD                   | STATUS CODE |
|--------------------------------------------|-------------|
| res.formatter.ok(data, meta?)              |     200     |
| res.formatter.created(data, meta?)         |     201     |
| res.formatter.noContent(data, meta?)       |     204     |
| res.formatter.badRequest(errors)           |     400     |
| res.formatter.unauthorized(errors)         |     401     |
| res.formatter.forbidden(errors)            |     403     |
| res.formatter.notFound(errors)             |     404     |
| res.formatter.methodNotAllowed(errors)     |     405     |
| res.formatter.unprocess(errors)            |     422     |
| res.formatter.serverError(errors)          |     500     |
| res.formatter.badGateway(errors)           |     502     |
| res.formatter.serviceUnavailable(errors)   |     503     |
| res.formatter.gatewayTimeout(errors)       |     504     |
