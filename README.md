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
