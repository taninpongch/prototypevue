<template>
  <UDashboardPanel grow>
    <UDashboardNavbar title="DA Name">
    </UDashboardNavbar>
    <!-- <TODO: content> -->
    <UDashboardPanelContent>
      <UHorizontalNavigation :links="links" class="border-b border-gray-200 dark:border-gray-800" />
      <UContainer class="'bg-white dark:bg-gray-900 space-y-4' : 'space-y-4'"
        :ui="{ base: '', padding: 'p-4 sm:p-4 lg:p-4', constrained: '' }">
        <p class="py-4 ">Project: Delivery</p>

        <UCard :ui="{ body: { base: 'space-y-4', padding: 'px-4 py-4 sm:p-4' } }">
          <!-- <div> -->
          <UFormGroup label="Project detail">
          </UFormGroup>
          <!-- </div> -->

          <UFormGroup label="Name">
            <UInput placeholder="Delivery" :ui="{ base: 'disabled:bg-gray-200 dark:disabled:bg-black' }" />
          </UFormGroup>

          <UFormGroup label="Description">
            <UInput placeholder="ออกแบบ Project มาเพื่อใช้สำหรับขนส่งอาหารให้ถึงมือผู้บริโภค"
              :ui="{ base: 'disabled:bg-gray-200 dark:disabled:bg-black' }" />
          </UFormGroup>

          <div class="flex flex-wrap items-center gap-4" v-bind:class="{ 'justify-end': 'justify-between' }">
            <div class="flex flex-wrap items-center gap-4">
              <UButton label="บันทึก" color="green" />
            </div>
          </div>
          <UDivider />

          <UContainer class="'bg-white dark:bg-gray-900 space-y-4' : 'space-y-4'"
            :ui="{ base: '', padding: 'p-4 sm:p-4 lg:p-4', constrained: '' }">
            <p class="py-4 ">Clubs</p>
            <!-- <p class="py-4 ">Add people/teams to Project </p> -->
            <UCard :ui="{ body: { base: 'space-y-4', padding: 'px-4 py-4 sm:p-4' } }">
              <div>
                <div class="flex justify-end items-end gap-4 pt-4">
                  <UButton class="flex items-center justify-end" label="Add club" color="green"
                    @click="isOpenAddClub = true" />
                </div>
                <!-- <UButtonGroup size="sm" orientation="horizontal">
                    <UInput />
                    <UButton icon="i-ion-md-search" color="gray" />
                  </UButtonGroup> -->
              </div>
              <!-- 
              <li class="flex items-center justify-between gap-3 py-3 px-4 sm:px-6">
                <div class="flex items-center gap-3 min-w-0">
                  <div class="text-sm min-w-0">
                    <p class="text-gray-900 dark:text-white font-medium truncate">2 Clubs</p>
                  </div>
                </div>
                <div class="flex items-center gap-3">
                  <div class="relative">
                    <UDropdown :items="fliter" :popper="{ placement: 'bottom-start' }">
                      <UButton label="Showing" color="white" trailing-icon="i-ion-chevron-down-sharp" />
                    </UDropdown>
                  </div>
                </div>
              </li> -->

              <ul class="divide-y divide-gray-200 dark:divide-gray-800">

                <li class="flex items-center justify-between gap-3 py-3 px-4 sm:px-6">
                  <div class="flex items-center gap-3 min-w-0">
                    <!-- <div class="">
                <UCheckbox />
              </div> -->
                    <div class="text-sm min-w-0">
                      <p class="text-gray-900 dark:text-white font-medium truncate">Business Management</p>
                      <p class="text-gray-400 dark:text-white font-medium truncate">เริ่มใช้งาน 18/10/2024 (13:41)</p>
                    </div>
                  </div>
                  <div class="flex items-center gap-3">
                    <div class="relative">
                      <p class="text-gray-900 dark:text-white font-medium truncate">Free</p>
                    </div>
                    <div data-headlessui-state="" class="relative inline-flex text-left rtl:text-right"
                      position="bottom-end">
                      <div disabled="false" id="headlessui-menu-button-v-0-58-1" aria-haspopup="menu"
                        aria-expanded="false" data-headlessui-state="" class="inline-flex w-full" role="button">
                        <button type="button"
                          class="focus:outline-none focus-visible:outline-0 disabled:cursor-not-allowed disabled:opacity-75 aria-disabled:cursor-not-allowed aria-disabled:opacity-75 flex-shrink-0 font-medium rounded-md text-sm gap-x-1.5 p-1.5 text-gray-700 dark:text-gray-200 hover:text-gray-900 dark:hover:text-white hover:bg-gray-50 dark:hover:bg-gray-800 focus-visible:ring-inset focus-visible:ring-2 focus-visible:ring-primary-500 dark:focus-visible:ring-primary-400 inline-flex items-center">
                          <span>
                            <UDropdown :items="Free" :popper="{ placement: 'bottom-start' }">
                              <UButton color="white" trailing-icon="i-ion:ellipsis-horizontal-sharp" />
                            </UDropdown>
                          </span>
                        </button>
                      </div>
                    </div>
                  </div>
                </li>
                <li class="flex items-center justify-between gap-3 py-3 px-4 sm:px-6">
                  <div class="flex items-center gap-3 min-w-0">
                    <!-- <div class="">
                <UCheckbox />
              </div> -->
                    <div class="text-sm min-w-0">
                      <p class="text-gray-900 dark:text-white font-medium truncate">Interaction and Messaging</p>
                      <p class="text-gray-400 dark:text-white font-medium truncate">เริ่มใช้งาน 1/11/2024 (09:00)
                        ใช้ได้ถึง 7/11/2024
                        (09:00)</p>
                    </div>
                  </div>
                  <div class="flex items-center gap-3">
                    <div class="relative">
                      <p class="text-gray-900 dark:text-white font-medium truncate">Paid</p>
                    </div>
                    <div data-headlessui-state="" class="relative inline-flex text-left rtl:text-right"
                      position="bottom-end">
                      <div disabled="false" id="headlessui-menu-button-v-0-58-1" aria-haspopup="menu"
                        aria-expanded="false" data-headlessui-state="" class="inline-flex w-full" role="button">
                        <button type="button"
                          class="focus:outline-none focus-visible:outline-0 disabled:cursor-not-allowed disabled:opacity-75 aria-disabled:cursor-not-allowed aria-disabled:opacity-75 flex-shrink-0 font-medium rounded-md text-sm gap-x-1.5 p-1.5 text-gray-700 dark:text-gray-200 hover:text-gray-900 dark:hover:text-white hover:bg-gray-50 dark:hover:bg-gray-800 focus-visible:ring-inset focus-visible:ring-2 focus-visible:ring-primary-500 dark:focus-visible:ring-primary-400 inline-flex items-center">
                          <span>
                            <UDropdown :items="Paid" :popper="{ placement: 'bottom-start' }">
                              <UButton color="white" trailing-icon="i-ion:ellipsis-horizontal-sharp" />
                            </UDropdown>

                          </span>
                        </button>
                      </div>
                    </div>
                  </div>
                </li>
              </ul>
            </UCard>
          </UContainer>
          <UDivider />
          <UButton label="Go to Dev portal" color="green" />

          <UModal v-model="isOpenAddClub">
            <UCard :ui="{ ring: '', divide: 'divide-y divide  -gray-100 dark:divide-gray-800' }">
              <template #header>
                <p class="py-2">Add clubs to Project (Delivery)</p>
              </template>
              <li class="flex items-center justify-between gap-3 py-3 px-4 sm:px-6">
                <div class="flex items-center gap-3 min-w-0">
                  <!-- <div class="" > -->
                  <!-- <UCheckbox /> -->
                  <UCheckbox label="Service Management" disabled help="xxxxxxxxxx" :model-value="false" />
                  <!-- </div> -->
                  <!-- <div class="text-sm min-w-0">
                  <p class="text-gray-900 dark:text-white font-medium truncate">Service Management</p>
                </div> -->
                </div>
                <div class="flex items-center gap-3">
                  <div class="relative">
                    <p class="text-gray-900 dark:text-white font-medium truncate">Slots used: 1 of 1</p>
                  </div>
                  <!-- <div data-headlessui-state="" class="relative inline-flex text-left rtl:text-right"
                  position="bottom-end">
                  <div disabled="false" id="headlessui-menu-button-v-0-58-1" aria-haspopup="menu" aria-expanded="false"
                    data-headlessui-state="" class="inline-flex w-full" role="button">
                    <button type="button"
                      class="focus:outline-none focus-visible:outline-0 disabled:cursor-not-allowed disabled:opacity-75 aria-disabled:cursor-not-allowed aria-disabled:opacity-75 flex-shrink-0 font-medium rounded-md text-sm gap-x-1.5 p-1.5 text-gray-700 dark:text-gray-200 hover:text-gray-900 dark:hover:text-white hover:bg-gray-50 dark:hover:bg-gray-800 focus-visible:ring-inset focus-visible:ring-2 focus-visible:ring-primary-500 dark:focus-visible:ring-primary-400 inline-flex items-center">
                      <span>
                        <UIcon name="i-ion-ellipsis-vertical" />
                      </span>
                    </button>
                  </div>
                </div> -->
                </div>
              </li>
              <li class="flex items-center justify-between gap-3 py-3 px-4 sm:px-6">
                <div class="flex items-center gap-3 min-w-0">
                  <!-- <div class="">
                  <UCheckbox />
                </div>
                <div class="text-sm min-w-0">
                  <p class="text-gray-900 dark:text-white font-medium truncate">Service Publishing</p>
                </div> -->
                  <UCheckbox label="Service Publishing" :model-value="false" />
                </div>
                <div class="flex items-center gap-3">
                  <div class="relative">
                    <p class="text-gray-900 dark:text-white font-medium truncate">Slots used: 0 of 1</p>
                  </div>
                  <!-- <div data-headlessui-state="" class="relative inline-flex text-left rtl:text-right" position="bottom-end">
            <div disabled="false" id="headlessui-menu-button-v-0-58-1" aria-haspopup="menu" aria-expanded="false"
              data-headlessui-state="" class="inline-flex w-full" role="button">
              <button type="button"
                class="focus:outline-none focus-visible:outline-0 disabled:cursor-not-allowed disabled:opacity-75 aria-disabled:cursor-not-allowed aria-disabled:opacity-75 flex-shrink-0 font-medium rounded-md text-sm gap-x-1.5 p-1.5 text-gray-700 dark:text-gray-200 hover:text-gray-900 dark:hover:text-white hover:bg-gray-50 dark:hover:bg-gray-800 focus-visible:ring-inset focus-visible:ring-2 focus-visible:ring-primary-500 dark:focus-visible:ring-primary-400 inline-flex items-center">
                <span>
                  <UIcon name="i-ion-ellipsis-vertical" />
                </span>
              </button>
            </div>
          </div> -->
                </div>
              </li>
              <li class="flex items-center justify-between gap-3 py-3 px-4 sm:px-6">
                <div class="flex items-center gap-3 min-w-0">
                  <!-- <div class="">
                  <UCheckbox />
                </div>
                <div class="text-sm min-w-0">
                  <p class="text-gray-900 dark:text-white font-medium truncate">The-S</p>
                </div> -->
                  <UCheckbox label="Business Management" :model-value="true" />

                </div>
                <div class="flex items-center gap-3">
                  <div class="relative">
                    <p class="text-gray-900 dark:text-white font-medium truncate">Slots used: 2 of 3</p>
                  </div>
                  <!-- <div data-headlessui-state="" class="relative inline-flex text-left rtl:text-right" position="bottom-end">
            <div disabled="false" id="headlessui-menu-button-v-0-58-1" aria-haspopup="menu" aria-expanded="false"
              data-headlessui-state="" class="inline-flex w-full" role="button">
              <button type="button"
                class="focus:outline-none focus-visible:outline-0 disabled:cursor-not-allowed disabled:opacity-75 aria-disabled:cursor-not-allowed aria-disabled:opacity-75 flex-shrink-0 font-medium rounded-md text-sm gap-x-1.5 p-1.5 text-gray-700 dark:text-gray-200 hover:text-gray-900 dark:hover:text-white hover:bg-gray-50 dark:hover:bg-gray-800 focus-visible:ring-inset focus-visible:ring-2 focus-visible:ring-primary-500 dark:focus-visible:ring-primary-400 inline-flex items-center">
                <span>
                  <UIcon name="i-ion-ellipsis-vertical" />
                </span>
              </button>
            </div>
          </div> -->
                </div>
              </li>
              <li class="flex items-center justify-between gap-3 py-3 px-4 sm:px-6">
                <div class="flex items-center gap-3 min-w-0">
                  <!-- <div class="">
                  <UCheckbox />
                </div>
                <div class="text-sm min-w-0">
                  <p class="text-gray-900 dark:text-white font-medium truncate">The-S</p>
                </div> -->
                  <UCheckbox label="Interaction and Messaging" :model-value="true" />

                </div>
                <div class="flex items-center gap-3">
                  <div class="relative">
                    <p class="text-gray-900 dark:text-white font-medium truncate">Slots used: 2 of 3</p>
                  </div>
                  <!-- <div data-headlessui-state="" class="relative inline-flex text-left rtl:text-right" position="bottom-end">
            <div disabled="false" id="headlessui-menu-button-v-0-58-1" aria-haspopup="menu" aria-expanded="false"
              data-headlessui-state="" class="inline-flex w-full" role="button">
              <button type="button"
                class="focus:outline-none focus-visible:outline-0 disabled:cursor-not-allowed disabled:opacity-75 aria-disabled:cursor-not-allowed aria-disabled:opacity-75 flex-shrink-0 font-medium rounded-md text-sm gap-x-1.5 p-1.5 text-gray-700 dark:text-gray-200 hover:text-gray-900 dark:hover:text-white hover:bg-gray-50 dark:hover:bg-gray-800 focus-visible:ring-inset focus-visible:ring-2 focus-visible:ring-primary-500 dark:focus-visible:ring-primary-400 inline-flex items-center">
                <span>
                  <UIcon name="i-ion-ellipsis-vertical" />
                </span>
              </button>
            </div>
          </div> -->
                </div>
              </li>

              <template #footer>
                <div class="flex flex-wrap items-center gap-4 pt-4" v-bind:class="{ 'justify-end': 'justify-between' }">
                  <div class="flex flex-wrap items-center gap-4">
                    <UButton label="Cancel" color="red" />
                    <UButton label="Add to Project" color="green" />
                  </div>
                </div>
              </template>
            </UCard>
          </UModal>

          <UModal v-model="isOpenUnSubscribe">
          <UCard :ui="{ ring: '', divide: 'divide-y divide  -gray-100 dark:divide-gray-800' }">
            <template #header>
              <p class="py-2 text-center">Unsubscribe 1 club</p>
            </template>
            <p>The following club will be unsubscribe:</p>
            <UAlert title="Business Management" icon="i-ion-ios-people" variant="solid" />
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

        <UModal v-model="isOpenSubscribe">
          <UCard :ui="{ ring: '', divide: 'divide-y divide  -gray-100 dark:divide-gray-800' }">
            <template #header>
              <p class="py-2 text-center">Subscribe 1 club</p>
            </template>
            <p>The following club will be subscribe:</p>
            <UAlert title="Interaction and Messaging" icon="i-ion-ios-people" variant="solid" />
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
    </UDashboardPanelContent>
  </UDashboardPanel>
