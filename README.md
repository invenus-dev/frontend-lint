# Frontend Lint

## About

Aim of this repository is to create sensible defaults for linters in JS/CSS scope of projects.

## Tooling

We are using the following tools:

- [Prettier](https://prettier.io/) - all basic formatting
- [ESLint](https://eslint.org/) - JavaScript, TypeScript
- [Stylelint](https://stylelint.io/) - CSS

## Scopes

We are testing in various scopes:

- React (through `npx create-react-app`)
- Vue 3 (through `npm init vue@latest`)
- Svelte (through `npx degit sveltejs/template`)

All of them with and without TypeScript enabled.

## Structure

All projects reside individually in a folder of this repository.

In the root level, we only have:
- a `.nvmrc` file which fixes Node to version 16,
- a `.prettierrc` file with prettier defaults,
- this Readme file.

## Install steps on custom projects

### Prettier
- We use prettier only as a IDE part now, you can install an official plugin into your IDE
- a `.prettierrc` file needs to be present and set as default IDE formatter

### ESLint
- Best is to follow config steps as presented by script. This should add all required libs and add `.eslintrc.js` file (or simmilar, this is chosen by you in questions). Make sure you tick environments properly - most often `browser` and `node` will be your case.
```
npm install eslint --save-dev
npm init @eslint/config
```

- CLI usage: you can call the lint explicitly from command line. Add `--ext` for any suffix you want to lint, and then path to folder / file to test.
```
npx eslint --ext .js src/
```

### Stylelint

- install via 
```
npm install --save-dev stylelint stylelint-config-standard stylelint-config-prettier
```
- [follow this guide](https://stylelint.io/user-guide/get-started) to craft a new `stylelintrc.json` file - with the prettier one we use

```
{
  "extends": ["stylelint-config-standard", "stylelint-config-prettier"]
}
```
- CLI usage: call linting any time with
```
npx stylelint "**/*.css"
```