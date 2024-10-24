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
  transaction: 'เติม',
  amount: Math.ceil(Math.random() * 100000),
  status: 'Success'
}, {
  Date: formattedTime,
  transaction: 'เติม',
  amount: Math.ceil(Math.random() * 100000),
  status: 'Fail'
}, {
  Date: formattedTime,
  transaction: 'ถอน',
  amount: Math.ceil(Math.random() * 100000),
  status: 'Fail'
}, {
  Date: formattedTime,
  transaction: 'ถอน',
  amount: Math.ceil(Math.random() * 100000),
  status: 'Done'
}]

</script>