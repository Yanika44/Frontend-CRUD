<template>
  <div class="mx-10 mt-5 mb-2 space-y-2">
    <p class="text-6xl w-max mb-6">XzawakezX</p>
    <div id="nav" class="text-xl flex justify-between">
      <div class="text-gray-400 flex space-x-10">
          <router-link to="/" class=" hover:bg-gray-600 hover:text-white transition duration-500 ease-in-out transform hover:-translate-y-2 hover:scale-100 rounded-full py-3 px-6">Home</router-link>
          <router-link to="/about" class="hover:bg-gray-600 hover:text-white transition duration-500 ease-in-out transform hover:-translate-y-2 hover:scale-100 rounded-full py-3 px-6">About us</router-link>
          <router-link to="/menu" class="hover:bg-gray-600 hover:text-white transition duration-500 ease-in-out transform hover:-translate-y-2 hover:scale-100 rounded-full py-3 px-6">Menu</router-link>
          <router-link to="/cart" class="hover:bg-gray-600 hover:text-white transition duration-500 ease-in-out transform hover:-translate-y-2 hover:scale-100 rounded-full py-3 px-6">Cart</router-link>
      </div>
      
      <div class="flex mr-10 space-x-4">
        <a href="https://www.facebook.com/yani.dear.3"><img src="@/assets/facebook.png" alt="No photo." width="35" height="30" class="opacity-25"></a>
        <a href="https://www.instagram.com/xzawakezx/"><img src="@/assets/instagram.png" alt="No photo." width="35" height="35" class="opacity-25"></a>
      </div>
    </div>
    <hr class="relative bottom-1 h-0.5" noshade="noshade" color="#EAEAEA"><br>
    <router-view />
  </div>
</template>

<style>
.router-link-exact-active{
  color: dimgrey;
}

/* lobster-regular - latin */
p {
  font-family: 'Satisfy';
  font-style: normal;
  font-weight: 400;
  src: url('../fonts/satisfy-v11-latin-regular.woff') format('woff');
}


</style>