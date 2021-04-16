<template>
  <div>
    <button
      class="text-lg text-center bg-yellow-500 float-right px-1.5 relative top-8 mr-1"
      @click="addToCart"
    >
      +
    </button>
    <img :src="getImagePath" alt="" class="w-full bg-red-400" />
    <div class="flex justify-between text-xl">
      <p>{{ food.name }}</p>
      <p>{{ food.price }}</p>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "MenuSlot",
  methods: {
    addToCart() {
      axios
        .get(`http://localhost:3000/cart/${this.food.id}`)
        .then((result) => {
          let data = result.data;
          let quantity = data.quantity;
          axios.put(`http://localhost:3000/cart/${this.food.id}`, {
            quantity: quantity + 1,
          });
        })
        .catch(() => {
          axios.post(`http://localhost:3000/cart`, {
            id: this.food.id,
            quantity: 1,
          });
        });
    },
  },
  computed: {
    getImagePath() {
      return require("@/assets/" + this.food.image);
    },
  },
  props: {
    food: Object,
  },
};
</script>

<style></style>