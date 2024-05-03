<template>
  <div>
    <div class="grid grid-cols-4 gap-5 mt-10">
      <CardVue
        title="Мужские Кроссовки Nike Blazer Mid Suede"
        image-url="/sneakers/sneakers-1.jpg"
        price="5500"
        :is-added="true"
        :isFavorite="true"
        :onClickAdd="onClickAdd"
      />
    </div>
  </div>
</template>

<script setup>
import CardVue from './Card.vue'

const onClickAdd = () => {
  alert('111')
}
</script>
