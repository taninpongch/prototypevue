<script setup lang="ts">
const modules = [{
  title: 'VueUse',
  description: 'Collection of essential Vue Composition Utilities for Vue 2 and 3.',
  to: 'https://github.com/vueuse/vueuse',
  icon: 'i-simple-icons-nuxtdotjs'
}, {
  title: 'ESLint',
  description: 'ESLint module for Nuxt.',
  to: 'https://github.com/nuxt-community/eslint-module',
  icon: 'i-simple-icons-eslint'
}, {
  title: 'Tailwind CSS',
  description: 'Add Tailwind CSS to your Nuxt application in seconds with PurgeCSS included for minimal CSS.',
  to: 'https://github.com/nuxt-modules/tailwindcss',
  icon: 'i-simple-icons-tailwindcss'
}, {
  title: 'Tailwind CSS',
  description: 'Add Tailwind CSS to your Nuxt application in seconds with PurgeCSS included for minimal CSS.',
  to: 'https://github.com/nuxt-modules/tailwindcss',
  icon: 'i-simple-icons-tailwindcss'
}]
</script>

<template>
  
  
  
  <UDashboardPanel grow>
    <UDashboardNavbar title="Club">
    </UDashboardNavbar>
    
    <UContainer class="'bg-white dark:bg-gray-900 space-y-4' : 'space-y-4'"
      :ui="{ base: '', padding: 'p-4 sm:p-4 lg:p-4', constrained: '' }">
      <p class="py-4 ">Club ต่างๆที่ทาง mana เปิดให้นักพัฒนาสามารถเข้าใช้งานผ่าน API โดยแบ่งแยกออกตามหมวดหมู่ได้ดังนี้</p>
  </UContainer>
    <UPageGrid>
      <UPageCard v-for="(module, index) in modules" :key="index" v-bind="module" target="_blank" :ui="{ wrapper: 'grid grid-cols-4 sm:grid-cols-2 xl:grid-cols-3' }">
        <template #description>
          <span class="line-clamp-2">{{ module.description }}</span>
        </template>
      </UPageCard>
    </UPageGrid>

  </UDashboardPanel>
</template>

