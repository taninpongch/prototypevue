<template>
  <UDashboardPanel grow>
    <UDashboardNavbar title="Topup">
    </UDashboardNavbar>


    <UCard class="h-screen">
      <UFormGroup class="m-2" label="เติมเงินจำนวนเท่าไหร่">
        <UInput placeholder="ขั้นต่ำ 1 บาท สูงสุด 2ล้านบาท" type="number" inputMode="number"
          :ui="{ base: 'disabled:bg-gray-200 dark:disabled:bg-black' }" />
      </UFormGroup>
      <UButton block :ui="{ rounded: 'rounded-full' }" @click="navigate">สร้าง QR เติมเงิน</UButton>
    </UCard>
  </UDashboardPanel>

</template>

<script setup lang="ts">
const navigate = () => {
  navigateTo('/A4')
}

</script>
