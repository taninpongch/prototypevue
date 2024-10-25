<template>
  <UDashboardPanel grow>
    <UDashboardNavbar title="ดูบัญชี">
    </UDashboardNavbar>
    <UTable :rows="people" />
  </UDashboardPanel>

</template>

<!-- format(date, 'd MMMM yyyy' -->
<script lang="ts" setup>
const date = new Date();
const formatter = new Intl.DateTimeFormat('en-US', { day: '2-digit', month: '2-digit', year: 'numeric', hour: '2-digit', minute: '2-digit', second: '2-digit' });
const formattedTime = formatter.format(date);
const people = [{
  Date: formattedTime,
  Reftransaction: 'TX00000001',
  transaction: 'เติม',
  amount: Math.ceil(Math.random() * 100000),
  status: 'Success'
}, {
  Date: formattedTime,
  Reftransaction: 'TX00000002',
  transaction: 'เติม',
  amount: Math.ceil(Math.random() * 100000),
  status: 'Fail'
}, {
  Date: formattedTime,
  Reftransaction: 'TX00000003',
  transaction: 'ถอน',
  amount: Math.ceil(Math.random() * 100000),
  status: 'Fail'
}, {
  Date: formattedTime,
  Reftransaction: 'TX00000004',
  transaction: 'ถอน',
  amount: Math.ceil(Math.random() * 100000),
  status: 'Done'
}]

</script>