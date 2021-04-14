<template>
  <div class="mx-10 mt-5 mb-2 space-y-2">
    <p class="text-3xl w-max">Xzawake</p>
    <div id="nav" class="text-xs flex justify-between">
      <div class="text-gray-400">
        <router-link to="/" class="px-1">Home</router-link>
        <router-link to="/about" class="px-1">About us</router-link>
        <router-link to="/menu" class="px-1">Menu</router-link>
      </div>
      <div class="flex mr-5">
        <div class="h-5 w-5 bg-gray-200"></div>
        <div class="h-5 w-5 bg-gray-200"></div>
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
