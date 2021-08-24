<script>
  export let name;
</script>

<main class="text-center p-4 max-w-xs mx-auto sm:max-w-none">
  <h1 class="text-red-500 text-6xl uppercase leading-loose font-thin">
    Hello {name}!
  </h1>
  <p class="text-gray-700">
    Visit the
    <a class="text-blue-600 hover:underline" href="https://svelte.dev/tutorial">
      Svelte tutorial
    </a>
    to learn how to build Svelte apps.
  </p>
</main>

<style lang="postcss" global>
  @tailwind base;
  @tailwind components;
  @tailwind utilities;
</style>
