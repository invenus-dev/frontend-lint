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
- this Readme file.

## Install steps on custom projects

### Prettier

- Install via

```console
$ npm install --save-dev --save-exact prettier
```

- create a `.prettierrc` file in the project folder with any settings

### ESLint

- Best is to follow config steps as presented by script. This should add all required libs and add `.eslintrc.js` file (or simmilar, this is chosen by you in questions). Make sure you tick environments properly - most often `browser` and `node` will be your case.

```console
$ npm install eslint --save-dev
$ npm init @eslint/config
```

- Add prettier config to ESLint like

```console
$ npm install --save-dev eslint-config-prettier
```

and add `prettier` as entry into `eslintrc.cjs`

- CLI usage: you can call the lint explicitly from command line. Add `--ext` for any suffix you want to lint, and then path to folder / file to test.

```console
$ npx eslint src/ --ext .js,.jsx
```

- To limit ESLint trying to parse parent folders for configuration, use `root: true` in the top-most config.

### Stylelint

- install via

```console
$ npm install --save-dev stylelint stylelint-config-standard stylelint-config-prettier
```

- [follow this guide](https://stylelint.io/user-guide/get-started) to craft a new `stylelintrc.json` file - with the prettier one we use

```json
{
  "extends": ["stylelint-config-standard", "stylelint-config-prettier"]
}
```

- CLI usage: call linting any time with

```console
$ npx stylelint "**/*.css"
```

## Visual Studio settings

- Official plugins recommended to use:
  - [Prettier - Code formatter](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)
  - [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)
  - [Stylelint](https://marketplace.visualstudio.com/items?itemName=stylelint.vscode-stylelint)
- After installing, you need to adjust settings of the plugins. See below for example. This is workspace settings, Action > Open Workspace Settings (JSON).

```json
{
  "folders": [
    {
      "path": "folder-in-project"
    }
  ],
  "settings": {
    "editor.defaultFormatter": "esbenp.prettier-vscode",
    "editor.codeActionsOnSave": {
      "source.fixAll.eslint": true,
      "source.fixAll.stylelint": true
    },
    "[css]": {
      "editor.defaultFormatter": "stylelint.vscode-stylelint"
    },
    "stylelint.validate": ["css"],
    "eslint.validate": ["javascript"]
  }
}
```
