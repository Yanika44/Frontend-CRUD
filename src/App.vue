<template>
  <div class="mx-10 mt-5 mb-2 space-y-2">
    <p class="text-6xl w-max">Xzawake</p>
    <div id="nav" class="text-xl flex justify-between">
      <div class="text-gray-400">
          <router-link to="/" class="px-1">Home</router-link>
          <router-link to="/about" class="px-1">About us</router-link>
          <router-link to="/menu" class="px-1">Menu</router-link>
          <router-link to="/cart" class="px-1">Cart</router-link>
      </div>
      <div class="flex mr-10 space-x-4">
        <div class="h-8 w-8 bg-gray-200"></div>
        <div class="h-8 w-8 bg-gray-200"></div>
      </div>
    </div>
    <hr class="relative bottom-2">
    <router-view />
  </div>
</template>

<style>
.router-link-exact-active{
  color: dimgrey;
}
</style>