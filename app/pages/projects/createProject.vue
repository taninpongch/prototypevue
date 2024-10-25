<template>
  <UDashboardPanel grow>
    <UDashboardNavbar title="Da Name">
    </UDashboardNavbar>

    <UContainer class="'bg-white dark:bg-gray-900 space-y-4' : 'space-y-4'"
      :ui="{ base: '', padding: 'p-4 sm:p-4 lg:p-4', constrained: '' }">
      <UCard :ui="{ body: { base: 'space-y-4', padding: 'px-4 py-4 sm:p-4' } }">

        <UFormGroup label="Project info">
        </UFormGroup>

        <UCard :ui="{ body: { base: 'space-y-4', padding: 'px-4 py-4 sm:p-4' } }">

          <UFormGroup label="Name">
            <UInput placeholder="กรุณากรอกชื่อ Project" 
              :ui="{ base: 'disabled:bg-gray-200 dark:disabled:bg-black' }" />
          </UFormGroup>

          <UFormGroup label="Description">
            <UInput placeholder="กรุณากรอกคำอธิบาย Project"
              :ui="{ base: 'disabled:bg-gray-200 dark:disabled:bg-black' }" />
          </UFormGroup>    
        </UCard>
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
