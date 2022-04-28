## Linting Vue App with TypeScript

### Deviations from global Readme

- Vue init via `npm init vue@latest`, the only difference from `vue-app` was selected TS
  - offers ESLint (ticked yes)
  - offers Prettier (ticked yes)
- I added a `.prettierrc` file
- there is recommended tooling for vscode - `johnsoncodehk.volar` + `johnsoncodehk.vscode-typescript-vue-plugin`. And this issue: see https://github.com/johnsoncodehk/volar/discussions/592 - it did not manifested in TS version.

### Stylelint, ESlint

- follow readme of vue-app regarding stylelint

### Actions

- there are actions defined in `package.json` that you can use for standalone checks:

```json
  "scripts": {    
    "typecheck": "vue-tsc --noEmit -p tsconfig.vitest.json --composite false",
    "lint": "eslint . --ext .vue,.js,.jsx,.cjs,.mjs,.ts,.tsx,.cts,.mts --fix --ignore-path .gitignore  && stylelint **/*.vue"
  },
```
