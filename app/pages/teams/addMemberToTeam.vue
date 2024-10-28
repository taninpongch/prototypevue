<template>
  <UDashboardPanel grow>
    <UDashboardNavbar title="The-S-Dev">
    </UDashboardNavbar>

    <!-- <TODO: content> -->
    <UContainer class="'bg-white dark:bg-gray-900 space-y-4' : 'space-y-4'"
      :ui="{ base: '', padding: 'p-4 sm:p-4 lg:p-4', constrained: '' }">
      <UCard :ui="{ body: { base: 'space-y-4', padding: 'px-4 py-4 sm:p-4' } }">
        <p class="py-4 ">Add a member to team</p>
        <UFormGroup label="Search by member name" />
        <UButtonGroup size="sm" orientation="horizontal">
          <UInput />
          <UButton icon="i-ion-md-search" color="gray" />
        </UButtonGroup>

        <UDivider />
        <ul class="divide-y divide-gray-200 dark:divide-gray-800">

          <li class="flex items-center justify-between gap-3 py-3 px-4 sm:px-6">
            <div class="flex items-center gap-3 min-w-0">
              <div class="">
                <UCheckbox />
              </div>
              <div class="text-sm min-w-0">
                <p class="text-gray-900 dark:text-white font-medium truncate">Aurora</p>
              </div>
            </div>
          </li>
          <li class="flex items-center justify-between gap-3 py-3 px-4 sm:px-6">
            <div class="flex items-center gap-3 min-w-0">
              <div class="">
                <UCheckbox />
              </div>
              <div class="text-sm min-w-0">
                <p class="text-gray-900 dark:text-white font-medium truncate">Tatae999</p>
              </div>
            </div>
          </li>
          <li class="flex items-center justify-between gap-3 py-3 px-4 sm:px-6">
            <div class="flex items-center gap-3 min-w-0">
              <div class="">
                <UCheckbox />
              </div>
              <div class="text-sm min-w-0">
                <p class="text-gray-900 dark:text-white font-medium truncate">Pao Pao</p>
              </div>
            </div>
          </li>
          <li class="flex items-center justify-between gap-3 py-3 px-4 sm:px-6">
            <div class="flex items-center gap-3 min-w-0">
              <div class="">
                <UCheckbox />
              </div>
              <div class="text-sm min-w-0">
                <p class="text-gray-900 dark:text-white font-medium truncate">Mr. P</p>
              </div>
            </div>
          </li>
        </ul>
      </UCard>

      <div class="flex flex-wrap items-center gap-4 pt-4" v-bind:class="{ 'justify-end': 'justify-between' }">
        <div class="flex flex-wrap items-center gap-4">
          <UButton @click="$router.back()" label="Cancel" color="white" />
          <UButton label="Add to team" color="green" @click="isOpen = true" />

          <UModal v-model="isOpen">
            <UCard :ui="{ ring: '', divide: 'divide-y divide  -gray-100 dark:divide-gray-800' }">
              <template #header>
                <p class="py-2">Add a member to team</p>
                <UAlert title="Aurora" icon="i-ion-ios-person-outline" variant="solid"
                  :closeButton="{ icon: 'i-heroicons-x-mark-20-solid', variant: 'soft', color: 'white' }" />
                <UAlert title="Tatae999" icon="i-ion-ios-person-outline" variant="solid"
                  :closeButton="{ icon: 'i-heroicons-x-mark-20-solid', variant: 'soft', color: 'white' }" />
              </template>

              <template #footer>
                <div class="flex flex-wrap items-center gap-4 pt-4" v-bind:class="{ 'justify-end': 'justify-between' }">
                  <div class="flex flex-wrap items-center gap-4">
                    <UButton label="Cancel" color="red" />
                    <UButton label="Confirm" color="green" />
                  </div>
                </div>
              </template>
            </UCard>
          </UModal>
        </div>
      </div>
    </UContainer>

  </UDashboardPanel>
</template>

<script setup lang="ts">
const isOpen = ref(false)
const selected = ref('sms')

</script>
