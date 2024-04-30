<script setup>
// import MyHello from './components/MyHello.vue'
</script>

<template>
  <div class="bg-white w-4/5 m-auto h-screen rounded-xl shadow-xl mt-14">
    <header class="flex justify-between border-b border-slate-300 px-8">
      <div class="flex items-center gap-4">
        <img src="/logo.png" alt="Logo" class="w-10" />
        <div>
          <h2 class="text">Vue Sneakers</h2>
          <p>Магазин лучших кроссовок</p>
        </div>
      </div>

      <ul>
        <li>
          <img src="/cart.svg" alt="Cart" />
          <b>1205 руб.</b>
        </li>

        <li>
          <img src="/heart.svg" alt="Cart" />
          <b>Закладки</b>
        </li>

        <li>
          <img src="/profile.svg" alt="Profile" />
          <b>Профиль</b>
        </li>
      </ul>
    </header>

    <h1>Umariy Blog</h1>
  </div>
</template>
