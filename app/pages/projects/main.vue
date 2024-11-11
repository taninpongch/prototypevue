<template>
  <UDashboardPanel grow>
    <UDashboardNavbar title="TheS">
    </UDashboardNavbar>

    <!-- <TODO: content> -->
    <UContainer class="'bg-white dark:bg-gray-900 space-y-4' : 'space-y-4'"
      :ui="{ base: '', padding: 'p-4 sm:p-4 lg:p-4', constrained: '' }">
      <p class="py-4 ">All</p>
      <UCard :ui="{ body: { base: 'space-y-4', padding: 'px-4 py-4 sm:p-4' } }">
        <div class="flex items-center justify-center">
          <UButtonGroup size="sm" orientation="horizontal">
            <UInput />
            <UButton icon="i-ion-md-search" color="gray" />
          </UButtonGroup>
          <UAlert variant="soft" :closeButton="{ label: 'New Project', variant: 'solid', to: 'createProject' }" />
        </div>

        <li class="flex items-center justify-between gap-3 py-3 px-4 sm:px-6">
          <div class="flex items-center gap-3 min-w-0">
            <div class="text-sm min-w-0">
              <p class="text-gray-900 dark:text-white font-medium truncate">2 Projects</p>
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
              <div class="text-sm min-w-0">
                <p class="text-gray-900 dark:text-white font-medium truncate">Delivery</p>
                <p class="text-gray-400 dark:text-white font-medium truncate">ออกแบบ Project
                  มาเพื่อใช้สำหรับขนส่งอาหารให้ถึงมือผู้บริโภค</p>
              </div>
            </div>
            <div class="flex items-center gap-3">
              <div class="relative">
                <p class="text-gray-900 dark:text-white font-medium truncate">15 member</p>
              </div>
              <div data-headlessui-state="" class="relative inline-flex text-left rtl:text-right" position="bottom-end">
                <div disabled="false" id="headlessui-menu-button-v-0-58-1" aria-haspopup="menu" aria-expanded="false"
                  data-headlessui-state="" class="inline-flex w-full" role="button">
                  <button type="button"
                    class="focus:outline-none focus-visible:outline-0 disabled:cursor-not-allowed disabled:opacity-75 aria-disabled:cursor-not-allowed aria-disabled:opacity-75 flex-shrink-0 font-medium rounded-md text-sm gap-x-1.5 p-1.5 text-gray-700 dark:text-gray-200 hover:text-gray-900 dark:hover:text-white hover:bg-gray-50 dark:hover:bg-gray-800 focus-visible:ring-inset focus-visible:ring-2 focus-visible:ring-primary-500 dark:focus-visible:ring-primary-400 inline-flex items-center">
                    <span>
                      <UDropdown :items="items" :popper="{ placement: 'bottom-start' }">
                        <UButton color="white" trailing-icon="i-ion:ellipsis-horizontal-sharp" />
                      </UDropdown>
                    </span>
                  </button>
                </div>
              </div>
            </div>
          </li>
          <li class="flex items-center justify-between gap-3 py-3 px-4 sm:px-6">
            <div @click="navigate()" class="flex items-center gap-3 min-w-0">
              <!-- <div class="">
                <UCheckbox />
              </div> -->
              <div class="text-sm min-w-0">
                <p class="text-gray-900 dark:text-white font-medium truncate">Salary</p>
                <p class="text-gray-400 dark:text-white font-medium truncate">
                  เขียนเว็บเพื่อจัดการการจ่ายเงินเดือนพนักงาน</p>
              </div>
            </div>
            <div class="flex items-center gap-3">
              <div class="relative">
                <p class="text-gray-900 dark:text-white font-medium truncate">6 member</p>
              </div>
              <div data-headlessui-state="" class="relative inline-flex text-left rtl:text-right" position="bottom-end">
                <div disabled="false" id="headlessui-menu-button-v-0-58-1" aria-haspopup="menu" aria-expanded="false"
                  data-headlessui-state="" class="inline-flex w-full" role="button">
                  <button type="button"
                    class="focus:outline-none focus-visible:outline-0 disabled:cursor-not-allowed disabled:opacity-75 aria-disabled:cursor-not-allowed aria-disabled:opacity-75 flex-shrink-0 font-medium rounded-md text-sm gap-x-1.5 p-1.5 text-gray-700 dark:text-gray-200 hover:text-gray-900 dark:hover:text-white hover:bg-gray-50 dark:hover:bg-gray-800 focus-visible:ring-inset focus-visible:ring-2 focus-visible:ring-primary-500 dark:focus-visible:ring-primary-400 inline-flex items-center">
                    <span>
                      <UDropdown :items="items" :popper="{ placement: 'bottom-start' }">
                        <UButton color="white" trailing-icon="i-ion:ellipsis-horizontal-sharp" />
                      </UDropdown>
                    </span>
                  </button>
                </div>
              </div>
            </div>
          </li>
        </ul>

        <UModal v-model="isOpenRemove">
          <UCard :ui="{ ring: '', divide: 'divide-y divide  -gray-100 dark:divide-gray-800' }">
            <template #header>
              <p class="py-2 text-center">Removing 1 Project</p>
            </template>
            <p>The following project will be removed:</p>
            <UAlert title="Delivery" icon="material-symbols-light:contract-edit-outline-rounded" variant="solid" />
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
      </UCard>
    </UContainer>

  </UDashboardPanel>
</template>

<script setup lang="ts">
const isOpenRemove = ref(false)

const navigate = () => {
  navigateTo('detail')
}

const items = [
  [{
    label: 'Remove',
    click: () => {
      console.log('Remove')
      isOpenRemove.value = true
    }
  }]
]

</script>
