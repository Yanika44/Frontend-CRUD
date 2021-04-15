<template>
  <div class="mx-16">
    <div
      class="w-full grid grid-cols-5 px-2 font-bold border-b-2 border-gray-200 text-xl"
    >
      <p class="col-span-3">name</p>
      <div class="col-span-2 flex justify-between">
        <p>quantity</p>
        <p>price</p>
      </div>
    </div>
    <cart-slot
      v-for="item in cart"
      :key="item.id"
      :item="item"
      @update="update"
      @del="del"
      class="text-lg"
    ></cart-slot>
    <div class="w-full grid grid-cols-5 px-2 border-t-2 border-gray-200">
      <p class="col-span-3"></p>
      <div class="col-span-2 flex justify-between">
        <p></p>
        <p class="w-8 text-center">{{ totalPrice }}</p>
      </div>
    </div>
  </div>
</template>

<script>
import CartSlot from "../components/CartSlot.vue";
import axios from "axios";
export default {
  name: "Cart",
  data() {
    return {
      cart: [],
    };
  },
  components: {
    CartSlot,
  },
  computed: {
    totalPrice() {
      let sum = 0;
      this.cart.forEach((item) => {
        sum += item.price * item.quantity;
      });
      return sum;
    },
  },
  methods: {
    update(payload) {
      let quantity = payload.quantity;
      let id = payload.id;
      this.cart.find((item) => item.id == id).quantity = quantity;
      axios
        .put("http://localhost:3000/cart/" + id, {
          quantity: quantity,
        })
    },
    del(id){
      this.cart = this.cart.filter((item)=>item.id != id)
    }
  },
  mounted() {
    axios.get("http://localhost:3000/cart").then((result) => {
      result.data.forEach((item) => {
        let cartItem = {};
        cartItem.quantity = parseInt(item.quantity);
        cartItem.id = item.id;
        axios
          .get(`http://localhost:3000/menu/${item.id}`)
          .then((result) => {
            cartItem.name = result.data.name;
            cartItem.price = parseInt(result.data.price);
          })
          .then(() => {
            this.cart.push(cartItem);
          });
      });
    });
  },
};
</script>

<style></style>