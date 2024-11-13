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

        <div class="flex flex-wrap items-center gap-4">
          <div class="flex flex-wrap items-center gap-4">
            <UFormGroup label="Role">
            </UFormGroup>
            <UButton :padded="false" color="gray" variant="link" icon="ion-information-circle-outline"
              @click="isOpenRoleInfo = true" />
          </div>
        </div>

        <USelect placeholder="ระบุตำแหน่งที่ต้องการเลือก" :options="bind_select" option-attribute="name"
          :ui="{ base: 'disabled:bg-gray-200 dark:disabled:bg-black' }" />
      </UCard>

      <div class="flex flex-wrap items-center gap-4 pt-4" v-bind:class="{ 'justify-end': 'justify-between' }">
        <div class="flex flex-wrap items-center gap-4">
          <UButton label="ยกเลิก" color="red" @click="navigate()" />
          <UButton label="ตกลง" color="green" @click="navigate()" />
        </div>
      </div>

      <UModal v-model="isOpenRoleInfo">
        <UCard :ui="{ ring: '', divide: 'divide-y divide  -gray-100 dark:divide-gray-800' }">
          <template #header>
            <p class="py-2 text-center">Dev organization roles</p>
          </template>

          <p class="py-2 font-semibold">Roles are used to grant access and permissions for teams and members.</p>
          <UAlert description="มีสิทธิในการจัดการสมาชิกในกลุ่ม จัดการ Clubs และเข้าใช้งาน Dev portal" title="Owner" />
          <UAlert description="มีสิทธิในการเข้าใช้งาน Dev portal" title="Member" />
          <template #footer>
            <div class="flex flex-wrap items-center gap-4 pt-4" v-bind:class="{ 'justify-end': 'justify-between' }">
              <div class="flex flex-wrap items-center gap-4">
                <UButton label="Close" color="red" />
                <!-- <UButton label="confirm" color="green" /> -->
              </div>
            </div>
          </template>
        </UCard>
      </UModal>
    </UContainer>

  </UDashboardPanel>
</template>

<script setup lang="ts">

const navigate = () => {
  navigateTo('main')
}

const isOpenRoleInfo = ref(false)

const bind_select = ref([{
  name: 'Member', value: 'Member'
}, {
  name: 'Owner', value: 'Owner'
}]);

</script>
