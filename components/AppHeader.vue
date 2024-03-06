<template>
  <header class="mt-5 flex items-start justify-between md:items-center">
    <div class="flex items-center md:space-x-12">
      <div class="hidden md:block">
        <NuxtLink
          to="/"
          class="p-2 text-xl font-semibold hover:bg-gray-200 dark:hover:bg-gray-800"
        >
          Maiky
        </NuxtLink>
      </div>

      <nav class="font-mono">
        <ul class="flex flex-col md:flex-row md:space-x-4">
          <li>
            <NuxtLink
              to="/"
              class="link"
            >
              Index
            </NuxtLink>
          </li>
          <li>
            <NuxtLink
              to="/about"
              class="link"
            >
              About
            </NuxtLink>
          </li>
          <li>
            <NuxtLink
              to="/blog"
              class="link"
            >
              Blog
            </NuxtLink>
          </li>
          <li>
            <NuxtLink
              to="/projects"
              class="link"
            >
              Projects
            </NuxtLink>
          </li>
        </ul>
      </nav>
    </div>

    <ClientOnly>
      <ColorModeSelector />
    </ClientOnly>
  </header>
</template>

<style scoped>
  .link {
    @apply p-1 text-2xl hover:bg-gray-200 dark:hover:bg-gray-800 md:text-base;
  }
</style>
