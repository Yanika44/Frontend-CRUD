<template>
  <div class="grid grid-cols-5 gap-3 mx-12">
      <menu-slot v-for="food in foods" :key="food.id" :food="food"></menu-slot>
  </div>
</template>

<script>
import MenuSlot from "../components/MenuSlot.vue";
import axios from "axios";
export default {
    neme: "Menu",
    data() {
        return {
            foods: null
        }
    },
    mounted(){
        axios.get("http://localhost:3000/menu").then((result)=>{
            this.foods = result.data;
        })
    },
    components: {
        MenuSlot
    }
}
</script>

<style>

</style>