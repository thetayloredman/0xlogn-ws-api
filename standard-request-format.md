---
description: All requests should follow this format.
---

# Standard Request Format

## For Requests

All requests will usually follow this predefined format. Note this is almost always minified in production.

```json
{
    "lognWS": { "version": "1.0.0", "isServer": false },
    "existingAuthUser": "<a user token>",
    "request": {
      "seq": 1, // sequencing number, for traffic management
      "command": "<the command to be run>",
      "arguments": {/* any other arguments to the command */}
    }
}
```

Here's the TypeScript typedef for that:

```typescript
type LogNWSRequest = {
    lognWS: { version: string, isServer: false },
    existingAuthUser: string | null,
    request: {
        seq: number,
        command: string,
        arguments: unknown
    }
}
```

## For Responses

This is what a client should ALWAYS expect from the server.

```json
{
    "lognWS": { "version": "1.0.0", "isServer": true },
    "response": {
        "seq": 1, // same sequencing number as the request
        "data": {
            "ok": true,
            "error": null,
            "data": {}
        }
    }
}
```

And again the TypeScript definitions:

```typescript
type LogNWSRequest = {
    lognWS: { version: string, isServer: true },
    request: {
        seq: number,
        data: {
            ok: boolean,
            error: string | null, // only null if ok is true
            data: unknown
        }
    }
}
```
