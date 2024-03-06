<template>
  <ul>
    <li v-for="link in links" :key="link.id">
      <NuxtLink
        :class="{ 'ml-4': level }"
        :to="{ path: route.path, hash: `#${link.id}` }"
      >
        {{ link.text }}
      </NuxtLink>
      <TableOfContents :links="link.children" :level="level + 1" />
    </li>
  </ul>
</template>

<script setup>
  const route = useRoute()
  defineProps({
    links: { type: Array, default: undefined },
    level: { type: Number, default: 0 }
  })
</script>
