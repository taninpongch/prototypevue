<template>
  <UDashboardPanel grow>
    <UHeader to="/login/main">
      <template #logo>
        <UAvatar size="sm" src="https://failfast.blob.core.windows.net/upload/Logo_manaForm.png" />
        Mana Dev Account
      </template>
      <template #right>
        <UButton label="Sign in" @click="navigatein()" />
        <UButton label="Sign up" color="green" @click="navigateup()" />
      </template>
    </UHeader>

    <ULandingSection title="The freedom to build anything"
      description="Nuxt UI Pro ships with an extensive set of advanced components that cover a wide range of use-cases."
      :features="[{
        name: '1. load app mana',
        description: 'Like Nuxt UI, change the style of any component from your App Config or customize them specifically through the ui prop.',
        icon: 'i-heroicons-wrench-screwdriver'
      },{
        name: '2.ทำการสร้างร้าน BA',
        description: 'Like Nuxt UI, change the style of any component from your App Config or customize them specifically through the ui prop.',
        icon: 'i-heroicons-wrench-screwdriver'
      },{
        name: '3.ใช้ app mana สแกน QR ด้านซ้ายมือ เพื่อสร้าง Dev Account',
        description: 'Like Nuxt UI, change the style of any component from your App Config or customize them specifically through the ui prop.',
        icon: 'i-heroicons-wrench-screwdriver'
      }]" align="right">

      <div class="text-center mx-auto">
          <p class="font-semibold">สแกน QR code เพื่อ sign up</p>
          <UAvatar :ui="{ rounded: '', size: '3xs' }"
            src="https://upload.wikimedia.org/wikipedia/commons/d/d0/QR_code_for_mobile_English_Wikipedia.svg"
            size="3xl" class="mx-auto mb-2" />
          <div>
            <ULink to="https://www.google.com/" active-class="text-primary"
              inactive-class="text-blue-500 dark:text-blue-400 hover:text-blue-700 dark:hover:text-blue-200">
              เปิด App mana
            </ULink>
          </div>
        </div>
    </ULandingSection>
  </UDashboardPanel>
</template>

<script setup lang="ts">
definePageMeta({
  layout: 'login'
})

const navigatein = () => {
  navigateTo('signIn')
}

const navigateup = () => {
  navigateTo('signUp')
}
</script>