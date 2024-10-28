<template>
  <UDashboardPanel grow>
    <UDashboardNavbar title="Sign Up Mana Dev Account">
    </UDashboardNavbar>
    <UContainer class="'bg-white dark:bg-gray-900 space-y-4' : 'space-y-4'"
      :ui="{ base: '', padding: 'p-4 sm:p-4 lg:p-4', constrained: '' }">
      <UCard :ui="{ body: { base: 'space-y-4', padding: 'px-4 py-4 sm:p-4' } }">
        <p>ขั้นตอนการ Sign Up</p>
        <p>1. load app mana</p>
        <p>2. ทำการสร้างร้าน BA</p>
        <p>3. ใช้ app mana สแกนเพื่อสร้าง Dev Account</p>


        <div class="text-center mx-auto">
          <p class="font-semibold">สแกน QR code เพื่อ sign up</p>
          <UAvatar :ui="{ rounded: '', size: '3xs' }"
            src="https://upload.wikimedia.org/wikipedia/commons/d/d0/QR_code_for_mobile_English_Wikipedia.svg"
            size="3xl" class="mx-auto mb-2" />
          <div>
            <ULink to="https://www.google.com/" active-class="text-primary"
              inactive-class="text-blue-500 dark:text-blue-400 hover:text-blue-700 dark:hover:text-blue-200">
              เปิด App mana
            </ULink>

          </div>
        </div>

      </UCard>
    </UContainer>
  </UDashboardPanel>
</template>

<script setup lang="ts">
definePageMeta({
  layout: 'login'
})
</script>