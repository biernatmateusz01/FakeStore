<template>
  <div class="flex flex-col rounded overflow-hidden shadow-md relative">
    <!-- <div class="h-4 w-4 absolute top-2 right-2 bg-white z-30"></div> -->
    <div class="flex flex-col h-full justify-between">
      <div class="pt-4 flex flex-col gap-2 p-3">
        <!-- <span class="text-center text-yellow-400">{{product}}</span> -->
        <div class="h-[300px]">
          <img :src="product.image" alt="" class="h-full object-cover block mx-auto" />
        </div>
        <span class="text-center font-bold text-xl truncate">{{ product.title }}</span>
        <span class="mt-3 text-sm text-center">
         {{product.description}}
        </span>
      </div>
      <div class="w-full flex mt-3">
        <div
          @click="$emit('buy-product', product)"
          class="w-1/2 py-4 bg-yellow-400 border-r hover:bg-yellow-500 cursor-pointer border-black p-1 flex items-center justify-center"
        >
          <svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke-width="1.5"
            stroke="currentColor"
            class="w-6 h-6"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M2.25 3h1.386c.51 0 .955.343 1.087.835l.383 1.437M7.5 14.25a3 3 0 00-3 3h15.75m-12.75-3h11.218c1.121-2.3 2.1-4.684 2.924-7.138a60.114 60.114 0 00-16.536-1.84M7.5 14.25L5.106 5.272M6 20.25a.75.75 0 11-1.5 0 .75.75 0 011.5 0zm12.75 0a.75.75 0 11-1.5 0 .75.75 0 011.5 0z"
            />
          </svg>
        </div>
        <div class="w-1/2 py-4 bg-yellow-400 p-1 flex items-center justify-center">
          price: {{ product.price }}
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
defineProps({
  product: Object
})
</script>
