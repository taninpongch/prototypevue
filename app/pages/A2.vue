<template>
  <UDashboardPanel v-if="showSidebar" grow>
    <UDashboardNavbar title="Home">

    </UDashboardNavbar>
    <UDashboardPanelContent>

      <label class="font-semibold text-4xl"> ยินดีต้อนรับสู่ CA</label>
      <UAvatar icon="i-heroicons-building-storefront-20-solid"
        :ui="{ rounded: 'rounded-none', size: { '3xl': 'w-full  h-full' } }" size="3xl" />
    </UDashboardPanelContent>
  </UDashboardPanel>
</template>

<script lang="ts" setup>
const showSidebar = ref(true) // You can set this value to false to hide the sidebar

</script>