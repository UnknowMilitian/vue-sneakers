<template>
  <div>
    <div
      class="relative bg-white mx-auto flex flex-col w-full border border-slate-100 rounded-xl p-8 cursor-pointer transition hover:shadow-xl hover:transform hover:-translate-y-2"
    >
      <div class="absolute top-8 left-8">
        <img
          v-if="onClickFavorite"
          @click="onClickFavorite"
          :src="!isFavorite ? '/like-1.svg' : '/like-2.svg'"
          alt="Favorite"
        />
      </div>
      <img :src="imageUrl" class="w-auto" alt="Sneaker" />
      <p class="mt-2">{{ title }}</p>
      <div class="flex justify-between mt-5">
        <div class="flex flex-col gap-2">
          <span class="text-slate-300">Цена:</span>
          <span class="font-bold">{{ price }} руб.</span>
        </div>
        <img
          v-if="onClickAdd"
          @click="onClickAdd"
          :src="!isAdded ? '/plus.svg' : '/checked.svg'"
          alt="Plus"
        />
      </div>
    </div>
  </div>
</template>

<script setup>
defineProps({
  id: Number,
  imageUrl: String,
  title: String,
  price: Number,
  isFavorite: Boolean,
  isAdded: Boolean,
  onClickFavorite: Function,
  onClickAdd: Function
})
</script>
