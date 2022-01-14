## SvelteKit Environment Variables

---

## Installation

`npm install sveltekit-env-vars`

## How to use?

In the **_svelte.config.js_** file just add two lines of code like so

`import addEnv from 'sveltekit-env-vars';`

and

`env: addEnv(),`

```js
import adapter from '@sveltejs/adapter-auto';

import addEnv from 'sveltekit-env-vars'; // here line 1

/** @type {import('@sveltejs/kit').Config} */
const config = {
  kit: {
    adapter: adapter(),

    // hydrate the <div id="svelte"> element in src/app.html
    target: '#svelte',
  },
  env: addEnv(), // here line 2
};

export default config;
```

## .env file

Create .env in the svelte project root and for example add the KEY variable as follow

```txt
KEY=123456789
```

## Make a test

Check the validity of configuration by adding `process.env['KEY']` in any svelte component

```js
// src/routes/index.svelte

`<script>`
  ...
  console.log(process.env['KEY']);    // 123456789
  // Note. Don't write proccess.env.KEY to avoid returning the undefined value
  console.log(process.env.KEY) // undefined
  ...
`</script>`
```
