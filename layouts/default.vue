<template>
  <div class="container mx-auto max-w-4xl">
    <AppHeader />

    <main class="mt-10 p-2">
      <slot />
    </main>
  </div>
</template>

<script setup>
  useHead({
    titleTemplate: '%s - Maiky',
    link: [
      {
        rel: 'preconnect',
        href: 'https://fonts.googleapis.com'
      },
      {
        rel: 'stylesheet',
        href: 'https://fonts.googleapis.com/css2?family=Inter&display=swap',
        crossorigin: ''
      }
    ]
  })
</script>

<style>
  body {
    @apply bg-white text-gray-700 dark:bg-gray-900 dark:text-gray-300;
    font-family: 'Inter', sans-serif;
  }
</style>
