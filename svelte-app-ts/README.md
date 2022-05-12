## Linting Svelte App with TypeScript

Initialized Svelte via:

```console
$ npx degit sveltejs/template svelte-app-ts
$ cd svelte-app
$ node scripts/setupTypeScript.js
$ npm install
$ npm run dev
```

**Extra npm modules**

```console
$ npm install -D eslint-plugin-svelte3 postcss postcss-html stylelint-config-recommended @typescript-eslint/eslint-plugin @typescript-eslint/parser
```

### Deviations from global Readme

See `svelte-app` readme for basic notes, same base configs used.

**ESLint**

There are a few changes to `.eslintrc.js`:

- added typescript parser and plugins
- removed the file itself from TS checking via `ignorePatterns` - was not able to fix the error on it otherwise
- some settings recommended as per: see https://codechips.me/eslint-svelte-typescript/
