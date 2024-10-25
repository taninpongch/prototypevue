<template>
  <UDashboardPanel grow>
    <UDashboardNavbar title="Topup">
    </UDashboardNavbar>

    <UDashboardPanelContent>
      <UCard class="h-screen">
        <UFormGroup class="m-2" label="เติมเงินจำนวนเท่าไหร่">
          <UInput placeholder="ขั้นต่ำ 1 บาท สูงสุด 2ล้านบาท" type="number" inputMode="number"
            :ui="{ base: 'disabled:bg-gray-200 dark:disabled:bg-black' }" class=" lg:min-w-min  " />
        </UFormGroup>
        <UButton :ui="{ rounded: 'rounded-full' }" @click="navigate" icon="i-heroicons-qr-code-20-solid">สร้าง QR
          เติมเงิน</UButton>
      </UCard>
    </UDashboardPanelContent>
  </UDashboardPanel>
</template>

<script setup lang="ts">
const navigate = () => {
  navigateTo('/A4')
}

</script>
