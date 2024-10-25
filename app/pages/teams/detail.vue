<template>
  <UDashboardPanel grow>
    <UDashboardNavbar title="The-S">
    </UDashboardNavbar>

    <!-- <TODO: content> -->
    <UContainer class="'bg-white dark:bg-gray-900 space-y-4' : 'space-y-4'"
      :ui="{ base: '', padding: 'p-4 sm:p-4 lg:p-4', constrained: '' }">
      <p class="py-4 ">The-S-Dev</p>
      <UCard :ui="{ body: { base: 'space-y-4', padding: 'px-4 py-4 sm:p-4' } }">
        <div class="flex items-center justify-center">
          <UButtonGroup size="sm" orientation="horizontal">
            <UInput />
            <UButton icon="i-ion-md-search" color="gray" />
          </UButtonGroup>
          <UAlert variant="soft" :closeButton="{ label: 'Add a member', variant: 'solid', to: 'addMemberToTeam' }" />
        </div>

        <li class="flex items-center justify-between gap-3 py-3 px-4 sm:px-6">
          <div class="flex items-center gap-3 min-w-0">
            <div class="">
              <UCheckbox />
            </div>
            <div class="text-sm min-w-0">
              <p class="text-gray-900 dark:text-white font-medium truncate">Select all ( 2 member )</p>
            </div>
          </div>
          <div class="flex items-center gap-3">
            <div class="relative">
              <div id="headlessui-listbox-button-v-0-22-0" aria-haspopup="listbox" aria-expanded="false"
                data-headlessui-state="" role="button" class="flex items-center w-full"><button
                  class="relative w-full disabled:cursor-not-allowed disabled:opacity-75 focus:outline-none border-0 inline-flex items-center text-left cursor-default capitalize rounded-md text-sm gap-x-1.5 px-2.5 py-1.5 shadow-sm bg-white dark:bg-gray-900 text-gray-900 dark:text-white ring-1 ring-inset ring-gray-300 dark:ring-gray-700 focus:ring-2 focus:ring-primary-500 dark:focus:ring-primary-400 pe-9"
                  type="button">
                  <span class="block truncate">Role</span>
                  <span class="absolute inset-y-0 end-0 flex items-center pointer-events-none px-2.5">
                    <UIcon name="i-ion:chevron-down-sharp" />
                  </span>
                </button>
              </div>
            </div>
          </div>
        </li>
        <UDivider />
        <ul class="divide-y divide-gray-200 dark:divide-gray-800">

          <li class="flex items-center justify-between gap-3 py-3 px-4 sm:px-6">
            <div class="flex items-center gap-3 min-w-0">
              <div class="">
                <UCheckbox />
              </div>
              <div class="text-sm min-w-0">
                <p class="text-gray-900 dark:text-white font-medium truncate">Aurora</p>
                <p class="text-gray-900 dark:text-white font-medium truncate">Owner</p>
              </div>
            </div>
            <div class="flex items-center gap-3">  
              <div class="relative">
                <UButton color="red" label="Leave team" />
              </div>         
              <div data-headlessui-state="" class="relative inline-flex text-left rtl:text-right" position="bottom-end">
                <div disabled="false" id="headlessui-menu-button-v-0-58-1" aria-haspopup="menu" aria-expanded="false"
                  data-headlessui-state="" class="inline-flex w-full" role="button">
                  <button type="button"
                    class="focus:outline-none focus-visible:outline-0 disabled:cursor-not-allowed disabled:opacity-75 aria-disabled:cursor-not-allowed aria-disabled:opacity-75 flex-shrink-0 font-medium rounded-md text-sm gap-x-1.5 p-1.5 text-gray-700 dark:text-gray-200 hover:text-gray-900 dark:hover:text-white hover:bg-gray-50 dark:hover:bg-gray-800 focus-visible:ring-inset focus-visible:ring-2 focus-visible:ring-primary-500 dark:focus-visible:ring-primary-400 inline-flex items-center">
                    <span>
                      <UIcon name="i-ion-ellipsis-vertical" />
                    </span>
                  </button>
                </div>
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
                <p class="text-gray-900 dark:text-white font-medium truncate">member</p>
              </div>
            </div>
            <div class="flex items-center gap-3">           
              <div data-headlessui-state="" class="relative inline-flex text-left rtl:text-right" position="bottom-end">
                <div disabled="false" id="headlessui-menu-button-v-0-58-1" aria-haspopup="menu" aria-expanded="false"
                  data-headlessui-state="" class="inline-flex w-full" role="button">
                  <button type="button"
                    class="focus:outline-none focus-visible:outline-0 disabled:cursor-not-allowed disabled:opacity-75 aria-disabled:cursor-not-allowed aria-disabled:opacity-75 flex-shrink-0 font-medium rounded-md text-sm gap-x-1.5 p-1.5 text-gray-700 dark:text-gray-200 hover:text-gray-900 dark:hover:text-white hover:bg-gray-50 dark:hover:bg-gray-800 focus-visible:ring-inset focus-visible:ring-2 focus-visible:ring-primary-500 dark:focus-visible:ring-primary-400 inline-flex items-center">
                    <span>
                      <UIcon name="i-ion-ellipsis-vertical" />
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

</script>
