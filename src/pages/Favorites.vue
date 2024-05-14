<script setup>
import axios from 'axios'
import { onMounted, ref } from 'vue'
import CardList from '../components/CardList.vue'

const favorites = ref([])

onMounted(async () => {
  try {
    const { data } = await axios.get(
      `https://d4b982c477888fd4.mokky.dev/favorites?_relations=items`
    )

    favorites.value = data.map((obj) => obj.item)
  } catch (error) {
    console.log(error)
  }
})
</script>

<template>
  <div>
    <h2 class="text-3xl font-bold mb-8 text-center md:text-left">Мои закладки</h2>

    <CardList :items="favorites" is-favorites />
  </div>
</template>
