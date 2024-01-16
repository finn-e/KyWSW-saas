<script setup lang="ts">
import type { NavItem } from '@nuxt/content/dist/runtime/types';

const navigation = inject<Ref<NavItem[]>>('navigation', ref([]))

const links = [{
  label: 'Sampling',
  to: '/docs'
}, {
  label: 'Donations',
  to: '/donations'
}, {
  label: 'Blog',
  to: '/blog'
}]
</script>

<template>
  <UHeader :links="links">
    <template #logo>
      KyWSW <UBadge label="Kentucky Watershed Watch" variant="subtle" class="mb-0.5" />
    </template>

    <template #right>
      <UButton label="Log in" color="gray" to="/login" />
      <UButton label="Sign up" icon="i-heroicons-arrow-right-20-solid" trailing color="black" to="/signup" class="hidden lg:flex" />
    </template>

    <template #panel>
      <UNavigationTree :links="mapContentNavigation(navigation)" default-open />
    </template>
  </UHeader>
</template>
