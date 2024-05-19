# create-svelte

Everything you need to build a Svelte project, powered by [`create-svelte`](https://github.com/sveltejs/kit/tree/main/packages/create-svelte).

## Project Creation

Project skeleton created for Svelte 5 and TypeScript with:

```bash
# create a new project in the current directory
pnpm create svelte
```

## Developing

Once you've created a project and installed dependencies with `npm install` (or `pnpm install` or `yarn`), start a development server:

```bash
pnpm run dev

# or start the server and open the app in a new browser tab
npm run dev -- --open
```

## Building

To create a production version of your app:

```bash
pnpm run build
```

You can preview the production build with `npm run preview`.

> To deploy your app, you may need to install an [adapter](https://kit.svelte.dev/docs/adapters) for your target environment.

# Misc

## Theme management

Using CSS variables, defined in `src/app.css` for each of the themes ('light' and 'dark').
The top level "+layout.svelte" implements the theme selection as follows:

- in the script section: defines a 'theme' variable and set it to the desired value
- in the components section: uses the theme variable to add the theme to the class 
- in the theme section: "@import '../app.css'"

For some reason, it works because at the point where the import is done, the selected
theme enables the selection of the variables corresponding to the right class.

The CSS variables can be used anythere in the application, as long as the theme class
isn't modified. If a component uses another theme class, this component and its children
will get the variables as defined in the newly specified theme.

Additionally, the preprocessor had been replaced in `svelte.config.js` in order to use
svelte preprocessor instead of vite preprocessor, and to prepend `src/app.scss` to all
scss preprocessing. This provides a mechanism to have SCSS variables and mixins. The 
idea is that `app.scss` simply includes the requires SCSS content, in this case the
files `_variables.scss` and `_mixins.scss`.

## Fonts management

Use [Fontsource](https://fontsource.org/) (see [instructions for svelte](https://fontsource.org/docs/guides/svelte)).

For instance, install 'luckiest-guy':

    npm install @fontsource/luckiest-guy

Then import it is top level '+layout.svelte':

    import '@fontsource/luckiest-guy';

And finally, use it in the CSS, dor instance global body:

    :global(body) {
        font-family: 'Luckiest Guy', system-ui;
    }

