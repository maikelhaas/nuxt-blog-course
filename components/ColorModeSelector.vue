<template>
  <div class="flex items-center space-x-2">
    <div
      v-if="nextModeLabel"
      class="text-xs text-gray-500"
    >
      Change to {{ nextMode }}
    </div>
    <button
      class="px-2 py-1 text-gray-500 hover:bg-gray-100 dark:hover:bg-gray-800"
      @click="toggleMode"
      @mouseenter="nextModeLabel = true"
      @mouseleave="nextModeLabel = false"
    >
      {{ nextModeIcon }}
    </button>
  </div>
</template>

<script setup>
  const colorMode = useColorMode()
  const nextModeLabel = ref(false)

  const modes = ['light', 'dark']

  const modeIcons = {
    light: '🌕',
    dark: '🌑'
  }

  const nextMode = computed(() => {
    const currentModeIndex = modes.indexOf(colorMode.preference)
    const nextModeIndex =
      currentModeIndex + 1 === modes.length ? 0 : currentModeIndex + 1

    return modes[nextModeIndex]
  })

  const nextModeIcon = computed(() => {
    return modeIcons[nextMode.value]
  })

  const toggleMode = () => (colorMode.preference = nextMode.value)
</script>
