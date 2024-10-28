<template>
  <UDashboardPanel grow>
    <UDashboardNavbar title="DA Name">
    </UDashboardNavbar>

    
    <!-- <TODO: content> -->
      <p class="py-4 "> Project > Delivery</p>
      <UHorizontalNavigation :links="links" class="border-b border-gray-200 dark:border-gray-800" />
      <UContainer class="'bg-white dark:bg-gray-900 space-y-4' : 'space-y-4'"
      :ui="{ base: '', padding: 'p-4 sm:p-4 lg:p-4', constrained: '' }">
      <UCard :ui="{ body: { base: 'space-y-4', padding: 'px-4 py-4 sm:p-4' } }">
        <!-- <div> -->
          <UFormGroup label="Project detail">
          </UFormGroup>
        <!-- </div> -->

          <UFormGroup label="Name">
            <UInput placeholder="Delivery" :ui="{ base: 'disabled:bg-gray-200 dark:disabled:bg-black' }" />
          </UFormGroup>

          <UFormGroup label="Description">
            <UInput placeholder="ออกแบบ Project มาเพื่อใช้สำหรับขนส่งอาหารให้ถึงมือผู้บริโภค" :ui="{ base: 'disabled:bg-gray-200 dark:disabled:bg-black' }" />
          </UFormGroup>
          <!-- </UCard> -->

          <div class="flex flex-wrap items-center gap-4" v-bind:class="{ 'justify-end': 'justify-between' }">
            <div class="flex flex-wrap items-center gap-4">
              <UButton label="บันทึก" color="green" />
            </div>
          </div>

        <UDivider />
        <UFormGroup label="API Usage">
          </UFormGroup>

          <p>XXXXXXXXX</p>
          <p>XXXXXXXXX</p>
          <p>XXXXXXXXX</p>
<!-- 
          <li  class="flex items-center justify-between gap-3 py-3 px-4 sm:px-6">
            <div class="flex items-center gap-3 min-w-0">
              <UIcon class="w-10 h-10" name="i-ion-ios-people" />
              <div class="text-sm min-w-0">
                <p class="text-gray-900 dark:text-white font-medium truncate">The-S-Dev</p>
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
                      <UIcon name="i-ion-ellipsis-vertical" />
                    </span>
                  </button>
                </div>
              </div>
            </div>
          </li> -->

        

      </UCard>

    </UContainer>

  </UDashboardPanel>
</template>

<script setup lang="ts">

const links = [
  [{
    label: 'Overview',
    icon: 'i-ion-md-home',
    to: '/projects/detail'
  }, {
    label: 'Member',
    icon: 'i-ion-people-sharp',
    to: '/projects/addTeamToProject'
  }]
]

const infos: any[] = [
  { label: "Name", value: "Delivery" },
  { label: "Description", value: "ออกแบบ Project มาเพื่อใช้สำหรับขนส่งอาหารให้ถึงมือผู้บริโภค" }
];

</script>
