## Linting React app

### Deviations from global Readme

- When running ESLint configuration wizard, indicate React is needed. `eslint-plugin-react` should be automatically added to devDependecies.
- Also, rather tick the `node` environment, without it `.eslintrc.js` will indicate warnings.
- There will be a warning about non-specified React version. You can do that in `.eslintrc.js` like this:

```javascript
{
  // ...
  "settings": {
    "react": {
      "version": "detect",
    }
  },
  // ...
}
```

- Starting from React 17, it is not required to `import React` any more in components - just add `plugin:react/jsx-runtime` into ESLint `.eslintrc.js` in it's `extends` section, if that is a case.
