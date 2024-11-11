<script setup lang="ts">
const route = useRoute()
const appConfig = useAppConfig()
const { isHelpSlideoverOpen } = useDashboard()

const footerLinks = [{
  label: 'Sign out',
  icon: 'ion-log-out-outline',
  to: '/login/main',
}]

// const groups = [{
//   key: 'links',
//   label: 'Go to',
//   commands: links.map(link => ({ ...link, shortcuts: link.tooltip?.shortcuts }))
// }, {
//   key: 'code',
//   label: 'Code',
//   commands: [{
//     id: 'source',
//     label: 'View page source',
//     icon: 'i-simple-icons-github',
//     click: () => {
//       window.open(`https://github.com/nuxt-ui-pro/dashboard/blob/main/pages${route.path === '/' ? '/index' : route.path}.vue`, '_blank')
//     }
//   }]
// }]

// const defaultColors = ref(['green', 'teal', 'cyan', 'sky', 'blue', 'indigo', 'violet'].map(color => ({ label: color, chip: color, click: () => appConfig.ui.primary = color })))
// const colors = computed(() => defaultColors.value.map(color => ({ ...color, active: appConfig.ui.primary === color.label })))
</script>

<template>
  <UDashboardLayout>
    <UDashboardPanel :width="250" :resizable="{ min: 200, max: 300 }" collapsible>
      <UDashboardNavbar class="!border-transparent" :ui="{ left: 'flex-1' }">

      </UDashboardNavbar>

      <UDashboardSidebar>
        <template #header>
          <div class="text-center mx-auto w-full ">
            <UAvatar class="mx-auto mb-2"
              src="https://static.vecteezy.com/system/resources/thumbnails/002/387/693/small_2x/user-profile-icon-free-vector.jpg"
              size="3xl"></UAvatar>
              <UserDropdown2 />
            <!-- <p class="font-semibold">Buttree</p>
            <p> #1411577</p> -->
          </div>
          <!-- <UDashboardSearchButton /> -->
        </template>

        <UDashboardSidebarLinks />

        <UDivider />

        <!-- <UDashboardSidebarLinks :links="[{ label: 'Colors', draggable: true, children: colors }]"
          @update:links="colors => defaultColors = colors" /> -->

        <div class="flex-1" />

        <UDashboardSidebarLinks :links="footerLinks" />

        <UDivider class="sticky bottom-0" />

        <template #footer>
          <!-- ~/components/UserDropdown.vue -->
          <!-- <UserDropdown /> -->
        </template>
      </UDashboardSidebar>
    </UDashboardPanel>

    <slot />

    <!-- ~/components/HelpSlideover.vue -->
    <HelpSlideover />
    <!-- ~/components/NotificationsSlideover.vue -->
    <NotificationsSlideover />

    <!-- <ClientOnly> -->
    <!-- <LazyUDashboardSearch :groups="groups" /> -->
    <!-- </ClientOnly> -->
  </UDashboardLayout>
</template>
