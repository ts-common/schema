# JSON-Schema

JSON-Schema API

## Notes

### additionalProperties

https://github.com/OAI/OpenAPI-Specification/pull/1548

- JSON-Schema. `additionalProperties` defaults to `true`.
- OpenAPI 2.0. `additionalProperties` defaults to `false`.
- OpenAPI 3.0.2. _"Consistent with JSON Schema, `additionalProperties` defaults to `true`."_
    https://github.com/OAI/OpenAPI-Specification/blob/v3.0.2-dev/versions/3.0.2.md

A simplified version of OpenAPI can introduce a global configuration field `additionalProperties`.
A strict version of OpenAPI should require the `additionalProperties` property if type is `object`.

### Default values

if `Schema` defines a default value then a validation step may produce a value of type which has no `undefined` values. For example

```ts
interface A {
    a?: string
}
```

transforms into
```ts
interface A {
    a: string
}
```