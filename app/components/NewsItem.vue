<template>
  <div
    v-if="item.urlToImage"
    class="p-2 rounded-xl shadow-md border border-gray-200"
  >
    <nuxt-link :to="item.url">
      <div class="flex flex-col h-full">
        <img
          :src="item.urlToImage"
          class="rounded-xl object-contain"
        >
        <h3 class="font-bold leading-5 mt-2">{{ item.title }}</h3>
        <p class="text-xs mt-1">{{ item.description }}</p>
        <p class="text-sm mt-auto"><span class="font-extrabold">Source:</span> {{ item.source.name }}</p>
      </div>
    </nuxt-link>
  </div>
</template>

<script setup lang="ts">
defineProps({
  item: {
    type: Object,
    required: true
  }
})
</script>

<style scoped>

</style>
