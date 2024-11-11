<template>
  <UDashboardPanel grow>
    <UDashboardNavbar title="TheS">
    </UDashboardNavbar>

    <UContainer class="'bg-white dark:bg-gray-900 space-y-4' : 'space-y-4'"
      :ui="{ base: '', padding: 'p-4 sm:p-4 lg:p-4', constrained: '' }">

      <UFormGroup size="xl" label="Team info">
      </UFormGroup>

      <UCard :ui="{ body: { base: 'space-y-4', padding: 'px-4 py-4 sm:p-4' } }">

        <UFormGroup label="Name">
          <UInput placeholder="กรุณากรอกชื่อทีม" :ui="{ base: 'disabled:bg-gray-200 dark:disabled:bg-black' }" />
        </UFormGroup>

        <UFormGroup label="Description">
          <UInput placeholder="กรุณากรอกคำอธิบายทีม" :ui="{ base: 'disabled:bg-gray-200 dark:disabled:bg-black' }" />
        </UFormGroup>
      </UCard>

      <div class="flex flex-wrap items-center gap-4 pt-4" v-bind:class="{ 'justify-end': 'justify-between' }">
        <div class="flex flex-wrap items-center gap-4">
          <UButton label="ยกเลิก" color="red" @click="$router.back()" />
          <UButton label="ตกลง" color="green" @click="navigate()" />
        </div>
      </div>
    </UContainer>

  </UDashboardPanel>
</template>

<script setup lang="ts">

const navigate = () => {
  navigateTo('detail')
}

const bind_select = ref([{
  name: 'Member', value: 'Member'
}, {
  name: 'Owner', value: 'Owner'
}]);

</script>
