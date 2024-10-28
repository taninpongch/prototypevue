<script setup lang="ts">
const items = computed(() => [
  [{
    slot: 'account',
    label: '',
    disabled: true
  }], [{
    label: 'Home',
    icon: 'i-ion-home-outline',
    click: () => {
      navigateTo('')
    }
  }, {
    label: 'Dev account',
    icon: 'i-heroicons-building-storefront',
    click: () => {
      navigateTo('/organization/main')
    }
  }, {
    label: '',
    icon: '',
  }]
])
</script>

<template>
  <UDropdown mode="hover" :items="items" :ui="{ width: 'w-full', item: { disabled: 'cursor-text select-text' } }"
    :popper="{ strategy: 'absolute', placement: 'top' }" class="w-full">
    <!-- <template #default="{ open }">
        <UButton color="gray" variant="ghost" class="w-full" label="Benjamin"
        :class="[open && 'bg-gray-50 dark:bg-gray-800']">
        <template #leading>
          <UAvatar src="https://avatars.githubusercontent.com/u/739984?v=4" size="2xs" />
        </template>
        
        <template #trailing>
          <UIcon name="i-ion-home-outline" class="w-5 h-5 ml-auto" />
        </template>
      </UButton>
    </template> -->

    <template #default="{ open }">
        <UButton block color="gray" variant="ghost" class="w-full" label="Buttree " size="xl"
        :class="[open && 'bg-gray-50 dark:bg-gray-800']">
      </UButton>
    </template>

    <template #account>
      <div class="text-left">
        <p class="truncate font-medium text-gray-900 dark:text-white">
          Buttree
        </p>
        <p class="truncate font-medium text-gray-900 dark:text-white">
          #1411577
        </p>
      </div>
    </template>
  </UDropdown>
</template>
