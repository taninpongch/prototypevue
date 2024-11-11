<template>
  <UDashboardPanel grow>
    <UDashboardNavbar title="Clubs">
    </UDashboardNavbar>
    <UDashboardPanelContent>

      <UHorizontalNavigation :links="links" class="border-b border-gray-200 dark:border-gray-800" />
      <UContainer class="'bg-white dark:bg-gray-900 space-y-4' : 'space-y-4'"
        :ui="{ base: '', padding: 'p-4 sm:p-4 lg:p-4', constrained: '' }">
        <ULandingCTA title="Service Management"
          description="We've built a strong, lasting partnership. Their trust is our driving force, propelling us towards shared success."
          card
          :links="[{ label: 'Get Started', color: 'green', size: 'md', variant: 'solid', click: mydlg }, { label: '7 days free trial', variant: 'link', color: 'gray', size: 'md' }]" />


        <div class="space-y-4 px-4 py-4">
          <UFormGroup class="py-2" label="Club details" />
          <p>Publisher: TheS</p>
          <p>Last updated: Jun 11, 2024 at 11:30 PM</p>
          <UDivider />
          <UFormGroup class="py-2" label="Example Configuration" />
          <p>XXXXXXXXX</p>
          <p>XXXXXXXXX</p>
          <p>XXXXXXXXX</p>
          <UDivider />
          <UFormGroup label="Known Limitations" />
          <UFormGroup label="Set up required" />
          <UFormGroup label="Example Configuration">
          </UFormGroup>
        </div>

        <UModal v-model="isOpenAddClub">
          <UCard :ui="{ ring: '', divide: 'divide-y divide  -gray-100 dark:divide-gray-800' }">
            <template #header>
              <p class="py-2">Select a Dev account</p>
            </template>
            <li class="flex items-center justify-between gap-3 py-3 px-4 sm:px-6">
              <div class="flex items-center gap-3 min-w-0">
                <div class="">
                  <UCheckbox />
                </div>
                <div class="text-sm min-w-0">
                  <p class="text-gray-900 dark:text-white font-medium truncate">TheS</p>
                </div>
              </div>
            </li>
            <li class="flex items-center justify-between gap-3 py-3 px-4 sm:px-6">
              <div class="flex items-center gap-3 min-w-0">
                <div class="">
                  <UCheckbox />
                </div>
                <div class="text-sm min-w-0">
                  <p class="text-gray-900 dark:text-white font-medium truncate">Lugent</p>
                </div>
              </div>
            </li>

            <template #footer>
              <div class="flex flex-wrap items-center gap-4 pt-4" v-bind:class="{ 'justify-end': 'justify-between' }">
                <div class="flex flex-wrap items-center gap-4">
                  <UButton label="Cancel" color="red" />
                  <UButton label="Install" color="green" />
                </div>
              </div>
            </template>
          </UCard>
        </UModal>
      </UContainer>

    </UDashboardPanelContent>
  </UDashboardPanel>
</template>

<script setup lang="ts">
definePageMeta({
  layout: 'dashboard'
});

const isOpenAddClub = ref(false)

const links = [
  [{
    label: 'Clubs',
    icon: 'i-ion-grid-outline',
    to: '/club/main'
  },{
    label: 'Overview',
    icon: 'i-ion-binoculars-outline',
    to: '/club/clubA'
  }, {
    label: 'Pricing',
    icon: 'i-material-symbols-light:paid-outline-rounded',
    to: '/club/pricing'
  }]
]

const infos: any[] = [
  { label: "Name", value: "Delivery" },
  { label: "Description", value: "ออกแบบ Project มาเพื่อใช้สำหรับขนส่งอาหารให้ถึงมือผู้บริโภค" }
];

const mydlg = () => { isOpenAddClub.value = true }
</script>