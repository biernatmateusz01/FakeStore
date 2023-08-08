<template>
  <div
    class="sticky top-12 left-0 shadow-md w-full flex flex-col gap-4 items-start flex flex-col gap-4 items-start p-4"
  >
    <div v-for="(item, index) in filters" :key="index" class="flex gap-1">
      <input
        :id="'category-' + index"
        :value="item"
        type="radio"
        v-model="checkedFilters"
        @change="$emit('change-filter', checkedFilters)"
      />
      <label :for="'category-' + index">{{ item }}</label>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted, defineProps } from "vue";

let selectedCategories = ref([]);
const checkedFilters = ref([])

defineProps({
  filters: Array
})
</script>
