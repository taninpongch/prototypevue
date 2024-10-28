<template>
  <UDashboardPanel grow>
    <UDashboardNavbar title="ดูบัญชี">
    </UDashboardNavbar>
    <UDashboardToolbar>
      <template #left>
        <USelectMenu v-model="selectedStatuses" icon="i-heroicons-check-circle" placeholder="Status" multiple
          :options="defaultStatuses" @change="onChange" />

      </template>
    </UDashboardToolbar>
    <UDashboardPanelContent>

      <UTable :rows="people2" v-model:sort="sort" :columns="defaultColumns" @change="console.log('xxx', selected)">
        <template #status-data="{ row }">
          <UBadge :label="row.status" :color="row.status === 'Success' ? 'green' : 'red'" variant="subtle"
            class="capitalize" />
        </template>
      </UTable>
    </UDashboardPanelContent>
  </UDashboardPanel>

</template>
<script lang="ts" setup>
const date = new Date();
const formatter = new Intl.DateTimeFormat('en-US', { day: '2-digit', month: '2-digit', year: 'numeric', hour: '2-digit', minute: '2-digit', second: '2-digit' });
// const people: any[] = [{
//   date: formattedTime,
//   reftransaction: 'TX00000001',
//   transaction: 'เติม',
//   amount: Math.ceil(Math.random() * 100000),
//   status: 'Success'
// }, {
//   date: formattedTime,
//   reftransaction: 'TX00000002',
//   transaction: 'เติม',
//   amount: Math.ceil(Math.random() * 100000),
//   status: 'Fail'
// }, {
//   date: formattedTime,
//   reftransaction: 'TX00000003',
//   transaction: 'ถอน',
//   amount: Math.ceil(Math.random() * 100000),
//   status: 'Fail'
// }, {
//   date: formattedTime,
//   reftransaction: 'TX00000004',
//   transaction: 'ถอน',
//   amount: Math.ceil(Math.random() * 100000),
//   status: 'Success'
// }];

const people = computed(() => {
  const data = []
  for (let i = 0; i < 4; i++) {
    const formattedTime = formatter.format(date.setHours(i + 1));
    data.push({
      date: formattedTime,
      reftransaction: `TX0000000${i + 1}`,
      transaction: i % 2 === 0 ? 'เติม' : 'ถอน',
      amount: Math.ceil(Math.random() * 100000),
      status: i % 2 === 0 ? 'Success' : 'Fail'
    })
  }
  return data
})

const defaultColumns = [{
  key: 'date',
  label: 'Date',
  sortable: true
}, {
  key: 'reftransaction',
  label: 'Reftransaction',
  sortable: true
}, {
  key: 'transaction',
  label: 'Transaction'
}, {
  key: 'amount',
  label: 'Amount'
}, {
  key: 'status',
  label: 'Status'
}]
const selected = ref<any>([]);
const selectedStatuses = ref([])
const selectedColumns = ref(defaultColumns)
// const columns = computed(() => defaultColumns.filter(column => selectedColumns.value.includes(column)))
const sort = ref({ column: 'date', direction: 'asc' as const })
const people2 = ref<any>(people.value);
const query = computed(() => ({ statuses: selectedStatuses.value, sort: sort.value.column }))




const defaultStatuses = people.value.reduce((acc, user) => {
  if (!acc.includes(user.status)) {
    acc.push(user.status)
  }
  return acc
}, [] as string[])

const onChange = () => {
  if (selectedStatuses.value.length == 0) {
    people2.value = people.value;
  } else {
    console.log("selectedStatuses", selectedStatuses.value);
    console.log(1);
    var data = [];
    if (selectedStatuses.value.length > 0) {
      for (let i = 0; i < people.value.length; i++) {
        if (selectedStatuses.value.includes(people.value[i].status)) {
          data.push(people.value[i]);
        }
      }
      people2.value = data;
    }
  }
}
</script>