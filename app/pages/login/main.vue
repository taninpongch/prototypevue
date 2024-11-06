<template>
  <UDashboardPanel grow>
    <!-- <UDashboardNavbar title="Mana Dev Account"> -->
    <UHeader :links="links">
      <template #logo>
        <UAvatar size="sm" src="https://failfast.blob.core.windows.net/upload/Logo_manaForm.png" />
        Mana Dev Account
      </template>

      <template #right>
        <UButton label="Sign in" @click="navigatein()" />
        <UButton label="Sign up" color="green" @click="navigateup()" />
      </template>
    </UHeader>

    <ULandingSection>
      <ULandingHero id="overview" title="Supercharged GitHub experience"
        description="Work in real-time with your team on open-source and private repositories, all in one place. Working on GitHub issues and notifications has never been that fun."
        orientation="vertical"
        :links="[{ label: 'Continue with GitHub', icon: 'i-simple-icons-github', color: 'gray', size: 'lg' }]">
      </ULandingHero>
    </ULandingSection>


    <ULandingSection :ui="{ wrapper: 'p-0 sm:py-16' }" title="Download the app" description="Wherever you are">
      <UPageGrid id="downloadManaApp3" class="scroll-mt-[calc(var(--header-height)+140px+128px+96px)]">
        <ULandingCard v-for="(item, index) in downloadManaApp" :key="index" v-bind="item"
          :ui="{ icon: { base: 'bg-red-600' } }" />
      </UPageGrid>
    </ULandingSection>

    <ULandingSection id="faq2" title="Frequently Asked Questions"
      description="If you can't find what you're looking for, email our support team and if you're lucky someone will get back to you">
      <ULandingFAQ multiple :items="faqList"  />
    </ULandingSection>

    <!-- <ULandingSection id="faq2" title="Frequently Asked Questions" description="If you can't find what you're looking for, email our support team and if you're lucky someone will get back to you"
      class="scroll-mt-[var(--header-height)]">
      <ULandingFAQ multiple :items="faqList" :ui="{
        button: {
          label: 'font-semibold',
          trailingIcon: {
            base: 'w-6 h-6'
          }
        }
      }" class="max-w-4xl mx-auto" />
    </ULandingSection> -->

  </UDashboardPanel>
</template>


<script setup lang="ts">

// const navigation = inject<Ref<NavItem[]>>('navigation', ref([]))
const links = [{
  label: 'Overview',
  icon: 'i-heroicons-book-open',
  to: '#overview',
}, {
  label: 'Download the app',
  icon: 'i-heroicons-square-3-stack-3d',
  to: '#downloadManaApp3',
}, {
  label: 'FAQ',
  icon: 'i-heroicons-rocket-launch',
  to: '#faq2',
}];

const downloadManaApp = [{
  title: 'On iOS',
  description: 'Works with iPhone, iPad, and Apple Watch',
  icon: 'i-simple-icons-eslint'
}, {
  title: 'On Android',
  description: 'Stay connected across phones, tablets, and smart devices',
  icon: 'i-simple-icons-tailwindcss'
}];

const faqList = [{
  label: 'Do you have a free trial?',
  content: 'Ea est ex aliqua exercitation quis et cillum adipisicing sit tempor veniam incididunt labore.'
}, {
  label: 'Can I use Nuxt UI Pro for Open Source projects?',
  content: 'Et adipisicing do do do sunt irure proident consequat fugiat tempor occaecat commodo fugiat in proident.'
}, {
  label: 'What does “Unlimited minor & patch updates” include?',
  content: 'Dolor dolor consectetur tempor consectetur sint ut id ex quis voluptate dolore incididunt qui mollit.'
}, {
  label: 'Do you offer technical support?',
  content: 'Sint id sint incididunt culpa.'
}]

const navigatein = () => {
  navigateTo('signIn')
}

const navigateup = () => {
  navigateTo('signUp')
}


definePageMeta({
  layout: 'login'
})
</script>