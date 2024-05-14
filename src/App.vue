<script setup>
import { ref, provide, computed } from 'vue'

import Header from './components/Header.vue'
import DrawerVue from './components/Drawer.vue'
import axios from 'axios'

// Cart (START)
const cart = ref([])

const drawerOpen = ref(false)

const totalPrice = computed(() => cart.value.reduce((acc, item) => acc + item.price, 0))
const vatPrice = computed(() => Math.round((totalPrice.value * 5) / 100))

const closeDrawer = () => {
  drawerOpen.value = false
}

const openDrawer = () => {
  drawerOpen.value = true
}

const addToCart = (item) => {
  cart.value.push(item)
  item.isAdded = true
}

const removeFromCard = (item) => {
  cart.value.splice(cart.value.indexOf(item), 1)
  item.isAdded = false
}

provide('cart', { cart, closeDrawer, openDrawer, addToCart, removeFromCard })

// /Cart (END)
</script>

<template>
  <DrawerVue v-if="drawerOpen" :total-price="totalPrice" :vatPrice="vatPrice" />

  <div class="bg-white w-[95%] xl:w-4/5 m-auto rounded-md md:rounded-xl shadow-xl my-5 md:my-14">
    <Header :total-price="totalPrice" @open-drawer="openDrawer" />

    <div class="p-10 px-4 md:px-10">
      <router-view></router-view>
    </div>
  </div>
</template>
