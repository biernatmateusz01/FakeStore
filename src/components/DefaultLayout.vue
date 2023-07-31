<template>
  <BaseNavbar />

  <div class="container block mx-auto py-6 px-2 xl:px-0">
    <div class="flex gap-4 flex-col xl:flex-row">
      <div class="w-full xl:w-1/5">
        <slot name="filters" />
      </div>
      <div class="w-full xl:flex-1">
        <slot name="elements" />
      </div>
    </div>
  </div>
  <BaseFooter />
</template>

<script setup>
import BaseNavbar from '../components/BaseNavbar.vue'
import BaseFooter from '../components/BaseFooter.vue'
import BaseFilters from '../components/BaseFilters.vue'
</script>
