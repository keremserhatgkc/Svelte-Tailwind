# Svelte template with Tailwind CSS

<div style="display:flex">
  <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/1b/Svelte_Logo.svg/199px-Svelte_Logo.svg.png" />
  <img src="https://seeklogo.com/images/T/tailwind-css-logo-5AD4175897-seeklogo.com.png" />
</div>

<br>

## Setup

Setting up Tailwind with Svelte is really simple, just install necessary dependencies:

```bash
npm i -D svelte-preprocess tailwindcss postcss autoprefixer
```

Create your configuration files

```bash
npx tailwindcss init
```

Configure **svelte-preprocess** in `rollup.config.js`

```js
// ...
import sveltePreprocess from 'svelte-preprocess'

// ...

export default {
  // ...
  plugins: [
    svelte({
      // ...
      preprocess: sveltePreprocess({
        sourceMap: !production,
        postcss: {
          plugins: [require('tailwindcss'), require('autoprefixer')()],
        },
      }),
    }),
    // ...
  ],
  // ...
}
```

Next, add tailwind styles into to App.svelte

```svelte
<script>
  export let name;
</script>

<main>
  <h1>Hello {name}!</h1>
  <p> Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p>
</main>

<style lang="postcss" global>
  @tailwind base;
  @tailwind components;
  @tailwind utilities;
</style>
```

Finally, add purge and JIT mode in `tailwind.config.js`:

```js
module.exports = {
  mode: 'jit',
  purge: ['./public/index.html', './src/**/*.svelte'],
  darkMode: false, // or 'media' or 'class'
  theme: {
    extend: {},
  },
  variants: {
    extend: {},
  },
  plugins: [],
}
```

<br>

## Get started with this template

Install the dependencies...

```bash
cd Svelte-Tailwind
npm install
```

...then start [Rollup](https://rollupjs.org):

```bash
npm run dev
```

## Building and running in production mode

```bash
npm run build
```
