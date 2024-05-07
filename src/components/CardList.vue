<script setup>
import CardVue from './Card.vue'

defineProps({
  items: Array
})

const emit = defineEmits(['addToFavorite', 'addToCart'])
</script>

<template>
  <div>
    <div class="grid grid-cols-4 gap-5 mt-10">
      <CardVue
        v-for="item in items"
        :key="item.id"
        :id="item.id"
        :title="item.title"
        :image-url="item.imageUrl"
        :price="item.price"
        :isFavorite="item.isFavorite"
        :onClickAdd="() => emit('addToCart', item)"
        :onClickFavorite="() => emit('addToFavorite', item)"
        :isAdded="item.isAdded"
      />
    </div>
  </div>
</template>