</template>

<script setup lang="ts">
const isOpenAddClub = ref(false)
const isOpenUnSubscribe = ref(false)
const isOpenSubscribe = ref(false)

const links = [
  [{
    label: 'Overview',
    icon: 'i-ion-md-home',
    to: '/projects/detail'
  }, {
    label: 'Collabolators',
    icon: 'i-ion-people-sharp',
    to: '/projects/addTeamToProject'
  }]
]

const infos: any[] = [
  { label: "Name", value: "Delivery" },
  { label: "Description", value: "ออกแบบ Project มาเพื่อใช้สำหรับขนส่งอาหารให้ถึงมือผู้บริโภค" }
];

const fliter = [
  [{
    label: 'All',
    click: () => {
      console.log('All');
    }
  },
  {
    label: 'Free',
    click: () => {
      console.log('Owner')
    }
  }, {
    label: 'Paid',
    click: () => {
      console.log('Member')
    }
  }]
]

const Free = [
  [{
    label: 'UnSubscribe',
    click: () => {
      console.log('Remove')
      isOpenUnSubscribe.value = true
    }
  }]
]

const Paid = [
  [{
    label: 'Subscribe ',
    click: () => {
      console.log('Change Role');
      isOpenSubscribe.value = true
    }
  },
  {
    label: 'UnSubscribe',
    click: () => {
      console.log('Remove')
      isOpenUnSubscribe.value = true
    }
  }]
]

</script>
