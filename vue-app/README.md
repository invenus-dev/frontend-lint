## Linting Vue App

### Deviations from global Readme

- Vue init via `npm init vue@latest` offers a few nice bits regarding linting:
  - offers ESLint (ticked yes)
  - offers Prettier (ticked yes)
- I added a `.prettierrc` file
- there is recommended tooling for vscode - `johnsoncodehk.volar` + `johnsoncodehk.vscode-typescript-vue-plugin`. Unfortunately both have issues not resolvable without Typescript config - see https://github.com/johnsoncodehk/volar/discussions/592
- Interesting repo to inspire from: https://github.com/sethidden/vue3-eslint-stylelint-demo

### Stylelint

These settings worked well for VSCode:

1. Install those

```bash
$ npm install --save-dev stylelint stylelint-config-recommended-vue stylelint-config-prettier postcss-html
```

2. Setup `.stylelintrc.json` as (the `postcss-html` is important here)

```json
{
  "extends": ["stylelint-config-recommended-vue", "stylelint-config-prettier"],
  "customSyntax": "postcss-html"
}
```

3. In VSCode (workspace) settings, where stylelint validation is dealt with, add `vue` as file format to validate as well:

```json
{
  //...
  "stylelint.validate": [
    "css",
    "vue",
  ],
  //...
}
```

