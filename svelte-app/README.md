## Linting Svelte App

Initialized Svelte via:

```console
$ npx degit sveltejs/template svelte-app
$ cd svelte-app
$ npm install
$ npm run dev
```

### Deviations from global Readme

**ESLint**

Basically can reuse any existing config from previous projects, and add [eslint-plugin-svelte](https://github.com/sveltejs/eslint-plugin-svelte3) (instructions in github readme).

For VSCode, add `"svelte"` into filetypes which ESLint validates (`"eslint.validate"` entry in workspace JSON).

**Stylelint**

[Follwing this tutorial](https://rodneylab.com/stylelint-sveltekit/) should give a hint.

I just used same settings as for Vue: `stylelint-config-prettier` and `postcss-html` for setting syntax.