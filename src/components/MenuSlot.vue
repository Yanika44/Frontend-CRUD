<template>
  <div>
    <button class="text-xs text-center bg-green-400 float-right px-1 relative top-5 mr-1" @click="addToCart">+</button>
    <img :src="getImagePath" alt="" class="w-full h-16 bg-red-400" />
    <div class="flex justify-between text-xs">
        <p>{{food.name}}</p>
        <p>{{food.price}}</p>
    </div>
    
  </div>
</template>

<script>
export default {
  name: "MenuSlot",
  methods: {
    addToCart: ()=>{
      
    }
  },
  computed:{
    getImagePath(){
      return require("@/assets/" + this.food.image);
    }
  },
  mounted() {
  },
  props: {
    food: Object,
  },
};
</script>

<style></style>
