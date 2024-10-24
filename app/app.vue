<script setup lang="ts">
const colorMode = useColorMode()

const color = computed(() => colorMode.value === 'dark' ? '#111827' : 'white')

useHead({
  meta: [
    { charset: 'utf-8' },
    { name: 'viewport', content: 'width=device-width, initial-scale=1' },
    { key: 'theme-color', name: 'theme-color', content: color }
  ],
  link: [
    { rel: 'icon', href: '/favicon.ico' }
  ],
  htmlAttrs: {
    lang: 'en'
  }
})

const title = 'Nuxt UI Pro - Dashboard template'
const description = 'Nuxt UI Pro is a collection of premium Vue components built on top of Nuxt UI to create beautiful & responsive Nuxt applications in minutes.'

useSeoMeta({
  title,
  description,
  ogTitle: title,
  ogDescription: description,
  ogImage: 'https://dashboard-template.nuxt.dev/social-card.png',
  twitterImage: 'https://dashboard-template.nuxt.dev/social-card.png',
  twitterCard: 'summary_large_image'
})
</script>

<template>
  <div>
    <NuxtLoadingIndicator />

    <NuxtLayout>
      <NuxtPage />
    </NuxtLayout>

    <UModals />
  </div>

  <!-- <UDashboardPanel grow>
    <UDashboardNavbar title="Topup">
      <UCard class="h-screen ">
        <div class="text-center mx-auto w-full ">
          <p class="font-semibold"> Use mana scan to login</p>
          <UAvatar class="mx-auto mb-2 "
            src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQEpxWQV3aLEcH8H6IKhAr3_WvERMBKHNFpZw&s" size="4xl">
          </UAvatar>
        </div>
        <UButton block :ui="{ rounded: 'rounded-full' }" @click="$router.push('/A2')">สร้าง QR เติมเงิน</UButton>
        <NuxtLink to="/A4">Go to A4</NuxtLink>
      </UCard>
    </UDashboardNavbar> 
   </UDashboardPanel>-->

</template>
