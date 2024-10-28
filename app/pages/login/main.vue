<template>
  <UDashboardPanel grow>
    <UDashboardNavbar title="Mana Dev Account">
    </UDashboardNavbar>
    <UContainer class="'bg-white dark:bg-gray-900 space-y-4' : 'space-y-4'"
      :ui="{ base: '', padding: 'p-4 sm:p-4 lg:p-4', constrained: '' }">
      <!-- <UHorizontalNavigation :links="links" class="border-b border-gray-200 dark:border-gray-800" /> -->
      <UCard :ui="{ body: { base: 'space-y-4', padding: 'px-4 py-4 sm:p-4' } }">

      <div class="flex flex-wrap items-center gap-4" v-bind:class="{ 'justify-end': 'justify-between' }">
        <div class="flex flex-wrap items-center gap-4">
          <UButton label="Sign in"  @click="navigatein()" />
          <UButton label="Sign up" color="green" @click="navigateup()" />
        </div>
      </div>
      </UCard>
    </UContainer>
  </UDashboardPanel>
</template>


<script setup lang="ts">
const links = [
  [], [{
    label: 'sign in',
    icon: '',
    to: '/login/signIn'
  }, {
    label: 'sign up',
    icon: '',
    to: '/login/signUp'
  }]
]

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