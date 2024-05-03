<template>
  <div class="flex border items-center border-slate-200 p-4 rounded-xl gap-4">
    <img class="w-16 h-16" src="/sneakers/sneakers-1.jpg" alt="Sneaker" />

    <div class="flex flex-col">
      <p>Кроссовки Nike Air Max 200</p>

      <div class="flex justify-between mt-2">
        <b>12990 руб</b>
        <img
          class="opacity-40 hover:opacity-100 cursor-pointer transition"
          src="/close.svg"
          alt=""
        />
      </div>
    </div>
  </div>
</template>

<script setup>
defineProps({
  img: String,
  title: String,
  price: Number,
  onClickDelete: Function
})
</script>
