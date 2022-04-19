## Linting React app with TypeScript

Describing a Create React App / TypeScript flavor, created with:

```console
$ npx create-react-app react-app-ts --template typescript
```

Some remarks, where this deviates from global README:
- ESLint: install with TypeScript indicated. Rest of remarks follow React app (without TypeScript)
- Be warned, that in CLI output of `npx eslint`, linting does not output TypeScript check issues. This is done separately through `tsc` like
```console
$ npx tsc --noEmit
```
- In VS Code, this should however work well with TS errors reporting into Problems tab.
