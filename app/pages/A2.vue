<template>
  <UDashboardPanel v-if="showSidebar" grow>
    <UDashboardNavbar title="Home">

    </UDashboardNavbar>
    <p class="font-semibold"> ยินดีต้อนรับสู่ CA</p>
    <UAvatar src="https://www.cdc.gov/importation/media/images/2024/07/GettyImages-1445770180.jpg" size="4xl" />
  </UDashboardPanel>
</template>

<script lang="ts" setup>
const showSidebar = ref(true) // You can set this value to false to hide the sidebar

</script>