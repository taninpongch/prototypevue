<template>
  <UDashboardPanel grow>
    <UHeader to="/login/main">
      <template #logo>
        <UAvatar size="sm" src="https://failfast.blob.core.windows.net/upload/Logo_manaForm.png" />
        Dev organization
      </template>
      <template #right>
        <UButton label="Sign in" @click="navigatein()" />
        <UButton label="Sign up" color="green" @click="navigateup()" />
      </template>
    </UHeader>

    <UContainer class="'bg-white dark:bg-gray-900 space-y-4' : 'space-y-4'"
      :ui="{ base: '', padding: 'p-4 sm:p-4 lg:p-4', constrained: '' }">
      <!-- <UCard :ui="{ body: { base: 'space-y-4', padding: 'px-4 py-4 sm:p-4' } }"> -->
        <div @click="navigate()" class="text-center mx-auto">
          <p class="font-semibold">Login เพื่อเข้าใช้งาน</p>
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

      <!-- </UCard> -->
    </UContainer>
  </UDashboardPanel>
</template>

<script setup lang="ts">
const navigate = () => {
  navigateTo('/')
}

const navigatein = () => {
  navigateTo('signIn')
}

const navigateup = () => {
  navigateTo('signUp')
}

definePageMeta({
  layout: 'login'
})

</script>