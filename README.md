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

### Setting up GitHub Pages deployment

_Using custom domain_

Use [push-dir package](https://github.com/L33T-KR3W/push-dir) following instructions for [command line deployment](https://nuxtjs.org/faq/github-pages/#command-line-deployment)

Install via npm

```sh
npm install push-dir --save-dev
```

Add following commands to `package.json`:

```json
"scripts": {
  ...
  "deploy": "push-dir --dir=dist --branch=gh-pages --cleanup"
}
```

Then generate and deploy your static application:

```sh
npm run generate
npm run deploy
```

See commit: [4e00343](https://github.com/nafSadh/sandbox-nuxt/commit/4e00343b3a75cdabca9ba757f4c4c44425f68f32).

TIP: make sure your project is setup to render from `gh-pages` branch.

#### Fix lost CNAME

Apparently push dir pushes a clean slate commit to gh-pages branch, so every
time you need to add CNAME file as well. To do this easilly, just add a
`staitc/CNAME` file and thus gh-pages root will have CNAME included.
[efb4e38](https://github.com/nafSadh/sandbox-nuxt/commit/efb4e38877c03295517e2371c1efbca9fa3535ea)
