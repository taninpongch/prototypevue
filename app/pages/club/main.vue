<template>
  <UDashboardPanel grow>
    <UDashboardNavbar title="Club">
    </UDashboardNavbar>
    <UDashboardPanelContent>
      <!-- <UContainer class="'bg-white dark:bg-gray-900 space-y-4' : 'space-y-4'"
        :ui="{ base: '', padding: 'p-4 sm:p-4 lg:p-4', constrained: '' }">
        <p class="py-4 ">Club ต่างๆที่ทาง mana เปิดให้นักพัฒนาสามารถเข้าใช้งานผ่าน API โดยแบ่งแยกออกตามหมวดหมู่ได้ดังนี้
        </p>
      </UContainer> -->


      <ULandingSection class="sm:py-6" title="Clubs for Mana dev account" />


      <!-- <UCard :ui="{ body: { base: 'space-y-4', padding: 'px-4 py-4 sm:p-4' } }"> -->
      <div class="flex items-center justify-center">
        <UButtonGroup size="sm" orientation="horizontal">
          <UInput />
          <UButton icon="i-ion-md-search" color="gray" />
        </UButtonGroup>
      </div>

      <li class="flex items-center justify-between gap-3 py-3 px-4 sm:px-6">
        <div class="flex items-center gap-3 min-w-0">
          <div class="text-sm min-w-0">
            <p class="text-gray-900 dark:text-white font-medium truncate">9 Results</p>
          </div>
        </div>
        <div class="flex items-center gap-3">
          <div class="relative">
            <UDropdown :items="fliter" :popper="{ placement: 'bottom-start' }">
              <UButton label="Price" color="white" trailing-icon="i-ion-chevron-down-sharp" />
            </UDropdown>
          </div>
        </div>
      </li>
      <!-- </UCard> -->
      <UPageGrid :ui="{ wrapper: 'grid grid-cols-4 sm:grid-cols-4 xl:grid-cols-4 gap-4' }">
        <UPageCard v-for="(module, index) in modules" :key="index" v-bind="module" target="_self"
          :ui="{ wrapper: 'grid grid-cols-4 sm:grid-cols-2 xl:grid-cols-3' }">
          <template #description>
            <!-- <span class="line-clamp-2">{{ module.description }}</span> -->
            <UAlert title="FREE"></UAlert>
            <UAlert title="FREE TRAIL"></UAlert>
          </template>
        </UPageCard>
      </UPageGrid>
    </UDashboardPanelContent>
  </UDashboardPanel>
</template>

<script setup lang="ts">
const modules = [{
  title: 'Service Management',
  description: 'ESLint module for Nuxt.',
  to: '/club/clubA',
  icon: 'i-simple-icons-eslint'
}, {
  title: 'Service Publishing',
  description: 'Add Tailwind CSS to your Nuxt application in seconds with PurgeCSS included for minimal CSS.',
  to: '/club/clubA',
  icon: 'i-simple-icons-tailwindcss'
}, {
  title: 'Business Management',
  description: 'Add Tailwind CSS to your Nuxt application in seconds with PurgeCSS included for minimal CSS.',
  to: '/club/clubA',
  icon: 'i-simple-icons-tailwindcss'
}, {
  title: 'Membership Management',
  description: 'Collection of essential Vue Composition Utilities for Vue 2 and 3.',
  to: '/club/clubA',
  icon: 'i-simple-icons-nuxtdotjs',
}, {
  title: 'Products and Orders',
  description: 'ESLint module for Nuxt.',
  to: '/club/clubA',
  icon: 'i-simple-icons-eslint'
}
, {
  title: 'Promotions',
  description: 'ESLint module for Nuxt.',
  to: '/club/clubA',
  icon: 'i-simple-icons-eslint'
}
, {
  title: 'Transaction Management',
  description: 'ESLint module for Nuxt.',
  to: '/club/clubA',
  icon: 'i-simple-icons-eslint'
}
, {
  title: 'Interaction and Messaging',
  description: 'ESLint module for Nuxt.',
  to: '/club/clubA',
  icon: 'i-simple-icons-eslint'
}
, {
  title: 'Data Analytics',
  description: 'ESLint module for Nuxt.',
  to: '/club/clubA',
  icon: 'i-simple-icons-eslint'
}]

const fliter = [
  [{
    label: 'All',
    click: () => {
      console.log('All');
    }
  },
  {
    label: 'Free',
    click: () => {
      console.log('Owner')
    }
  }, {
    label: 'Paid',
    click: () => {
      console.log('Member')
    }
  }]
]
</script>