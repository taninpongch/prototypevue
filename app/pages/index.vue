<script setup lang="ts">
import { sub } from 'date-fns'
import type { Period, Range } from '~/types'

definePageMeta({
  layout: 'login'
})

const isOpenLeave = ref(false);
const mydlg = () => { navigateTo('/organization/main')
}

const navigate = () => {
  navigateTo('../projects/main')
}

const navigateout = () => {
  navigateTo('/login/main')
}

const items = [[{
  label: 'New mail',
  icon: 'i-heroicons-paper-airplane',
  to: '/inbox'
}, {
  label: 'New user',
  icon: 'i-heroicons-user-plus',
  to: '/users'
}]]

const range = ref<Range>({ start: sub(new Date(), { days: 14 }), end: new Date() })
const period = ref<Period>('daily')
</script>

<template>
  <UDashboardPanel grow>
    <UDashboardPanelContent>
      <UHeader to="/login/main">
      <template #logo>
        <UAvatar size="sm" src="https://failfast.blob.core.windows.net/upload/Logo_manaForm.png" />
        Dev organization
      </template>
      <template #right>
        <UButton label="Sign out" color="red" @click="navigateout()" />
      </template>
    </UHeader>
    <ULandingCTA title="Tutorial"
            description="We've built a strong, lasting partnership. Their trust is our driving force, propelling us towards shared success."
            card />
    <UContainer class="'bg-white dark:bg-gray-900 space-y-4' : 'space-y-4'"
      :ui="{ base: '', padding: 'p-4 sm:p-4 lg:p-4', constrained: '' }">
      <!-- <p class="py-4 ">Dev Organization List</p> -->
      <!-- <UCard :ui="{ body: { base: 'space-y-4', padding: 'px-4 py-4 sm:p-4' } }"> -->
        <li class="flex items-center justify-between gap-3 py-3 px-4 sm:px-6">
          <div class="flex items-center gap-3 min-w-0">
            <div class="text-sm min-w-0">
              <p class="text-gray-900 dark:text-white font-medium truncate">2 Dev Organization</p>
            </div>
          </div>
        </li>
        <!-- <UDivider /> -->
        <ul class="divide-y divide-gray-200 dark:divide-gray-800">
          <li class="flex items-center justify-between gap-3 py-3 px-4 sm:px-6">
            <div @click="navigate()" class="flex items-center gap-3 min-w-0">
              <!-- <div class="">
                <UCheckbox />
              </div> -->
              <span
                class="relative inline-flex items-center justify-center flex-shrink-0 rounded-full h-10 w-10 text-base">
                <img class="rounded-full h-10 w-10 text-base"
                  src="https://placehold.co/600x600.png">
              </span>
              <div class="text-sm min-w-0">
                <p class="text-gray-900 dark:text-white font-medium truncate">TheS (Owner)</p>
                <p class="text-gray-400 dark:text-white font-medium truncate">คุณมีโปรเจคทั้งหมด 2 โปรเจค</p>
              </div>
            </div>
            <div class="flex items-center gap-3">
              <div class="relative" @click="isOpenLeave = true">
                <UButton color="red" label="Leave" />
              </div>
              <div class="relative" @click="navigate">
                <UButton label="Go to organazation" />
              </div>
            </div>
          </li>

          <li class="flex items-center justify-between gap-3 py-3 px-4 sm:px-6">
            <div @click="navigate()" class="flex items-center gap-3 min-w-0">
              <!-- <div class="">
                <UCheckbox />
              </div> -->
              <span
                class="relative inline-flex items-center justify-center flex-shrink-0 rounded-full h-10 w-10 text-base">
                <img class="rounded-full h-10 w-10 text-base"
                  src="https://placehold.co/600x600.png">
              </span>
              <div class="text-sm min-w-0">
                <p class="text-gray-900 dark:text-white font-medium truncate">Lugent (Member)</p>
                <p class="text-gray-400 dark:text-white font-medium truncate">คุณมีโปรเจคทั้งหมด 0 โปรเจค</p>
              </div>
            </div>
            <div class="flex items-center gap-3">
              <div class="relative" @click="isOpenLeave = true">
                <UButton color="red" label="Leave" />
              </div>
              <div class="relative" @click="navigate">
                <UButton label="Go to organazation" />
              </div>
            </div>
          </li>
        </ul>
      <!-- </UCard> -->

      <div>
        <UModal v-model="isOpenLeave">
          <UCard :ui="{ ring: '', divide: 'divide-y divide  -gray-100 dark:divide-gray-800' }">
            <template #header>
              <p class="py-2 text-center">Leave Dev Account</p>
            </template>
            <template #footer>
              <div class="flex flex-wrap items-center gap-4 pt-4" v-bind:class="{ 'justify-end': 'justify-between' }">
                <div class="flex flex-wrap items-center gap-4">
                  <UButton label="Cancel" color="red" />
                  <UButton label="confirm" color="green" />
                </div>
              </div>
            </template>
          </UCard>
        </UModal>
      </div>
    </UContainer>


  </UDashboardPanelContent>
  </UDashboardPanel>
</template>
