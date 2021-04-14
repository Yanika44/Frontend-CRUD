<template>
  <div class="grid grid-cols-5 justify-between px-2 border-b border-gray-200">
    <p class="col-span-3">{{ item.name }}</p>
    <div class="col-span-2 flex justify-between">
      <input type="number" v-model="quantity" class="w-16" />
      <p class="text-center w-8">{{ totalPrice }}</p>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "CartSlot",
  computed: {
    totalPrice() {
      return this.quantity * this.item.price;
    },
  },
  data() {
    return {
      quantity: this.item.quantity,
    };
  },
  props: {
    item: Object,
  },
  updated() {
    this.$emit("update", {
      quantity: this.quantity,
      id: this.item.id,
    });
    if (this.quantity <= 0) {
      axios.delete(`http://localhost:3000/cart/${this.item.id}`).then(() => {
        this.$emit("del", this.item.id);
      }).catch(()=>{
        this.$emit("del", this.item.id);
      });
    }
  },
};
</script>

<style></style>
