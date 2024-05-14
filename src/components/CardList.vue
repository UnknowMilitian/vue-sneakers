<script setup>
import CardVue from './Card.vue'

defineProps({
  items: Array,
  isFavorites: Boolean
})

const emit = defineEmits(['addToFavorite', 'addToCart'])
</script>

<template>
  <div>
    <div
      class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 xl:grid-cols-4 gap-5 mt-10"
      v-auto-animate
    >
      <CardVue
        v-for="item in items"
        :key="item.id"
        :id="item.id"
        :title="item.title"
        :image-url="item.imageUrl"
        :price="item.price"
        :isFavorite="item.isFavorite"
        :onClickAdd="isFavorites ? null : () => emit('addToCart', item)"
        :onClickFavorite="isFavorites ? null : () => emit('addToFavorite', item)"
        :isAdded="item.isAdded"
      />
    </div>
  </div>
</template>
