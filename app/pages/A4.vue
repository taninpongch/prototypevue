<template>
  <UDashboardPanel grow>
    <UDashboardNavbar title="Topup">
    </UDashboardNavbar>

    <UDashboardPanelContent>
      <UCard class="h-screen scroll-auto">
        <div class="text-center mx-auto w-full ">
          <p class="font-semibold"> คิวอาร์โค้ดเติมเงิน</p>
          <p class="font-semibold"> รหัสอ้างอิง : 123456</p>
          <UAvatar class="mx-auto mb-2 " :ui="{ rounded: 'rounded-none', size: { '3xl': 'w-[300px]  h-[300px]' } }" size="3xl"
            src="https://fv5-3.files.fm/thumb_show.php?i=qe8c9k8368&view&v=1&PHPSESSID=526864e7f00bcd2edc8bfa15109161c46a3bb868">
          </UAvatar>
          <p class="font-semibold"> สแกน QR เพื่อเติมเงิน</p>
          <p class="font-semibold"> หมดอายุในอีก 30:00 นาที</p>
          <UPricingGrid
            :ui="{ wrapper: 'text-left w-full md:grid-cols-1 lg:grid-cols-1 lg:grid lg:w-1/2 lg:h-1/2  mx-auto ' }"
            class="py-2">
            <UCard class="text-center ">
              <p class="font-bold text-black text-xl">เงื่อนไขการใช้งาน</p>
              <p class="font-bold text-black"> • คิวอาร์โค้ดนี้ใช้ได้ครั้งเดียว</p>
              <p class="font-bold text-black"> • หลังจากสร้าง ต้องใช้ภายใน 30 นาทีเท่านั้น</p>
            </UCard>
          </UPricingGrid>

          <UButton class=" m-2" block :ui="{ rounded: 'rounded-full' }" @click="topupsucess">Topup Success</UButton>
          <UPricingGrid v-if="success"
            :ui="{ wrapper: 'text-left w-full md:grid-cols-1 lg:grid-cols-1 lg:grid lg:w-1/2 lg:h-1/2  mx-auto ' }"
            class="py-2">
            <UCard class="text-center">
              <p class="font-bold text-black "> หมายเลขคำสั่ง : 123456</p>

              <UAvatar icon="i-ion-ios-checkmark-circle-outline" size="3xl"
                :ui="{ background: 'bg-white', icon: { size: { '3xl': 'w-full  h-full' } } }" />

              <p class="font-bold text-black text-4xl">เติมเงินสำเร็จ</p>
            </UCard>
          </UPricingGrid>


          <UButton block :ui="{ rounded: 'rounded-full' }" @click="topupfail">Topup Fail</UButton>
          <UPricingGrid v-if="fail"
            :ui="{ wrapper: 'text-left w-full md:grid-cols-1 lg:grid-cols-1 lg:grid lg:w-1/2 lg:h-1/2  mx-auto ' }"
            class="py-2">

            <UCard class="text-center">
              <p class="font-bold text-black"> หมายเลขคำสั่ง : 9876546</p>
              <UAvatar icon="i-ion-ios-clock-outline" size="3xl"
                :ui="{ background: 'bg-white', icon: { size: { '3xl': 'w-full  h-full' } } }" />

              <p class="font-bold text-black text-4xl">QR หมดอายุ</p>
            </UCard>
          </UPricingGrid>

        </div>
        <!-- <UFormGroup class="m-2" label="คิวอาร์โค้ดเติมเงิน">
        <UInput placeholder="ขั้นต่ำ 1 บาท สูงสุด 2ล้านบาท" type="number" inputMode="number"
          :ui="{ base: 'disabled:bg-gray-200 dark:disabled:bg-black' }" />
      </UFormGroup>
      <UButton block :ui="{ rounded: 'rounded-full' }" @click="navigate">สร้าง QR เติมเงิน</UButton> -->
      </UCard>
    </UDashboardPanelContent>
  </UDashboardPanel>

</template>

<script setup lang="ts">
const success = ref(false);
const fail = ref(false);
const navigate = () => {
  navigateTo('/A4')
}

const topupsucess = () => {
  success.value = true;
}


const topupfail = () => {
  fail.value = true;
}


</script>