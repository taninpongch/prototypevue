<script setup lang="ts">
import { sub } from 'date-fns'
import type { Period, Range } from '~/types'

definePageMeta({
  layout: 'dashboard'
})

const { isNotificationsSlideoverOpen } = useDashboard()
const mydlg = () => { navigateTo('/organization/main')
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
    <UDashboardNavbar title="Dashboard">
    </UDashboardNavbar>

    <!-- <UContainer class="'bg-white dark:bg-gray-900 space-y-4' : 'space-y-4'"
      :ui="{ base: '', padding: 'p-4 sm:p-4 lg:p-4', constrained: '' }">
      <UCard :ui="{ body: { base: 'space-y-4', padding: 'px-4 py-4 sm:p-4' } }">
        <p class="text-5xl">web นี้คืออะไร + tutorial + mana update?</p>
      </UCard>
    </UContainer> -->
    <UCard :ui="{ body: { base: 'space-y-4', padding: 'px-4 py-4 sm:p-4' } }">
      <ULandingCTA title="Tutorial"
          description="We've built a strong, lasting partnership. Their trust is our driving force, propelling us towards shared success."
          card
          :links="[{ label: 'Go to Dev account', color: 'green', size: 'md', variant: 'solid', click: mydlg }]" />

      
      <!-- <ULandingCard title="Color Palette"
      description="Choose a primary and a gray color from your Tailwind CSS color palette. Components will be styled accordingly."
      icon="i-heroicons-swatch" color="primary" /> -->
      <!-- <ULandingCTA
    title="Trusted and supported by our amazing community"
    description="We've built a strong, lasting partnership. Their trust is our driving force, propelling us towards shared success."
    card
  /> -->
      <!-- <UDashboardCard title="TheS" description="You have 2 projects"
        :links="[{ label: 'Learn more', color: 'gray', trailingIcon: 'i-heroicons-arrow-right-20-solid' }]" />
      <UDashboardCard title="Lugent" description="You have 0 project"
        :links="[{ label: 'Learn more', color: 'gray', trailingIcon: 'i-heroicons-arrow-right-20-solid' }]" /> -->

    </UCard>
  </UDashboardPanel>
</template>

<!-- 
<template>
  <UDashboardPage>
    <UDashboardPanel grow>
      <UDashboardNavbar title="Home">
        <template #right>
          <UTooltip
            text="Notifications"
            :shortcuts="['N']"
          >
            <UButton
              color="gray"
              variant="ghost"
              square
              @click="isNotificationsSlideoverOpen = true"
            >
              <UChip
                color="red"
                inset
              >
                <UIcon
                  name="i-heroicons-bell"
                  class="w-5 h-5"
                />
              </UChip>
            </UButton>
          </UTooltip>

          <UDropdown :items="items">
            <UButton
              icon="i-heroicons-plus"
              size="md"
              class="ml-1.5 rounded-full"
            />
          </UDropdown>
        </template>
      </UDashboardNavbar>

      <UDashboardToolbar>
        <template #left>
          <HomeDateRangePicker
            v-model="range"
            class="-ml-2.5"
          />

          <HomePeriodSelect
            v-model="period"
            :range="range"
          />
        </template>
      </UDashboardToolbar>

      <UDashboardPanelContent>
        <HomeChart
          :period="period"
          :range="range"
        />

        <div class="grid lg:grid-cols-2 lg:items-start gap-8 mt-8">
          <HomeSales />
          <HomeCountries />
        </div>
      </UDashboardPanelContent>
    </UDashboardPanel>
  </UDashboardPage>
</template> -->
