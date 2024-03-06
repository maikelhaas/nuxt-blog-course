<template>
  <NuxtLayout>
    <section>
      <h1 class="mb-4 text-4xl">Oeps! {{ error?.statusCode }}</h1>
      <h2 class="text-1xl text-gray-500 dark:text-gray-400">
        {{ error?.statusMessage }}
      </h2>
    </section>
  </NuxtLayout>
</template>

<script setup>
  defineProps({ error: { type: Object, default: undefined } })
</script>

<style lang="scss" scoped></style>
