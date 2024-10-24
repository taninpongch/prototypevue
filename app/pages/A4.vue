<template>
  <UDashboardPanel grow>
    <UDashboardNavbar title="Topup">
    </UDashboardNavbar>


    <UCard class="h-screen ">
      <div class="text-center mx-auto w-full ">
        <p class="font-semibold"> คิวอาร์โค้ดเติมเงิน</p>
        <p class="font-semibold"> รหัสอ้างอิง : 123456</p>
        <UAvatar class="mx-auto mb-2 "
          src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQEpxWQV3aLEcH8H6IKhAr3_WvERMBKHNFpZw&s" size="4xl">
        </UAvatar>
        <p class="font-semibold"> สแกน QR เพื่อเติมเงิน</p>
        <p class="font-semibold"> หมดอายุในอีก 30:00 นาที</p>
        <!-- <UCard class="bg-red-600  text-left w-full items-center border">
          <p class="font-semibold"> เงื่อนไขการใช้งาน</p>
          <p class="font-semibold"> • คิวอาร์โค้ดนี้ใช้ได้ครั้งเดียว</p>
          <p class="font-semibold"> • หลังจากสร้าง ต้องใช้ภายใน 30 นาทีเท่านั้น</p>

        </UCard> -->
        <UPricingGrid
          :ui="{ wrapper: 'text-left w-full md:grid-cols-1 lg:grid-cols-1 lg:grid lg:w-1/2 lg:h-1/2  mx-auto ' }"
          class="py-2">
          <!-- <UPricingCard title="เงื่อนไขการใช้งาน">
            <template #description class="">
              <p class="font-bold text-black"> • คิวอาร์โค้ดนี้ใช้ได้ครั้งเดียว</p>
              <p class="font-bold text-black"> • หลังจากสร้าง ต้องใช้ภายใน 30 นาทีเท่านั้น</p>
            </template>
</UPricingCard> -->
          <UCard class="text-center">
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
            <p class="font-bold text-black"> หมายเลขคำสั่ง : 123456</p>
            <p class="font-bold text-black text-4xl">เติมเงินสำเร็จ</p>
          </UCard>
        </UPricingGrid>


        <UButton block :ui="{ rounded: 'rounded-full' }" @click="topupfail">Topup Fail</UButton>
        <UPricingGrid v-if="fail"
          :ui="{ wrapper: 'text-left w-full md:grid-cols-1 lg:grid-cols-1 lg:grid lg:w-1/2 lg:h-1/2  mx-auto ' }"
          class="py-2">

          <UCard class="text-center">
            <p class="font-bold text-black"> หมายเลขคำสั่ง : 9876546</p>
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