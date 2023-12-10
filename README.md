# Hinokami Kagura

## TypeScript

Paths option links all the packages that is hosted under each packages `dist`. This helps the TypeScript compiler find the all the local packages that is link through the yarn workspaces.

```json
{
  "$schema": "https://json.schemastore.org/tsconfig",
  "compilerOptions": {
    ...
    "baseUrl": ".",
    "paths": {
      "@hinokami-kagura/*": ["packages/*/dist"]
    }
  },
  ...
}

```

### Supported Environment

```json
{
  "$schema": "https://json.schemastore.org/tsconfig",
  "compilerOptions": {
    ...
    "module": "ESNext",
    ...
  },
  ...
}

```

In the base [tsconfig](./tsconfig.json) file, we set the property `"module": "ESNext"` which means the compiled JavaScript supports ESM and will look like the following:

```JavaScript
const greeting = (name) => `hello, ${name || "world"}`;
export default greeting;
//# sourceMappingURL=index.js.map
```

### Why not use `CommonJS`?

ESM modules works better for tree shaking, leading to faster dev time, and smaller production bundles.

To learn more, you can readd this [post](https://web.dev/articles/reduce-javascript-payloads-with-tree-shaking).
