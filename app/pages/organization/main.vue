<template>
  <UDashboardPanel grow>
    <UDashboardNavbar title="Dev Account">
    </UDashboardNavbar>

    <!-- <TODO: content> -->
    <UContainer class="'bg-white dark:bg-gray-900 space-y-4' : 'space-y-4'"
      :ui="{ base: '', padding: 'p-4 sm:p-4 lg:p-4', constrained: '' }">
      <p class="py-4 ">Dev Account List</p>
      <UCard :ui="{ body: { base: 'space-y-4', padding: 'px-4 py-4 sm:p-4' } }">
        <li class="flex items-center justify-between gap-3 py-3 px-4 sm:px-6">
          <div class="flex items-center gap-3 min-w-0">
            <div class="text-sm min-w-0">
              <p class="text-gray-900 dark:text-white font-medium truncate">2 Dev Account</p>
            </div>
          </div>
        </li>
        <UDivider />
        <ul class="divide-y divide-gray-200 dark:divide-gray-800">

          <li class="flex items-center justify-between gap-3 py-3 px-4 sm:px-6">
            <div @click="navigate()" class="flex items-center gap-3 min-w-0">
              <!-- <div class="">
                <UCheckbox />
              </div> -->
              <span
                class="relative inline-flex items-center justify-center flex-shrink-0 rounded-full h-10 w-10 text-base">
                <img class="rounded-full h-10 w-10 text-base"
                  src="https://aithailand.co.th/uploads/texteditor/DM-01_1630551951.png">
              </span>
              <div class="text-sm min-w-0">
                <p class="text-gray-900 dark:text-white font-medium truncate">TheS</p>
              </div>
            </div>
            <div class="flex items-center gap-3">
              <div class="relative" @click="isOpenLeave = true">
                <UButton color="red" label="Leave" />
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
                <p class="text-gray-900 dark:text-white font-medium truncate">Lugent</p>
              </div>
            </div>
            <div class="flex items-center gap-3">
              <div class="relative" @click="isOpenLeave = true">
                <UButton color="red" label="Leave" />
              </div>
            </div>
          </li>
        </ul>
      </UCard>

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

  </UDashboardPanel>
</template>

<script setup lang="ts">
const isOpenRemove = ref(false)
const isOpenChange = ref(false)
const selected = ref('sms')
const isOpenLeave = ref(false)

const navigate = () => {
  navigateTo('../projects/main')
}

const fliter = [
  [{
    label: 'All',
    click: () => {
      console.log('All');
    }
  },
  {
    label: 'Owner',
    click: () => {
      console.log('Owner')
    }
  }, {
    label: 'Member',
    click: () => {
      console.log('Member')
    }
  }]
]

const items = [
  [{
    label: 'Change Role',
    click: () => {
      console.log('Change Role');
      isOpenChange.value = true
    }
  },
  {
    label: 'Remove',
    click: () => {
      console.log('Remove')
      isOpenRemove.value = true
    }
  }]
]

</script>
