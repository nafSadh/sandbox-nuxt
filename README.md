# Sandbox-Nuxt

> A sandbox for NuxtJS

## Build Setup

```bash
# install dependencies
$ npm install

# serve with hot reload at localhost:3000
$ npm run dev

# build for production and launch server
$ npm run build
$ npm run start

# generate static project
$ npm run generate
```

For detailed explanation on how things work, check out [Nuxt.js docs](https://nuxtjs.org).

## Developer's Note

### Create new app with Nuxt

```sh
$ npx create-nuxt-app <project-name>
```

then run locally using:

```sh
$ npm run dev
```

### Customize Buefy

Add customizing scss from https://buefy.org/documentation/customization/

1. Create a `/assets/scss/main.scss`
2. Copy the [example from buefy.org](https://buefy.org/documentation/customization)
3. Modify for ex. \$primary: #8c67ef; to another value
4. Reference in nuxt.config.{ts/js} like this:

```js
css: ['@/assets/scss/main.scss']
```

If you need to include other css files, do:

```js
css: ["@/assets/scss/main.scss", "~/assets/css/main.css"],
```

Restart Nuxt.
You may see the following error:

```
ERROR  Failed to compile with 1 errors

This dependency was not found:

* ..\assets\scss\main.scss in ./.nuxt/App.js                    friendly-errors 04:47:26

To install it, you can run: npm install --save ..\assets\scss\main.scss
```

↑ running the above command won't help.
So, try running following commands:

```sh
npm install sass-loader --save-dev
npm install --save-dev node-sass
```

Voila! Now running `npm run dev` will reflect style changes.

### prettier `␍` issue

If you face the following error:

```
  12:34  error  Delete `␍`  prettier/prettier
```

consider adding the following to `.prettierrc`:

```
  "endOfLine": "auto"
```

If face this issue on `git commit`, make sure `.prettierrc` is added to the version control.
