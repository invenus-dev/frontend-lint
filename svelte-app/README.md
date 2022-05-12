## Linting Svelte App

Initialized Svelte via:

```console
$ npx degit sveltejs/template svelte-app
$ cd svelte-app
$ npm install
$ npm run dev
```

**Extra npm modules**

```console
$ npm install -D eslint-plugin-svelte3 postcss postcss-html stylelint-config-recommended
```

### Deviations from global Readme



**ESLint**

Basically can reuse any existing config from previous projects, and add [eslint-plugin-svelte](https://github.com/sveltejs/eslint-plugin-svelte3) (instructions in github readme).

For VSCode, add `"svelte"` into filetypes which ESLint validates (`"eslint.validate"` entry in workspace JSON).

**Stylelint**

[Following this tutorial](https://rodneylab.com/stylelint-sveltekit/) should give a hint.

I just used same settings as for Vue: `stylelint-config-prettier` and `postcss-html` for setting syntax.

**Visual Studio Code**

For VSCode, recommended to install `svelte.svelte-vscode` extension.

