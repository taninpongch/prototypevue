<template>
  <UDashboardPanel grow>
    <UDashboardNavbar title="DA NAME">
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
            <div class="">
              <UCheckbox />
            </div>
            <div class="text-sm min-w-0">
              <p class="text-gray-900 dark:text-white font-medium truncate">2 member</p>
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
              <span
                class="relative inline-flex items-center justify-center flex-shrink-0 rounded-full h-10 w-10 text-base">
                <img class="rounded-full h-10 w-10 text-base"
                  src="https://ipx.nuxt.com/f_auto,s_192x192/gh_avatar/antfu">
              </span>
              <div class="text-sm min-w-0">
                <p class="text-gray-900 dark:text-white font-medium truncate">aurora</p>
              </div>
            </div>
            <div class="flex items-center gap-3">
              <div class="relative">
                <div @click="xxx()" id="headlessui-listbox-button-v-0-22-0" aria-haspopup="listbox" aria-expanded="false"
                  data-headlessui-state="" role="button" class="flex items-center w-full"><button
                    class="relative w-full disabled:cursor-not-allowed disabled:opacity-75 focus:outline-none border-0 inline-flex items-center text-left cursor-default capitalize rounded-md text-sm gap-x-1.5 px-2.5 py-1.5 shadow-sm bg-white dark:bg-gray-900 text-gray-900 dark:text-white ring-1 ring-inset ring-gray-300 dark:ring-gray-700 focus:ring-2 focus:ring-primary-500 dark:focus:ring-primary-400 pe-9"
                    type="button">
                    <span class="block truncate">Owner</span>
                    <span class="absolute inset-y-0 end-0 flex items-center pointer-events-none px-2.5">
                      <UIcon name="i-ion:chevron-down-sharp" />
                    </span>
                  </button>
                </div>
                <div v-if="isShow" class="z-20 group w-full"
                  style="position: absolute; inset: 0px 0px auto auto; margin: 0px; transform: translate3d(-0.5px, 40px, 0px);"
                  data-popper-placement="bottom-end">
                  <div @click="yyy()" class=""><!---->
                    <ul id="headlessui-listbox-options-v-0-23-27" aria-labelledby="headlessui-listbox-button-v-0-23-2"
                      aria-orientation="vertical" role="listbox" tabindex="0" data-headlessui-state="open"
                      class="relative focus:outline-none overflow-y-auto scroll-py-1 ring-1 ring-gray-200 dark:ring-gray-700 rounded-md shadow-lg bg-white dark:bg-gray-800 p-1 max-h-60"
                      aria-activedescendant="headlessui-listbox-option-v-0-23-29"><!---->
                      <li
                        class="cursor-default select-none relative flex items-center justify-between gap-1 capitalize rounded-md px-1.5 py-1.5 text-sm text-gray-900 dark:text-white"
                        id="headlessui-listbox-option-v-0-23-28" role="option" tabindex="-1" aria-selected="false"
                        data-headlessui-state="">
                        <div class="flex items-center gap-1.5 min-w-0"><!----><span class="truncate">member</span></div>
                        <!---->
                      </li>
                      <li
                        class="cursor-default select-none relative flex items-center justify-between gap-1 capitalize rounded-md px-1.5 py-1.5 text-sm text-gray-900 dark:text-white bg-gray-100 dark:bg-gray-900 pe-7"
                        id="headlessui-listbox-option-v-0-23-29" role="option" tabindex="-1" aria-selected="true"
                        data-headlessui-state="active selected">
                        <div class="flex items-center gap-1.5 min-w-0"><!----><span class="truncate">owner</span></div>
                        <span class="absolute inset-y-0 end-0 flex items-center pe-2"><span
                            class="iconify i-heroicons:check-20-solid h-5 w-5 text-gray-900 dark:text-white flex-shrink-0"
                            aria-hidden="true"></span></span>
                      </li><!---->
                    </ul>
                  </div>
                </div>
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
              <span
                class="relative inline-flex items-center justify-center flex-shrink-0 rounded-full h-10 w-10 text-base">
                <img class="rounded-full h-10 w-10 text-base"
                  src="https://ipx.nuxt.com/f_auto,s_192x192/gh_avatar/antfu">
              </span>
              <div class="text-sm min-w-0">
                <p class="text-gray-900 dark:text-white font-medium truncate">tatae999</p>
              </div>
            </div>
            <div class="flex items-center gap-3">
              <div class="relative">
                <div id="headlessui-listbox-button-v-0-22-0" aria-haspopup="listbox" aria-expanded="false"
                  data-headlessui-state="" role="button" class="flex items-center w-full"><button
                    class="relative w-full disabled:cursor-not-allowed disabled:opacity-75 focus:outline-none border-0 inline-flex items-center text-left cursor-default capitalize rounded-md text-sm gap-x-1.5 px-2.5 py-1.5 shadow-sm bg-white dark:bg-gray-900 text-gray-900 dark:text-white ring-1 ring-inset ring-gray-300 dark:ring-gray-700 focus:ring-2 focus:ring-primary-500 dark:focus:ring-primary-400 pe-9"
                    type="button">
                    <span class="block truncate">member</span>
                    <span class="absolute inset-y-0 end-0 flex items-center pointer-events-none px-2.5">
                      <UIcon name="i-ion:chevron-down-sharp" />
                    </span>
                  </button>
                </div>
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
          <li class="flex items-center bg-gray-100  justify-between gap-3 py-3 px-4 sm:px-6">
            <div class="flex items-center gap-3 min-w-0">
              <UCheckbox disabled />
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
                <div id="headlessui-listbox-button-v-0-22-0" aria-haspopup="listbox" aria-expanded="false"
                  data-headlessui-state="" role="button" class="flex items-center w-full">
                  <button disabled
                    class="relative w-full disabled:cursor-not-allowed disabled:opacity-75 focus:outline-none border-0 inline-flex items-center text-left cursor-default capitalize rounded-md text-sm gap-x-1.5 px-2.5 py-1.5 shadow-sm bg-white dark:bg-gray-900 text-gray-900 dark:text-white ring-1 ring-inset ring-gray-300 dark:ring-gray-700 focus:ring-2 focus:ring-primary-500 dark:focus:ring-primary-400 pe-9"
                    type="button">
                    <span class="block truncate">member</span>
                    <span class="absolute inset-y-0 end-0 flex items-center pointer-events-none px-2.5">
                      <UIcon name="i-ion:chevron-down-sharp" />
                    </span>
                  </button>
                </div>  
              </div>

              <div data-headlessui-state="" class="relative inline-flex text-left rtl:text-right" position="bottom-end">
                <div disabled="true" id="headlessui-menu-button-v-0-58-1" aria-haspopup="menu" aria-expanded="false"
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

      <div class="flex flex-wrap items-center gap-4 pt-4" v-bind:class="{ 'justify-end': 'justify-between' }">
        <div class="flex flex-wrap items-center gap-4">
          <UButton label="change role comfirm" color="green" @click="isOpen1 = true" />
          <UModal v-model="isOpen1">
            <UCard :ui="{ ring: '', divide: 'divide-y divide  -gray-100 dark:divide-gray-800' }">
              <template #header>
                <p class="py-2 text-center">comfirm change role</p>
              </template>

              <p class="py-2 font-semibold">assign maintainer role to</p>
              <div>
                <p>aurora</p>
                <p>maintainer1</p>
              </div>
              <p class="py-2 font-semibold">assign member role to</p>
              <p>membername1</p>
              <p>membername2</p>
              <p>membername3</p>
              <div>
              </div>

              <template #footer>
                <div class="flex flex-wrap items-center gap-4 pt-4" v-bind:class="{ 'justify-end': 'justify-between' }">
                  <div class="flex flex-wrap items-center gap-4">
                    <UButton label="Cancel" color="red" />
                    <UButton label="Add to team" color="green" />
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
const isOpen1 = ref(false)
const isShow = ref(false)

const xxx = () => {
  isShow.value = true
}

const yyy = () => {
  isShow.value = false

}

</script>
