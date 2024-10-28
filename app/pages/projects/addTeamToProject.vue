<template>
  <UDashboardPanel grow>
    <UDashboardNavbar title="DA Name">
    </UDashboardNavbar>


    <UHorizontalNavigation :links="links" class="border-b border-gray-200 dark:border-gray-800" />

    <!-- <TODO: content> -->
    <UContainer class="'bg-white dark:bg-gray-900 space-y-4' : 'space-y-4'"
      :ui="{ base: '', padding: 'p-4 sm:p-4 lg:p-4', constrained: '' }">
      <p class="py-4 ">Project: Delivery</p>
      <!-- <p class="py-4 ">Add people/teams to Project </p> -->
      <UCard :ui="{ body: { base: 'space-y-4', padding: 'px-4 py-4 sm:p-4' } }">


        <div class="">
          <div>
            <div class="flex justify-end items-end gap-4 pt-4">
              <UButton class="flex items-center justify-end" label="Add people" color="green"
                @click="dlgPeople = true" />
              <UButton class="flex items-center justify-end" label="Add team" color="green" @click="isOpen = true" />
            </div>
            <UButtonGroup size="sm" orientation="horizontal">
              <UInput />
              <UButton icon="i-ion-md-search" color="gray" />
            </UButtonGroup>
          </div>
        </div>

        <!-- <li class="flex items-center justify-between gap-3 py-3 px-4 sm:px-6">
          <div class="flex items-center gap-3 min-w-0">
            <div class="text-sm min-w-0">
              <p class="text-gray-900 dark:text-white font-medium truncate">3 Collabolators</p>
            </div>
          </div>
        </li> -->

        <li class="flex items-center justify-between gap-3 py-3 px-4 sm:px-6">
          <div class="flex items-center gap-3 min-w-0">
            <!-- <div class="">
              <UCheckbox />
            </div> -->
            <div class="text-sm min-w-0">
              <p class="text-gray-900 dark:text-white font-medium truncate">3 Collabolators</p>
            </div>
          </div>
          <div class="flex items-center gap-3">
            <div class="relative">
              <UDropdown :items="fliter" :popper="{ placement: 'bottom-start' }">
                <UButton label="Collabolators" color="white" trailing-icon="i-ion-chevron-down-sharp" />
              </UDropdown>
            </div>
          </div>
        </li>


        <!-- 
        <div class="flex items-center">
          <div class="">
            <UButtonGroup size="sm" orientation="horizontal">
              <UInput />
              <UButton icon="i-ion-md-search" color="gray" />
            </UButtonGroup>

            <li class="flex items-center justify-between gap-3 py-3 px-4 sm:px-6">
              <div class="flex items-center gap-3 min-w-0">
                <div class="text-sm min-w-0">
                  <p class="text-gray-900 dark:text-white font-medium truncate">3 Collabolators</p>
                </div>
              </div>
            </li>
          </div> -->

        <UModal v-model="isOpen">
          <UCard :ui="{ ring: '', divide: 'divide-y divide  -gray-100 dark:divide-gray-800' }">
            <template #header>
              <p class="py-2">Add teams to Project (Delivery)</p>

            </template>

            <li class="flex items-center justify-between gap-3 py-3 px-4 sm:px-6">
              <div class="flex items-center gap-3 min-w-0">
                <div class="">
                  <UCheckbox />
                </div>
                <div class="text-sm min-w-0">
                  <p class="text-gray-900 dark:text-white font-medium truncate">The-S-Dev</p>
                </div>
              </div>
              <div class="flex items-center gap-3">
                <div class="relative">
                  <p class="text-gray-900 dark:text-white font-medium truncate">15 members</p>
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
                <div class="">
                  <UCheckbox />
                </div>
                <div class="text-sm min-w-0">
                  <p class="text-gray-900 dark:text-white font-medium truncate">The-S-Highclass</p>
                </div>
              </div>
              <div class="flex items-center gap-3">
                <div class="relative">
                  <p class="text-gray-900 dark:text-white font-medium truncate">11 members</p>
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
                <div class="">
                  <UCheckbox />
                </div>
                <div class="text-sm min-w-0">
                  <p class="text-gray-900 dark:text-white font-medium truncate">The-S-Firstclass</p>
                </div>
              </div>
              <div class="flex items-center gap-3">
                <div class="relative">
                  <p class="text-gray-900 dark:text-white font-medium truncate">4 members</p>
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
            <!-- <UAlert title="The-S-Dev" icon="i-ion-ios-people" variant="solid"
                :closeButton="{ icon: 'i-heroicons-x-mark-20-solid', variant: 'soft', color: 'white' }" />
              <UAlert title="The-S-Gp" icon="i-ion-ios-people" variant="solid"
                :closeButton="{ icon: 'i-heroicons-x-mark-20-solid', variant: 'soft', color: 'white' }" /> -->


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

        <UModal v-model="dlgPeople">
          <UCard :ui="{ ring: '', divide: 'divide-y divide  -gray-100 dark:divide-gray-800' }">
            <template #header>
              <p class="py-2">Add people to Project (Delivery)</p>

              <!-- <UAlert title="The-S-Dev" icon="i-ion-ios-people" variant="solid"
                :closeButton="{ icon: 'i-heroicons-x-mark-20-solid', variant: 'soft', color: 'white' }" />
              <UAlert title="The-S-Gp" icon="i-ion-ios-people" variant="solid"
                :closeButton="{ icon: 'i-heroicons-x-mark-20-solid', variant: 'soft', color: 'white' }" /> -->
              <UButtonGroup size="sm" orientation="horizontal">
                <UInput />
                <UButton icon="i-ion-md-search" color="gray" />
              </UButtonGroup>
            </template>

            <li class="flex items-center justify-between gap-3 py-3 px-4 sm:px-6">
              <div class="flex items-center gap-3 min-w-0">
                <div class="">
                  <UCheckbox />
                </div>
                <div class="text-sm min-w-0">
                  <p class="text-gray-900 dark:text-white font-medium truncate">Buttree</p>
                </div>
              </div>
              <div class="flex items-center gap-3">
                <div class="relative">
                  <p class="text-gray-900 dark:text-white font-medium truncate">Member</p>
                </div>
              </div>
            </li>

            <li class="flex items-center justify-between gap-3 py-3 px-4 sm:px-6">
              <div class="flex items-center gap-3 min-w-0">
                <div class="">
                  <UCheckbox />
                </div>
                <div class="text-sm min-w-0">
                  <p class="text-gray-900 dark:text-white font-medium truncate">Tachapong</p>
                </div>
              </div>
              <div class="flex items-center gap-3">
                <div class="relative">
                  <p class="text-gray-900 dark:text-white font-medium truncate">Member</p>
                </div>
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

        <UModal v-model="isOpenRemove">
          <UCard :ui="{ ring: '', divide: 'divide-y divide  -gray-100 dark:divide-gray-800' }">
            <template #header>
              <p class="py-2 text-center">Removing 1 Collabolator</p>
            </template>
            <p>The following collabolator will be removed:</p>
            <UAlert title="The-S-GP" icon="i-ion-people-sharp" variant="solid" />
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

        <!-- <UFormGroup label="Add teams to Project (Delivery)">
        </UFormGroup> -->

        <UDivider />
        <ul class="divide-y divide-gray-200 dark:divide-gray-800">

          <li class="flex items-center justify-between gap-3 py-3 px-4 sm:px-6">
            <div class="flex items-center gap-3 min-w-0">
              <!-- <div class="">
                <UCheckbox />
              </div> -->
              <div class="text-sm min-w-0">
                <p class="text-gray-900 dark:text-white font-medium truncate">The-S-Dev</p>
                <p class="text-gray-400 dark:text-white font-medium truncate">ทีม Dev ผู้กล้าหาญ จับกระบี่กวัดแกว่งกวาดล้างผญามาญ</p>
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
            <div class="flex items-center gap-3 min-w-0">
              <!-- <div class="">
                <UCheckbox />
              </div> -->
              <div class="text-sm min-w-0">
                <p class="text-gray-900 dark:text-white font-medium truncate">The-S-Firstclass</p>
                <p class="text-gray-400 dark:text-white font-medium truncate">ทีม Dev ตัวเล็กตัวน้อย</p>
              </div>
            </div>
            <div class="flex items-center gap-3">
              <div class="relative">
                <p class="text-gray-900 dark:text-white font-medium truncate">4 members</p>
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
            <div class="flex items-center gap-3 min-w-0">
              <!-- <div class="">
                <UCheckbox />
              </div> -->
              <div class="text-sm min-w-0">
                <p class="text-gray-900 dark:text-white font-medium truncate">Buttree</p>
                <p class="text-gray-900 dark:text-white font-medium truncate"></p>
              </div>
            </div>
            <div class="flex items-center gap-3">
              <div class="relative">
                <p class="text-gray-900 dark:text-white font-medium truncate"></p>
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
      </UCard>

    </UContainer>

  </UDashboardPanel>
</template>

<script setup lang="ts">
const isOpen = ref(false)
const dlgPeople = ref(false)
const isOpenRemove = ref(false)

const navigate = () => {
  navigateTo('detail')
}

const navigateCreateTeam = () => {
  navigateTo('../teams/createteam')
}

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

const items = [
  [{
    label: 'Remove',
    click: () => {
      console.log('Remove')
      isOpenRemove.value = true
    }
  }]
]

const fliter = [
  [{
    label: 'All',
    click: () => {
      console.log('All');
    }
  },
  {
    label: 'teams',
    click: () => {
      console.log('teams')
    }
  }, {
    label: 'people',
    click: () => {
      console.log('people')
    }
  }]
]

</script>
