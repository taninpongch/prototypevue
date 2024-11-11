<template>
  <UDashboardPanel grow>
    <UDashboardNavbar title="TheS">
    </UDashboardNavbar>

    <UContainer class="'bg-white dark:bg-gray-900 space-y-4' : 'space-y-4'"
      :ui="{ base: '', padding: 'p-4 sm:p-4 lg:p-4', constrained: '' }">

      <UFormGroup size="xl" label="Personal info">
      </UFormGroup>

      <UCard :ui="{ body: { base: 'space-y-4', padding: 'px-4 py-4 sm:p-4' } }">

        <UFormGroup label="Tel">
          <UInput placeholder="เช่น 0123456789" type="number"
            :ui="{ base: 'disabled:bg-gray-200 dark:disabled:bg-black' }" />
        </UFormGroup>

        <UFormGroup label="MRID.">
          <UInput placeholder="เช่น 1234567" type="number"
            :ui="{ base: 'disabled:bg-gray-200 dark:disabled:bg-black' }" />
        </UFormGroup>

        <div class="flex flex-wrap items-center gap-4" v-bind:class="{ 'justify-end': 'justify-between' }">
          <div class="flex flex-wrap items-center gap-4">
            <p class="text-green-500">ข้อมูลถูกต้อง</p>
            <p class="text-red-600">ข้อมูลไม่ถูกต้อง</p>
            <UButton :loading="true" label="Verify" color="green" />
          </div>
        </div>

        <UDivider />

        <UFormGroup label="Work info">
        </UFormGroup>
        <UFormGroup label="Role">
          <USelect placeholder="ระบุตำแหน่งที่ต้องการเลือก" :options="bind_select" option-attribute="name"
            :ui="{ base: 'disabled:bg-gray-200 dark:disabled:bg-black' }" />
        </UFormGroup>
      </UCard>

      <div class="flex flex-wrap items-center gap-4 pt-4" v-bind:class="{ 'justify-end': 'justify-between' }">
        <div class="flex flex-wrap items-center gap-4">
          <UButton label="ยกเลิก" color="red" @click="navigate()" />
          <UButton label="ตกลง" color="green" @click="navigate()" />
        </div>
      </div>
    </UContainer>

  </UDashboardPanel>
</template>

<script setup lang="ts">

const navigate = () => {
  navigateTo('main')
}


const bind_select = ref([{
  name: 'Member', value: 'Member'
}, {
  name: 'Owner', value: 'Owner'
}]);

</script>
