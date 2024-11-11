<template>
  <UDashboardPanel grow>
    <UDashboardNavbar title="TheS">
    </UDashboardNavbar>

    <!-- <TODO: content> -->
    <UContainer class="'bg-white dark:bg-gray-900 space-y-4' : 'space-y-4'"
      :ui="{ base: '', padding: 'p-4 sm:p-4 lg:p-4', constrained: '' }">
      <p class="py-4 ">Manage Access</p>
      <UCard :ui="{ body: { base: 'space-y-4', padding: 'px-4 py-4 sm:p-4' } }">
        <div class="flex items-center justify-center">
          <UButtonGroup size="sm" orientation="horizontal">
            <UInput />
            <UButton icon="i-ion-md-search" color="gray" />
          </UButtonGroup>
          <UAlert variant="soft" :closeButton="{ label: 'invite member', variant: 'solid', to: 'create' }" />
        </div>

        <li class="flex items-center justify-between gap-3 py-3 px-4 sm:px-6">
          <div class="flex items-center gap-3 min-w-0">
            <div class="text-sm min-w-0">
              <p class="text-gray-900 dark:text-white font-medium truncate">2 member</p>
            </div>
          </div>
          <div class="flex items-center gap-3">
            <div class="relative">
              <UDropdown :items="fliter" :popper="{ placement: 'bottom-start' }">
                <UButton label="Role" color="white" trailing-icon="i-ion-chevron-down-sharp" />
              </UDropdown>
            </div>
            <UButton :padded="false" color="gray" variant="link" icon="ion-information-circle-outline"
              @click="isOpenRoleInfo = true" />
          </div>
        </li>
        <UDivider />
        <ul class="divide-y divide-gray-200 dark:divide-gray-800">

          <li class="flex items-center justify-between gap-3 py-3 px-4 sm:px-6">
            <div class="flex items-center gap-3 min-w-0">
              <!-- <div class="">
                <UCheckbox />
              </div> -->
              <span
                class="relative inline-flex items-center justify-center flex-shrink-0 rounded-full h-10 w-10 text-base">
                <img class="rounded-full h-10 w-10 text-base"
                  src="https://ipx.nuxt.com/f_auto,s_192x192/gh_avatar/antfu">
              </span>
              <div class="text-sm min-w-0">
                <p class="text-gray-900 dark:text-white font-medium truncate">Teerachai</p>
              </div>
            </div>
            <div class="flex items-center gap-3">
              <div class="relative">
                <p>owner</p>
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
              <span
                class="relative inline-flex items-center justify-center flex-shrink-0 rounded-full h-10 w-10 text-base">
                <img class="rounded-full h-10 w-10 text-base"
                  src="https://ipx.nuxt.com/f_auto,s_192x192/gh_avatar/antfu">
              </span>
              <div class="text-sm min-w-0">
                <p class="text-gray-900 dark:text-white font-medium truncate">Buttree</p>
              </div>
            </div>
            <div class="flex items-center gap-3">
              <div class="relative">
                <p>member</p>
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
          <li class="flex items-center bg-gray-100  justify-between gap-3 py-3 px-4 sm:px-6">
            <div class="flex items-center gap-3 min-w-0">
              <!-- <UCheckbox disabled /> -->
              <span
                class="relative inline-flex items-center justify-center flex-shrink-0 rounded-full h-10 w-10 text-base">
                <img class="rounded-full h-10 w-10 text-base"
                  src="https://ipx.nuxt.com/f_auto,s_192x192/gh_avatar/antfu">
              </span>
              <div class="text-sm min-w-0">
                <p class="text-gray-900 dark:text-white font-medium truncate">มดงาน11</p>
              </div>
            </div>
            <div class="flex items-center gap-3">
              <div class="relative">
                <p>member</p>
              </div>
              <div data-headlessui-state="" class="relative inline-flex text-left rtl:text-right" position="bottom-end">
                <div disabled id="headlessui-menu-button-v-0-58-1" aria-haspopup="menu" aria-expanded="false"
                  data-headlessui-state="" class="inline-flex w-full" role="button">
                  <button type="button"
                    class="focus:outline-none focus-visible:outline-0 disabled:cursor-not-allowed disabled:opacity-75 aria-disabled:cursor-not-allowed aria-disabled:opacity-75 flex-shrink-0 font-medium rounded-md text-sm gap-x-1.5 p-1.5 text-gray-700 dark:text-gray-200 hover:text-gray-900 dark:hover:text-white hover:bg-gray-50 dark:hover:bg-gray-800 focus-visible:ring-inset focus-visible:ring-2 focus-visible:ring-primary-500 dark:focus-visible:ring-primary-400 inline-flex items-center">
                    <span>
                      <UDropdown disabled :items="items" :popper="{ placement: 'bottom-start' }">
                        <UButton disabled color="white" trailing-icon="i-ion:ellipsis-horizontal-sharp" />
                      </UDropdown>
                    </span>
                  </button>
                </div>
              </div>
            </div>
          </li>
        </ul>
      </UCard>

      <div>
        <UModal v-model="isOpenRemove">
          <UCard :ui="{ ring: '', divide: 'divide-y divide  -gray-100 dark:divide-gray-800' }">
            <template #header>
              <p class="py-2 text-center">Removing 1 member</p>
            </template>
            <p>The following members will be removed:</p>
            <UAlert title="Buttree" icon="i-ion-ios-person-outline" variant="solid" />
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

        <UModal v-model="isOpenChange">
          <UCard :ui="{ ring: '', divide: 'divide-y divide  -gray-100 dark:divide-gray-800' }">
            <template #header>
              <p class="py-2 text-center">Change the role</p>
            </template>

            <p class="py-2 font-semibold">Select a new role</p>
            <URadioGroup v-model="selected"
              :options="[{ value: 'owner', label: 'owner', help: 'discription owner' }, { value: 'member', label: 'member', help: 'discription member' }]">
            </URadioGroup>

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

        <UModal v-model="isOpenRoleInfo">
          <UCard :ui="{ ring: '', divide: 'divide-y divide  -gray-100 dark:divide-gray-800' }">
            <template #header>
              <p class="py-2 text-center">DevAccount roles</p>
            </template>

            <p class="py-2 font-semibold">Roles are used to grant access and permissions for teams and members.</p>
            <UAlert description="มีสิทธิในการจัดการสมาชิกในกลุ่ม จัดการ Clubs และเข้าใช้งาน Dev portal" title="Owner" />
            <UAlert description="มีสิทธิในการเข้าใช้งาน Dev portal" title="Member" />
            <template #footer>
              <div class="flex flex-wrap items-center gap-4 pt-4" v-bind:class="{ 'justify-end': 'justify-between' }">
                <div class="flex flex-wrap items-center gap-4">
                  <UButton label="Close" color="red" />
                  <!-- <UButton label="confirm" color="green" /> -->
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
const isOpenRoleInfo = ref(false)
const selected = ref('sms')

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
