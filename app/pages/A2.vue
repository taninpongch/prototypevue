<template>
  <UDashboardPanel v-if="showSidebar" grow>
    <UDashboardNavbar title="Home">

    </UDashboardNavbar>
    <UDashboardPanelContent>

      <label class="font-semibold text-4xl"> ยินดีต้อนรับสู่ CA</label>
      <UAvatar src="https://fv5-2.files.fm/thumb.php?i=37hxqdee37&v=1&n=BA-web-test-banner.png"
        :ui="{ rounded: 'rounded-none', size: { '3xl': 'w-full  h-full' } }" size="3xl" />
    </UDashboardPanelContent>
  </UDashboardPanel>
</template>

<script lang="ts" setup>
const showSidebar = ref(true) // You can set this value to false to hide the sidebar

</script>